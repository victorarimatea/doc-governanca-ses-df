# Backlog de Versões — governanca-ses-df

---

## v1.1 — 2026-06-21

**Tipo de alteração:** Adição (nova categoria documental) + registro de pendência
**Autorizado por:** victorarimatea
**Status:** ativo
**Exposição de motivos:** Adição do primeiro documento da categoria de
instrumentos de planejamento estratégico-orçamentário — a Programação Anual de
Saúde (PAS) SES-DF 2026. As categorias documentais até então cobriam legislação
federal, legislação distrital, portarias ministeriais, resoluções CFM,
resoluções ANVISA e referências internacionais. A PAS não se enquadra em
nenhuma delas: é instrumento de planejamento, abrindo uma categoria nova. O
documento foi transcrito pela skill S05 (v1.1) e submetido a duas rodadas de
revisão estrutural por modelo externo (ETAPA 7.5), que identificaram e tiveram
corrigidos um header de OE ausente (OE 08), seis títulos de OE truncados e uma
divergência de contagem de indicadores (82 vs. 83) reconciliada pela
recategorização do bloco AT-001 como ação administrativa.

### Arquivos adicionados nesta versão
- `07-instrumentos-planejamento/PAS-SESDF-2026.md` — Programação Anual de Saúde
  2026 (88 páginas; 22 objetivos estratégicos, 82 indicadores do PDS, 8
  diretrizes com tabela orçamentária LOA, Anexos I e II)

### Arquivos atualizados nesta versão
- `README.md` — v1.0 → v1.1: árvore de estrutura com a nova categoria; total de
  documentos 28 → 29; nota sobre numeração de pastas
- `INDICE.md` — nova seção `07-instrumentos-planejamento/`; total de arquivos
  30 → 32; data de atualização

### Pendência registrada (SEV4 — sessão dedicada futura)

**Inconsistência de numeração de pastas.** Duas pastas compartilham o prefixo
`03`: `03-portarias-ministeriais` e `03-resolucoes-cfm`. A numeração sequencial
correta seria:

| Atual | Correto |
|---|---|
| `03-portarias-ministeriais` | `03-portarias-ministeriais` |
| `03-resolucoes-cfm` | `04-resolucoes-cfm` |
| `04-resolucoes-anvisa` | `05-resolucoes-anvisa` |
| `05-referencias-internacionais` | `06-referencias-internacionais` |

A nova categoria foi criada já com o número **`07`** (e não `06`) para reservar
a posição correta na sequência que resultará da renumeração — evitando acúmulo
de demanda quando a correção for executada. A correção em si (renomear três
pastas = mover 14 arquivos via API, com DELETE dos caminhos antigos) não foi
feita nesta sessão por ser cirurgia de repositório sem ganho funcional imediato
e por envolver operações de deleção fora do escopo do dia. **Severidade: SEV4.**

---

## v1.0 — 2026-06-02

**Tipo de alteração:** Criação
**Autorizado por:** victorarimatea
**Status:** em_execucao
**Exposição de motivos:** Criação do repositório D01 — primeiro repositório
do tipo Documento (D) no ecossistema DTD/SETIS/SES-DF. Consolida 28 documentos
transcritos ao longo das Fases 1 e 2 Tier 1 do Pipeline de Transcrição
Documental, produzidos em sessões no Cowork. A migração dos 28 arquivos .md
ocorrerá em etapa subsequente após a estrutura base estar estabelecida.

### Arquivos criados nesta versão
- `README.md` — ficha técnica e descrição do repositório
- `INDICE.md` — mapa completo dos 28 documentos e estrutura de subpastas
- `WORKFLOW-ESPECIFICACAO.md` — placeholder aguardando conteúdo real (v1.1)
- `backlog-versoes.md` — este arquivo
- Subpastas reservadas com `.gitkeep`:
  `01-legislacao-federal/`, `02-legislacao-distrital/`,
  `03-portarias-ministeriais/`, `03-resolucoes-cfm/`,
  `04-resolucoes-anvisa/`, `05-referencias-internacionais/`

### Pendências desta versão
- Upload dos 28 arquivos .md (aguarda Victor compartilhar os arquivos)
- Substituição do WORKFLOW-ESPECIFICACAO.md pelo conteúdo real

---
