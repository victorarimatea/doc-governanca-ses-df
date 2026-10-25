# Especificação do Workflow de Transcrição Documental

**Projeto:** Transcrição de Documento para Arquivamento em Markdown
**Responsável:** Diretor de Transformação Digital — SES-DF
**Versão:** 1.1 — 2026-06-01
**Status:** Ativo

---

## 1. Intenção do Comandante

### Missão

Transformar documentos regulatórios oficiais em arquivos Markdown estruturados, fiéis ao original, auditáveis, pesquisáveis e reutilizáveis — constituindo a camada documental primária do ecossistema `governanca-ses-df`.

### Estado Final Esperado

Cada documento transcrito deve satisfazer **todos** os critérios abaixo. Este é o benchmark de qualidade que o pipeline deve verificar autonomamente antes de considerar uma transcrição concluída:

#### 1.1 Estrutura obrigatória

- [ ] Front Matter YAML válido com todos os campos preenchidos (nenhum campo vazio ou "Não identificado" sem justificativa)
- [ ] Ficha Técnica Documental em tabela Markdown com 12 linhas
- [ ] Seção "Observações da Conversão" presente e não vazia
- [ ] Seção "Conteúdo Integral Transcrito" presente e com conteúdo substantivo
- [ ] Seção "Controle de Integridade" com status de conversão explícito

#### 1.2 Fidelidade ao original

- [ ] Nenhum elemento estrutural jurídico ausente (ver §2.1)
- [ ] Nenhum artefato de extração presente no conteúdo (ver §2.2)
- [ ] Assinatura(s) presente(s) e corretamente formatadas
- [ ] Texto integral sem truncamento — número de parágrafos coerente com o número de páginas
- [ ] Nenhum texto refluxado com quebras de linha espúrias (linhas de conteúdo com menos de 40 caracteres intercaladas com linhas longas são sinal de alerta)

#### 1.3 Organização visual

- [ ] Cada marcador estrutural jurídico inicia em seu próprio parágrafo (linha em branco antes)
- [ ] Tabelas Markdown válidas (header + separador + linhas de dados)
- [ ] Nenhum parágrafo inicia com letra minúscula (exceto continuação de texto, alíneas)

#### 1.4 Rastreabilidade

- [ ] `arquivo_original` corresponde ao nome exato do PDF fonte
- [ ] `fonte_externa` contém URL válida ou "Não identificado" justificado
- [ ] `versao_transcricao` reflete o número de revisões do documento

---

## 2. Definições Técnicas

### 2.1 Elementos Estruturais Jurídicos (devem iniciar novo parágrafo)

| Marcador | Exemplo | Regex de detecção |
|---|---|---|
| Artigo | `Art. 1º` | `^Art\.\s+\d+` |
| Parágrafo numerado | `§ 1º` | `^§\s*\d+` |
| Parágrafo único | `Parágrafo único.` | `^Parágrafo\s+[Úú]nico` |
| Inciso | `I -` `XIV —` | `^[IVX]+\s+[-–—]` |
| Alínea | `a)` `b)` | `^[a-z])\s` |
| Capítulo | `CAPÍTULO I` | `^CAPÍTULO\s` |
| Seção | `Seção I` | `^SEÇÃO\s` ou `^Seção\s` |
| Subseção | `SUBSEÇÃO I` | `^SUBSEÇÃO\s` |
| Título | `TÍTULO I` | `^TÍTULO\s` |
| Livro | `LIVRO I` | `^LIVRO\s` |
| Anexo | `ANEXO I` | `^ANEXO\s[IVX]+` |

### 2.2 Artefatos de Extração (devem ser filtrados)

| Tipo | Exemplo | Filtro aplicado |
|---|---|---|
| Timestamp DOU | `27/04/2026, 23:46` | Regex `^\d{2}/\d{2}/\d{4},\s+\d{2}:\d{2}` |
| URL de acesso | `https://www.in.gov.br/...` | Regex `^https?://` |
| Numeração de página | `3/118` | Regex `^\d+/\d+$` |
| Cabeçalho DOU | `DIÁRIO OFICIAL DA UNIÃO` | Exato |
| Metadados DOU | `Publicado em:` `Órgão:` `Edição:` `Seção:` `Página:` | Prefixo |
| Disclaimer DOU | `Este conteúdo não substitui o publicado na versão certificada.` | Exato |
| Cabeçalho SINJ-DF | `Lei XXXX de DD/MM/AAAA` | Regex `^Lei\s+\d+\s+de\s+\d{2}/\d{2}/\d{4}` |
| Rodapé BVS | `Saúde Legis - Sistema de Legislação da Saúde` | Regex `^Sa[ãú]de Legis` |
| Advertência BVS | `Este texto não substitui...` | Regex `^Este texto n` |

### 2.3 Tipos de Fonte e Método de Extração Recomendado

| Tipo de Fonte | Método | Observações na Conversão |
|---|---|---|
| Portal Planalto.gov.br | `extract_dict_mode` | "PDF extraído do portal Planalto.gov.br, processado localmente." |
| DOU/Imprensa Nacional (PDF) | `extract_blocks` + reflow | "PDF oficial gerado a partir do DOU/Imprensa Nacional, processado localmente." |
| SINJ-DF | `extract_blocks` + reflow | "PDF extraído do SINJ-DF, processado localmente." |
| BVS Saúde Legis | `extract_blocks` + reflow | "PDF extraído do BVS Saúde Legis, processado localmente." |
| Portais internacionais (WHO, IMDRF etc.) | `extract_blocks` + reflow | Indicar idioma original e portal específico |

---

## 3. Histórico de Problemas e Soluções

### P01 — Fragmentação de nomes e datas no bloco de assinaturas
**Sintoma:** Data e nomes dos signatários ficavam fragmentados ou fundidos com o sufixo de datação.
**Causa raiz:** `split_signature_names()` usava transição minúscula→maiúscula como critério de quebra.
**Solução:** Detectar sufixo `;` após data → manter linha intacta. Dividir nomes apenas em espaços duplos (`\s{2,}`).
**Status:** ✅ Resolvido.

### P02 — Artefatos DOU no conteúdo transcrito
**Sintoma:** URLs, timestamps e cabeçalhos DOU apareciam no corpo do documento.
**Causa raiz:** PDFs do DOU incluem metadados de acesso web no layout de página.
**Solução:** Lista de filtros (`SKIP_EXACT`, `SKIP_RE`) aplicados linha a linha.
**Status:** ✅ Resolvido.

### P03 — Cabeçalhos SINJ-DF e BVS repetidos entre páginas
**Sintoma:** "Lei 7215 de 02/01/2023" e "Saúde Legis..." apareciam como parágrafos de conteúdo.
**Causa raiz:** Cabeçalhos e rodapés de página tratados como texto normativo.
**Solução:** Regexes específicas adicionadas ao `SKIP_RE`.
**Status:** ✅ Resolvido.

### P04 — Marcadores estruturais jurídicos fundidos com parágrafos anteriores
**Sintoma:** `Art. 2º` aparecia como continuação do parágrafo do `Art. 1º`.
**Causa raiz:** O reflow juntava linhas sem verificar marcadores estruturais.
**Solução:** `LEGAL_STRUCT` regex aplicado durante o reflow e em `apply_legal_structure()`.
**Status:** ✅ Resolvido — implementado em v2.3 (dict-mode) e v1.2 (extract_blocks).

### P05 — Quebras de linha espúrias no texto corrido
**Sintoma:** Parágrafos com texto quebrado palavra por palavra.
**Causa raiz:** `extract_blocks` preservava todas as quebras internas dos blocos.
**Solução:** `reflow_block_lines()` — linhas juntadas com espaço exceto antes de marcadores jurídicos.
**Status:** ✅ Resolvido.

### P06 — ANEXO II da Portaria 3.233/2024 — cobertura parcial de municípios
**Sintoma:** Parser original recuperava apenas ~75% dos 5.570 municípios.
**Causa raiz:** Layout de tabela com coluna de valor extraída separadamente.
**Solução:** Parser regex com `MUN_PATTERN` sobre texto achatado + merge de blocos partidos + fallback `MUN_NOVAL`.
**Resultado:** 5.571 municípios; 4.241 com valor, 1.330 marcados como N/I.
**Status:** ✅ Resolvido com ressalva documentada.

### P07 — Redação imprecisa de "Observações da Conversão" para PDFs do DOU
**Sintoma:** Redação sugeria que o DOU foi acessado diretamente, não o PDF local.
**Causa raiz:** Redação genérica sem distinguir fonte de origem do artefato processado.
**Solução:** Funções `obs_dou_pdf()` e `obs_portal_pdf()` com redação padronizada.
**Status:** ✅ Resolvido.

### P08 — Arquivo original inutilizável (capa visual sem conteúdo textual)
**Sintoma:** PDF de 1 página sem texto extraível — identificado no EU AI Act Overview 2024.
**Causa raiz:** Arquivo é imagem de capa (JPEG renderizado como PDF), não o documento completo.
**Solução:** Ver §3.1 — Protocolo de Exceção.
**Status:** ✅ Protocolo formalizado.

### P09 — Marcação de tabela feita só por sombreamento de célula
**Sintoma:** na RENASES 2012 (Portaria GM/MS 841/2012), os critérios de acesso 1 a 6 de cada ação ou serviço são células pintadas de cinza, sem texto. A extração de texto não captura nada, e a tabela sai sem a informação principal.
**Causa raiz:** a informação está no desenho da página (retângulos de preenchimento), não na camada de texto.
**Solução:** ler `page.get_drawings()`. A grade são retângulos pretos finos e a marcação é o preenchimento cinza (~0,75). As bandas de linha vêm das horizontais cobertas pelo vertical da coluna de critérios. A coluna é atribuída pelo centro da célula, e cada célula marcada vira `■` no Markdown. Conferência visual obrigatória por renderização de pelo menos duas páginas. Registrar a adaptação de representação nas Observações.
**Status:** ✅ Resolvido (22/10/2026).

### P10 — Palavras quebradas sem hífen em células estreitas
**Sintoma:** em PDF de editor de texto, palavra longa demais para a célula é partida sem hífen ("anatomopatológico" + "s", "plásticas/reparador" + "as", "(psicodiagnósticos" + ")"). Juntar sempre com espaço corrompe a palavra; juntar por heurística ampla funde palavras legítimas ("otorrinolaringologia e").
**Causa raiz:** o editor quebra a palavra no limite da célula; não há marca de hifenização.
**Solução:** juntar sem espaço só quando: (a) a linha anterior tem um único token encostado na borda direita da célula; e (b) a linha seguinte começa por pontuação de fechamento, ou é fragmento de uma letra, ou a junção forma palavra existente no vocabulário do próprio documento. Listar todas as junções feitas e conferir uma a uma.
**Status:** ✅ Resolvido (22/10/2026).

### P11 — Tabela de PDF de editor de texto sem espaços entre palavras
**Sintoma:** na Portaria de Consolidação nº 1/2017 (PDF do Saúde Legis gerado pelo Word), `find_tables().extract()` devolve o texto das células sem espaços ("TABELADEREFERÊNCIADECORESCMYK").
**Causa raiz:** o PDF posiciona as palavras sem caractere de espaço; a extração por célula concatena os glifos.
**Solução:** montar o texto de cada célula pelas palavras de `page.get_text("words")` cujo centro cai na célula, na ordem de bloco, linha e palavra. Quando o detector deixa colunas inteiras de fora (palavras alinhadas às linhas da tabela, mas fora da sua caixa), acrescentar essas colunas pelas faixas verticais de cada linha. Conferência palavra a palavra obrigatória.
**Status:** ✅ Resolvido (24/10/2026).

### P12 — Remissão de origem quebrada em parágrafo à parte
**Sintoma:** em texto compilado do Saúde Legis, a remissão "(Origem: PRT MS/GM 1646/2015, Art. 2º)" quebra antes de "Art." e o reflow abre parágrafo novo, como se fosse um artigo ("Art. 2º)").
**Causa raiz:** a linha de continuação começa por "Art.", que é marcador jurídico.
**Solução:** depois do reflow, reunir ao parágrafo anterior o parágrafo curto que fecha um parêntese deixado aberto, descontando o ")" dos marcadores de alínea ("a)") na contagem. Conferir que nenhum parágrafo termina com parêntese aberto e que a numeração dos artigos não tem repetição.
**Status:** ✅ Resolvido (24/10/2026).

---

### 3.1 — Protocolo de Exceção: Arquivo Original Inutilizável

**Condições de ativação:** zero blocos em todas as páginas; OCR < 50 palavras; documento de 1 página com dimensões de capa; inspeção visual confirma capa/logo sem corpo textual.

**Passos obrigatórios:**
1. Registrar limitação nas Observações da Conversão
2. Buscar documento na fonte oficial (DOI → portal do órgão → repositório citado)
3. Verificar autenticidade — apenas fontes oficiais aceitas
4. Atualizar `arquivo_original` (manter nome local) e `fonte_externa` (URL real de extração)
5. Não prosseguir sem conteúdo verificável
6. Se fonte oficial inacessível: status "Conversão Pendente — Fonte Indisponível"

---


### P13 — Grade aninhada do SINJ-DF (cada célula é uma caixa própria)

**Problema:** nas tabelas da Portaria SES/DF nº 321/2023 (páginas 20 a 23), cada célula é uma caixa desenhada à parte dentro de uma célula maior. `find_tables()` vê só a grade externa (duas colunas) e junta o texto de várias caixas numa célula, misturando horários e legendas.
**Solução:** usar `find_tables()` só para achar a área da tabela. Cada caractere vai para a caixa formada pelas bordas desenhadas mais próximas à sua volta (linhas e retângulos finos cinzentos; os traços azuis de link e os pretos de tachado ficam de fora). As caixas são ordenadas em linhas e colunas pela posição do canto superior esquerdo. Dentro da caixa, um espaço é inserido quando há intervalo horizontal entre caracteres. Conferência: palavras e, quando o PDF cola células vizinhas sem espaço, caracteres (sem espaço e pontuação).
**Limitação:** células mescladas e caixas de larguras diferentes são acomodadas numa grade simples; uma célula pode ficar deslocada para a coluna vizinha. O conteúdo fica completo.

### P14 — Duas redações do mesmo ato (original e republicada)

**Problema:** a Portaria SAS/MS nº 118/2014 foi republicada no DOU "por ter saído com incorreção no original", com diferenças de conteúdo. Uma transcrição só, ou a mistura das duas, apaga a diferença; dois nomes sem relação entre si parecem dois atos.
**Solução (aprovada pelo Victor em 25/10/2026):** um par PDF + Markdown para cada redação, com o mesmo nome-base e os sufixos `-ORIGINAL` e `-REPUBLICADA` (ex.: `PORTARIA-SASMS-118-2014-DESATIVACAO-CNES-ORIGINAL.md` e `...-REPUBLICADA.md`). Cada transcrição diz, nas Observações, qual redação é, a publicação de cada uma (DOU, data, seção, página), que a republicada é a que vale para o conteúdo, onde está a outra e quais são as diferenças. Nenhuma combina dispositivos das duas. O `status_documental` da original diz que foi substituída pela republicação. Vale também para retificação publicada como novo texto integral.
**Limitação:** a retificação publicada só como errata (trecho corrigido, sem texto integral) não gera par; registra-se nas Observações da transcrição do ato.

### P15 — Página da internet impressa em PDF pelo navegador (DOU no in.gov.br, Saúde Legis)

**Problema:** a Portaria de Consolidação SAES/MS nº 1/2022 e a Resolução de Consolidação CIT nº 1/2021 chegaram como páginas de portal salvas em PDF pelo navegador, não como fac-símile do diário. A regra do DOU (desfazer o hífen do fim da linha) apagaria hífens reais (216 casos na consolidação SAES); cada página traz cabeçalho ou rodapé de impressão; na continuação de tabelas entre páginas, palavras da primeira linha ficavam fora das células detectadas.
**Solução (aprovada pelo Victor em 25/10/2026, skill v1.6, §WEB):** hífen do fim da linha mantido; cabeçalho e rodapé de impressão retirados linha a linha (data e hora, título da página, endereço, "n/N"); metadados do DOU da primeira página levados para a ficha; data de impressão registrada como data do texto; palavras órfãs devolvidas à célula pela linha e pela coluna; remissões "Art. N," reunidas ao parágrafo anterior; títulos de anexo reunidos antes de "(Origem: …)". Conferência palavra a palavra sem diferença nos dois documentos.
**Limitação:** tabelas quebradas entre páginas ficam como uma tabela por página.

## 4. Etapa de Auto-Verificação

| Critério | Verificação |
|---|---|
| Front Matter válido | Parse YAML + presença de todos os campos obrigatórios |
| Seções obrigatórias | Presença das 5 seções por header `#` |
| Conteúdo não vazio | Seção de conteúdo > 200 caracteres |
| Marcadores jurídicos presentes | Regex sobre o conteúdo — ausência total = falha |
| Ausência de artefatos | Busca por padrões de artefato no conteúdo |
| Quebras espúrias | > 3 linhas consecutivas < 40 caracteres = alerta |
| Assinatura presente | Detecção de data no padrão `SIG_PATTERN` |

**Resultados:** PASSOU → "Conversão Completa" | ALERTA → ressalva | FALHOU → correção autônoma ou registro

---

## 5. Organização dos Arquivos de Saída

```
governanca-ses-df/
├── WORKFLOW-ESPECIFICACAO.md
├── 01-legislacao-federal/
├── 02-legislacao-distrital/
├── 03-portarias-ministeriais/
├── 03-resolucoes-cfm/
├── 04-resolucoes-anvisa/
└── 05-referencias-internacionais/
```

---

## 6. Convenção de Nomenclatura de Arquivos

```
[TIPO]-[ORGAO]-[NUMERO]-[ANO]-[DESCRICAO-CURTA].md
```

Exemplos: `LEI-FEDERAL-12965-2014-MARCO-CIVIL-DA-INTERNET.md`, `RESOLUCAO-CFM-2314-2022-TELEMEDICINA.md`

---

## 7. Convenção de Versão de Transcrição

| Versão | Significado |
|---|---|
| `1.0` | Primeira transcrição |
| `1.1`, `1.2`... | Correções de extração |
| `2.0` | Reprocessamento completo |

---

## 8. Visão de Automação (Roadmap)

- **Fase atual:** Assistida com controle de qualidade humano
- **Próxima fase:** Assistida com auto-verificação (PASSOU → entrega automática; ALERTA/FALHOU → revisão humana)
- **Fase futura:** Sequencial autônoma com relatório consolidado
- **Condições para progressão:** Taxa PASSOU ≥ 95% em ≥ 10 documentos consecutivos; nenhum P01–P07 reincidente

---

## 9. Status dos Documentos

### Fase 1 — Regulamentações nacionais

| # | Documento | Arquivo | Status |
|---|---|---|---|
| 01 | Lei 12.965/2014 — Marco Civil | `LEI-FEDERAL-12965-2014-MARCO-CIVIL-DA-INTERNET.md` | ✅ v2.3 |
| 02 | Lei 13.709/2018 — LGPD | `LEI-FEDERAL-13709-2018-LGPD.md` | ✅ v2.3 |
| 03 | Lei 13.853/2019 — Altera LGPD/ANPD | `LEI-FEDERAL-13853-2019-ALTERA-LGPD-CRIA-ANPD.md` | ✅ v1.3 |
| 04 | Lei 13.787/2018 — Digitalização | `LEI-FEDERAL-13787-2018-DIGITALIZACAO-DOCUMENTOS.md` | ✅ v1.3 |
| 05 | Lei 13.989/2020 — Telemedicina | `LEI-FEDERAL-13989-2020-TELEMEDICINA.md` | ✅ v1.2 |
| 06 | Lei GDF 7.215/2023 — Telemedicina DF | `LEI-DISTRITAL-GDF-7215-2023-TELEMEDICINA-DF.md` | ✅ v1.2 |
| 07 | Portaria GM/MS 3.632/2020 — ESD28 | `PORTARIA-GMMS-3632-2020-ESTRATEGIA-SAUDE-DIGITAL-ESD28.md` | ✅ v1.2 |
| 08 | Portaria GM/MS 3.233/2024 — SUS Digital | `PORTARIA-GMMS-3233-2024-PROGRAMA-SUS-DIGITAL.md` | ✅ v1.2 |
| 09 | Portaria GM/MS 3.727/2024 — INMSD | `PORTARIA-GMMS-3727-2024-INMSD.md` | ✅ v1.1 |
| 10 | Portaria GM/MS 7.495/2025 | `PORTARIA-GMMS-7495-2025-SUS-DIGITAL-AGORA-TEM-ESPECIALISTAS.md` | 🔄 Pendente |
| 11 | Portaria SESDF 513/2022 | `PORTARIA-SESDF-513-2022-SERVICO-TELEMEDICINA-DF.md` | 🔄 Pendente |
| 12 | Portaria SAES/MS 2.326/2024 | `PORTARIA-SAESMS-2326-2024-TELESSAUDE-TABELA-SUS.md` | 🔄 Pendente |
| 13 | Resolução CFM 2.227/2018 | `RESOLUCAO-CFM-2227-2018-TELEMEDICINA.md` | 🔄 Pendente |
| 14 | Resolução CFM 2.314/2022 | `RESOLUCAO-CFM-2314-2022-TELEMEDICINA.md` | 🔄 Pendente |
| 15 | Resolução CFM 2.454/2026 | `RESOLUCAO-CFM-2454-2026-INTELIGENCIA-ARTIFICIAL.md` | 🔄 Pendente |
| 16 | RDC ANVISA 657/2022 | `RDC-ANVISA-657-2022-SAMD.md` | 🔄 Pendente |
| 17 | IN SES-DF 01/2023 | `IN-SESDF-01-2023-TELEMEDICINA-DF.md` | 🔄 Pendente |

### Fase 2 — Referências internacionais (10 arquivos bilíngues EN+PT)

| # | Documento | Status |
|---|---|---|
| 18-19 | IMDRF SaMD Key Definitions 2013 (EN+PT) | ✅ v1.0 |
| 20-21 | IMDRF SaMD Risk Categorization 2014 (EN+PT) | ✅ v1.0 |
| 22-23 | EU AI Act Overview 2024 (EN+PT) | ✅ v1.0 |
| 24-25 | OECD Health Data Governance 2025 (EN+PT) | ✅ v1.0 |
| 26-27 | PAHO 8 Principles Digital Transformation 2021 (EN+PT) | ✅ v1.0 |

### Fase 4 — Base normativa da RENASES (projeto Carteira de Serviços, CICS/SES-DF)

| # | Documento | Arquivo | Status |
|---|---|---|---|
| 30 | Decreto 7.508/2011 — Organização do SUS (texto compilado) | `01-legislacao-federal/DECRETO-FEDERAL-7508-2011-ORGANIZACAO-DO-SUS.md` | ✅ v1.1 (PDF preservado registrado) |
| 31 | Portaria GM/MS 841/2012 — RENASES 1ª versão (com a lista) | `03-portarias-ministeriais/PORTARIA-GMMS-841-2012-RENASES-1A-VERSAO.md` | ✅ v1.0 (Conversão Revisada — P09, P10) |
| 32 | Resolução CIT 2/2012 — Diretrizes da RENASES (revogada por consolidação; texto nos arts. 26 a 46 da Res. Consolidação CIT 1/2021) | `03-portarias-ministeriais/RESOLUCAO-CIT-2-2012-DIRETRIZES-RENASES.md` | ✅ v1.3 |
| 33 | Informe RENASES — pauta da CIT, fev/2012 | `08-documentos-tecnicos/INFORME-CIT-RENASES-2012-OFICINA-TRIPARTITE.md` | ✅ v1.1 (PDF preservado) |
| 34 | Portaria de Consolidação GM/MS 1/2017 — organização e funcionamento do SUS (absorve a Portaria 841/2012 nos arts. 14 a 21) | `03-portarias-ministeriais/PORTARIA-CONSOLIDACAO-GMMS-1-2017-ORGANIZACAO-E-FUNCIONAMENTO-DO-SUS.md` | ✅ v1.0 (Conversão Completa com ressalva — Anexo XV cortado na margem do PDF de origem) |
| 56 | Resolução de Consolidação CIT nº 1/2021 — consolida as resoluções da CIT (123 artigos, 11 anexos); absorve a Resolução CIT 2/2012 nos arts. 26 a 46 e a revoga (art. 122, IV) | `03-portarias-ministeriais/RESOLUCAO-CONSOLIDACAO-CIT-1-2021-RESOLUCOES-DA-CIT.md` | ✅ v1.0 (Conversão Completa) |

### Fase 5 — Normas distritais do guia "Rotina que Gera Resultado" (migradas em 24/10/2026)

| # | Documento | Arquivo | Status |
|---|---|---|---|
| 35 | Decreto 39.048/2018 | `02-legislacao-distrital/DECRETO-DISTRITAL-39048-2018-REGULAMENTA-TPD.md` | ✅ v1.0 (Conversão Completa) |
| 36 | Decreto 39.546/2018 | `02-legislacao-distrital/DECRETO-DISTRITAL-39546-2018-REGIMENTO-INTERNO-SESDF.md` | ✅ v1.0 (Conversão Completa) |
| 37 | Decreto 44.322/2023 | `02-legislacao-distrital/DECRETO-DISTRITAL-44322-2023-PDPAS.md` | ✅ v1.0 (Conversão Completa) |
| 38 | Decreto 46.893/2025 | `02-legislacao-distrital/DECRETO-DISTRITAL-46893-2025-COPLANS.md` | ✅ v1.0 (Conversão Completa) |
| 39 | Decreto 48.924/2026 | `02-legislacao-distrital/DECRETO-DISTRITAL-48924-2026-REDE-DE-INTELIGENCIA-EM-SAUDE.md` | ✅ v1.0 (Conversão Completa) |
| 40 | Lei distrital 6.137/2018 | `02-legislacao-distrital/LEI-DISTRITAL-6137-2018-TPD.md` | ✅ v1.0 (Conversão Completa) |
| 41 | Portaria Conjunta SES/FEPECS 2/2023 | `02-legislacao-distrital/PORTARIA-CONJUNTA-SESDF-FEPECS-2-2023-PRATICAS-CURRICULARES.md` | ✅ v1.0 (Conversão Completa) |
| 42 | Portaria SES-DF 1.357/2018 | `02-legislacao-distrital/PORTARIA-SESDF-1357-2018-ATENCAO-HOSPITALAR.md` | ✅ v1.0 (Conversão Completa) |
| 43 | Portaria SES-DF 1.388/2018 | `02-legislacao-distrital/PORTARIA-SESDF-1388-2018-POLITICA-DISTRITAL-DE-REGULACAO.md` | ✅ v1.0 (Conversão Completa) |
| 44 | Portaria SES-DF 252/2024 | `02-legislacao-distrital/PORTARIA-SESDF-252-2024-ALTERA-PORTARIA-321-2023.md` | ✅ v1.0 (Conversão Completa) |
| 45 | Portaria SES-DF 321/2023 | `02-legislacao-distrital/PORTARIA-SESDF-321-2023-HORARIOS-ESCALAS-E-FREQUENCIA.md` | ✅ v1.0 (Conversão Completa) |
| 46 | Portaria SES-DF 337/2023 | `02-legislacao-distrital/PORTARIA-SESDF-337-2023-TPD.md` | ✅ v1.0 (Conversão Completa) |
| 47 | Portaria SES-DF 386/2017 | `02-legislacao-distrital/PORTARIA-SESDF-386-2017-COMPONENTE-HOSPITALAR-RUE.md` | ✅ v1.0 (Conversão Revisada (anexos em imagem)) |
| 48 | Portaria SES-DF 473/2023 | `02-legislacao-distrital/PORTARIA-SESDF-473-2023-REGULAMENTA-PDPAS.md` | ✅ v1.0 (Conversão Completa) |
| 49 | Portaria SES-DF 510/2025 | `02-legislacao-distrital/PORTARIA-SESDF-510-2025-EGRESSOS-DE-UTI.md` | ✅ v1.0 (Conversão Completa) |
| 50 | Portaria SES-DF 536/2018 | `02-legislacao-distrital/PORTARIA-SESDF-536-2018-URGENCIAS-EM-SAUDE-MENTAL.md` | ✅ v1.0 (Conversão Revisada (anexos em imagem)) |
| 51 | Portaria SES-DF 570/2020 | `02-legislacao-distrital/PORTARIA-SESDF-570-2020-TRANSFERENCIAS-INTER-HOSPITALARES.md` | ✅ v1.0 (Conversão Completa) |
| 52 | Portaria SES-DF 839/2020 | `02-legislacao-distrital/PORTARIA-SESDF-839-2020-REVOGA-PORTARIA-570-2020.md` | ✅ v1.0 (Conversão Completa) |

### Fase 6 — Base normativa do CNES (projeto Carteira de Serviços, CICS/SES-DF)

| # | Documento | Arquivo | Status |
|---|---|---|---|
| 53 | Portaria SAS/MS 118/2014 — redação republicada (DOU de 16/06/2014); revogada por consolidação, texto nos arts. 227 a 230 da Portaria de Consolidação SAES/MS nº 1/2022 | `03-portarias-ministeriais/PORTARIA-SASMS-118-2014-DESATIVACAO-CNES-REPUBLICADA.md` | ✅ v1.0 (Conversão Revisada — fonte em imagem, leitura visual conferida com OCR e com a consolidação) |
| 54 | Portaria SAS/MS 118/2014 — redação original (DOU de 19/02/2014) | `03-portarias-ministeriais/PORTARIA-SASMS-118-2014-DESATIVACAO-CNES-ORIGINAL.md` | ✅ v1.0 (Conversão Completa) |
| 55 | Portaria de Consolidação SAES/MS nº 1/2022 — atenção especializada (433 artigos, 61 anexos); o CNES está no Título III, Capítulo III, arts. 217 a 290; absorve a Portaria SAS/MS 118/2014 e a revoga (art. 432, LXIV) | `03-portarias-ministeriais/PORTARIA-CONSOLIDACAO-SAESMS-1-2022-ATENCAO-ESPECIALIZADA.md` | ✅ v1.0 (Conversão Revisada — dois anexos em imagem, leitura visual) |

### Fase 3 — Migração GitHub (este repositório)
✅ Repositório `governanca-ses-df` criado em 2026-06-02
🔄 Upload dos 28 arquivos .md — pendente

---

*Documento mantido pelo pipeline de transcrição. Atualizar a cada nova solução (§3) e mudança de status (§9).*
