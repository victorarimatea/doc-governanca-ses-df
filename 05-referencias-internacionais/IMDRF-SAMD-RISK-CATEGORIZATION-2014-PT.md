---
id_documento: IMDRF-SAMD-RISK-CATEGORIZATION-2014
titulo: "Software como Dispositivo Médico": Possível Estrutura para Categorização de Risco e Considerações Correspondentes
tipo_documental: Documento Técnico Final — International Medical Device Regulators Forum
instituicao_origem: International Medical Device Regulators Forum (IMDRF)
autor: IMDRF Software as a Medical Device (SaMD) Working Group
data_criacao: 2014-09-18
data_publicacao: 2014-09-18
idioma: Português (Brasil)
idioma_original: Inglês (EN)
versao_idioma: Tradução integral PT-BR
documento_par: IMDRF-SAMD-RISK-CATEGORIZATION-2014-EN.md
status_documental: Vigente
arquivo_original: IMDRF - SaMD - RISK CATEGORIZATION.pdf
fonte_externa: https://www.imdrf.org/sites/default/files/docs/imdrf/final/technical/imdrf-tech-140918-samd-framework-risk-categorization-141013.pdf
data_transcricao: 2026-05-31
versao_transcricao: 1.0
---

# Ficha Técnica Documental

| Campo | Valor |
|---|---|
| Título do Documento | "Software como Dispositivo Médico": Possível Estrutura para Categorização de Risco e Considerações Correspondentes |
| Tipo Documental | Documento Técnico Final — International Medical Device Regulators Forum |
| Instituição de Origem | International Medical Device Regulators Forum (IMDRF) |
| Autor(es) | IMDRF Software as a Medical Device (SaMD) Working Group |
| Data de Criação | 2014-09-18 |
| Data de Publicação | 2014-09-18 |
| Data de Transcrição | 2026-05-31 |
| Idioma desta versão | Português (Brasil) |
| Idioma original | Inglês (EN) |
| Versão do idioma | Tradução integral PT-BR |
| Documento par | IMDRF-SAMD-RISK-CATEGORIZATION-2014-EN.md |
| Número de Páginas | 30 |
| Nome do Arquivo Original | IMDRF - SaMD - RISK CATEGORIZATION.pdf |
| Link Externo de Acesso | https://www.imdrf.org/sites/default/files/docs/imdrf/final/technical/imdrf-tech-140918-samd-framework-risk-categorization-141013.pdf |
| Versão da Transcrição | 1.0 |

---

# Observações da Conversão

Tradução integral para o Português do Brasil do documento original em inglês IMDRF/SaMD WG/N12FINAL:2014. A tradução preserva a estrutura, numeração de seções, notas de rodapé e exemplos do documento original. Termos técnicos consolidados no campo regulatório de dispositivos médicos de software foram mantidos conforme o uso estabelecido pela ANVISA e pela literatura regulatória nacional. Documento complementar ao IMDRF/SaMD WG/N10FINAL:2013 (Definições-Chave). Diretamente referenciado pela RDC ANVISA nº 657/2022. Documento par em EN: IMDRF-SAMD-RISK-CATEGORIZATION-2014-EN.md.

---

# Conteúdo Integral Transcrito

IMDRF

International Medical Device Regulators Forum

Documento Final

"Software como Dispositivo Médico": Possível Estrutura para Categorização de Risco e Considerações Correspondentes

Título:

Grupo de Autoria: Grupo de Trabalho do IMDRF sobre Software como Dispositivo Médico (SaMD)

Data: 18 de setembro de 2014

Jeffrey Shuren, Presidente do IMDRF

Este documento foi produzido pelo International Medical Device Regulators Forum. Não há restrições à reprodução ou ao uso deste documento; no entanto, a incorporação deste documento, parcial ou integralmente, em outro documento, ou sua tradução para idiomas outros que não o inglês, não implica nem representa endosso de qualquer natureza por parte do International Medical Device Regulators Forum.

Copyright © 2014 pelo International Medical Device Regulators Forum.

Sumário

### 1.0 Introdução ........................................................................................................................ 4

### 2.0 Escopo.................................................................................................................................... 5

### 3.0 Definições ........................................................................................................................... 7

### 3.1 SOFTWARE COMO DISPOSITIVO MÉDICO ................................................................................... 7 3.2 USO PRETENDIDO / FINALIDADE PRETENDIDA ................................................................................. 7 3.3 FINALIDADE MÉDICA............................................................................................................ 7 3.4 ALTERAÇÕES EM SaMD ............................................................................................................... 9

### 4.0 Contexto do SaMD e Aspectos que Influenciam a Segurança do Paciente.......................................... 9

### 5.0 Fatores Importantes para a Caracterização do SaMD ............................................................ 10

### 5.1 SIGNIFICÂNCIA DA INFORMAÇÃO FORNECIDA PELO SaMD À DECISÃO CLÍNICA ......... 10 5.2 SITUAÇÃO OU CONDIÇÃO DE SAÚDE ........................................................................ 11

### 6.0 Declaração de Definição do SaMD ............................................................................................ 12

### 7.0 Categorização do SaMD ...................................................................................................... 13

### 7.1 PRINCÍPIOS DE CATEGORIZAÇÃO ........................................................................................ 13 7.2 CATEGORIAS DE SaMD ........................................................................................................ 14 7.3 CRITÉRIOS PARA DETERMINAÇÃO DA CATEGORIA DO SaMD ............................................................ 14 7.4 EXEMPLOS DE SaMD: ..................................................................................................... 15

### 8.0 Considerações Gerais para SaMD ................................................................................. 20

### 8.1 DESIGN E DESENVOLVIMENTO ............................................................................................ 20 8.2 ALTERAÇÕES ........................................................................................................................ 22

### 9.0 Considerações Específicas para SaMD ................................................................................. 23

### 9.1 CONSIDERAÇÕES SOBRE O AMBIENTE SOCIOTÉCNICO ...................................................... 23 9.2 CONSIDERAÇÕES SOBRE O AMBIENTE TECNOLÓGICO E DE SISTEMAS......................................... 25 9.3 SEGURANÇA DA INFORMAÇÃO COM RELAÇÃO ÀS CONSIDERAÇÕES DE SEGURANÇA ............................ 26

### 10.1 ESCLARECIMENTO DA DEFINIÇÃO DE SaMD ..................................................................................... 27 10.2 ANÁLISE DA ESTRUTURA DE SaMD COM AS CLASSIFICAÇÕES EXISTENTES ............................. 29

18 de setembro de 2014 Página 2 de 30

Prefácio

O documento aqui apresentado foi produzido pelo International Medical Device Regulators Forum (IMDRF), um grupo voluntário de reguladores mundiais de dispositivos médicos. O documento foi submetido a consulta ao longo de seu desenvolvimento.

Não há restrições à reprodução, distribuição ou uso deste documento; no entanto, a incorporação deste documento, parcial ou integralmente, em qualquer outro documento, ou sua tradução para idiomas outros que não o inglês, não implica nem representa endosso de qualquer natureza por parte do International Medical Device Regulators Forum.

18 de setembro de 2014 Página 3 de 30

### 1.0 Introdução

O software está desempenhando um papel cada vez mais importante e crítico na área da saúde, com muitas finalidades clínicas e administrativas. O software utilizado na saúde opera em um ambiente sociotécnico complexo — composto por software, hardware, redes e pessoas — e frequentemente integra sistemas maiores que devem operar de forma unificada. Esse software frequentemente depende de outros softwares comerciais prontos (COTS) e de outros sistemas e repositórios de dados como fonte de dados.

Um subconjunto do software utilizado na saúde atende à definição de dispositivo médico; em todo o mundo, as autoridades reguladoras regulamentam esse software de acordo.

As regulamentações existentes para software de dispositivos médicos estão em grande parte focadas em software de dispositivos médicos incorporado a dispositivos médicos dedicados de hardware, e se concentram em danos físicos, transmissão de energia e/ou substâncias de ou para o corpo, o grau de invasividade ao corpo, a proximidade a órgãos sensíveis, a duração do uso, as doenças, os processos e o risco para a saúde pública, a competência do usuário e o efeito sobre a população devido a doenças transmissíveis, etc.

Hoje, o software de dispositivos médicos muitas vezes é capaz de atingir seu propósito médico pretendido independentemente de dispositivos médicos de hardware. Está sendo cada vez mais implantado em hardware de propósito geral e entregue, em diversos ambientes de cuidado, em uma multiplicidade de plataformas tecnológicas (por exemplo, computadores pessoais, smartphones e na nuvem), de fácil acesso. Também está sendo cada vez mais interconectado a outros sistemas e conjuntos de dados (por exemplo, por meio de redes e pela Internet).

A complexidade do software de dispositivos médicos, combinada com a crescente conectividade dos sistemas, resulta em comportamentos emergentes normalmente não observados em dispositivos médicos de hardware.

Isso introduz desafios novos e únicos. Por exemplo:

• O software de dispositivos médicos pode se comportar de maneira diferente quando implantado em diferentes plataformas de hardware. • Muitas vezes, uma atualização disponibilizada pelo fabricante fica a cargo do usuário do software de dispositivo médico para instalação. • Devido à sua natureza não física (diferenciação-chave), o software de dispositivo médico pode ser duplicado em inúmeras cópias e amplamente distribuído, muitas vezes fora do controle do fabricante.

Além disso, existem aspectos do ciclo de vida do software de dispositivos médicos que apresentam desafios adicionais. Por exemplo, os fabricantes de software frequentemente:

• Possuem ciclos de desenvolvimento rápidos, • Introduzem alterações frequentes em seus softwares, e • Distribuem atualizações de forma massiva e rápida.

18 de setembro de 2014 Página 4 de 30

Este documento está focado em um subconjunto selecionado de software de dispositivos médicos. Esse software é denominado Software como Dispositivo Médico (SaMD) e está definido no IMDRF SaMD WG N10 / Software as a Medical Device: Key Definitions.

Definição: Software como Dispositivo Médico¹

SaMD é definido como software com a finalidade de ser utilizado para um ou mais propósitos médicos que realiza esses propósitos sem fazer parte de um dispositivo médico de hardware.

O objetivo deste documento é introduzir uma abordagem fundacional, um vocabulário harmonizado e considerações gerais e específicas para que fabricantes, reguladores e usuários possam abordar os desafios únicos associados ao uso do SaMD. A abordagem desenvolvida neste documento visa apenas estabelecer um entendimento comum sobre o SaMD e pode ser utilizada como referência. Este documento não pretende substituir ou modificar esquemas ou requisitos regulatórios de classificação existentes. São necessários esforços adicionais antes que esta abordagem fundacional possa ser utilizada para fins regulatórios.

### 2.0 Escopo

Finalidade do documento

O propósito do documento é introduzir uma abordagem fundacional, um vocabulário harmonizado e considerações gerais e específicas, para que fabricantes, reguladores e usuários possam abordar os desafios únicos associados ao uso do SaMD, por meio de:

• Estabelecimento de vocabulário comum e uma abordagem para categorizar o SaMD;

• Identificação de informações específicas para descrever o SaMD em termos da significância da informação fornecida pelo SaMD à decisão clínica, da situação ou condição de saúde e da funcionalidade central;

• Fornecimento de critérios para categorizar o SaMD com base na combinação da significância da informação fornecida pelo SaMD à decisão clínica e da situação ou condição de saúde associada ao SaMD; e

¹ Consulte a Seção 3.0 para a definição completa, incluindo notas.

18 de setembro de 2014 Página 5 de 30 • Identificação de considerações apropriadas, durante o processo do ciclo de vida (requisitos, design, desenvolvimento, testes, manutenção e uso) do SaMD.

Campo de aplicação • O sistema de categorização neste documento se aplica ao SaMD conforme definido no documento relacionado, IMDRF SaMD WG N10 / Software as a Medical Device: Key Definitions, e não abrange outros tipos de software.

• Software destinado como acessório a um dispositivo médico (ou seja, software que não tem em si mesmo uma finalidade médica) não está no escopo deste documento.

• Este documento se concentra no SaMD independentemente da tecnologia de software e/ou da plataforma (por exemplo, aplicativo móvel, nuvem, servidor).

• Este documento não aborda software que aciona ou controla um dispositivo médico de hardware.

Relação com outras classificações e normas regulatórias² • Este documento não pretende substituir nem criar novas práticas de gestão de riscos; ao contrário, utiliza princípios de gestão de riscos (por exemplo, princípios em normas internacionais) para identificar riscos genéricos para o SaMD.

• A estrutura de categorização neste documento não é uma classificação regulatória, nem implica uma convergência de regras de classificação. No entanto, define um caminho em direção a um vocabulário e uma abordagem comuns. Trabalho adicional é necessário para alinhar as regras de classificação existentes com essa estrutura.

• A estrutura de categorização não tem a intenção de substituir ou conflitar com o conteúdo e/ou desenvolvimento de normas técnicas ou de processo relacionadas às atividades de gestão de riscos de software.

² Detalhes adicionais podem ser encontrados no Apêndice 0.

18 de setembro de 2014 Página 6 de 30

### 3.0 Definições

### 3.1 Software como Dispositivo Médico

O termo "Software como Dispositivo Médico" (SaMD) é definido como software com a finalidade de ser utilizado para um ou mais propósitos médicos que realiza esses propósitos sem fazer parte de um dispositivo médico de hardware.

NOTAS:

• SaMD é um dispositivo médico e inclui dispositivo médico de diagnóstico in vitro (IVD). • SaMD é capaz de funcionar em plataformas computacionais de propósito geral (não médico).³ • "sem fazer parte de" significa software não necessário para que um dispositivo médico de hardware alcance seu propósito médico pretendido. • O software não atende à definição de SaMD se sua finalidade pretendida for acionar um dispositivo médico de hardware. • SaMD pode ser utilizado em combinação (por exemplo, como módulo) com outros produtos, incluindo dispositivos médicos. • SaMD pode ser interfaceado com outros dispositivos médicos, incluindo dispositivos médicos de hardware e outros softwares SaMD, bem como com software de propósito geral. • Aplicativos móveis que atendam à definição acima são considerados SaMD.

### 3.2 Uso Pretendido / Finalidade Pretendida

Para o uso pretendido do SaMD, aplica-se a definição do GHTF/SG1/N70:2011 "Label and Instructions for Use for Medical Devices":

O termo "uso pretendido / finalidade pretendida" é a intenção objetiva do fabricante quanto ao uso de um produto, processo ou serviço, conforme refletida nas especificações, instruções e informações fornecidas pelo fabricante.

### 3.3 Finalidade Médica

Os dois termos a seguir, conforme definidos no GHTF/SG1/N71:2012 "Definition of the Terms 'Medical Device' and 'In Vitro Diagnostic (IVD) Medical Device'" (em itálico abaixo), identificam a finalidade médica aplicável ao SaMD:

#### 3.3.1 Dispositivo Médico "Dispositivo médico" significa qualquer instrumento, aparelho, implemento, máquina, utensílio, implante, reagente para uso in vitro, software, material ou outro artigo similar ou relacionado, destinado pelo

³ "Plataformas computacionais" incluem recursos de hardware e software (por exemplo, sistema operacional, hardware de processamento, armazenamento, bibliotecas de software, telas, dispositivos de entrada, linguagens de programação etc.). Os "sistemas operacionais" que o SaMD requer podem ser executados em um servidor, uma estação de trabalho, uma plataforma móvel ou outra plataforma de hardware de propósito geral.

18 de setembro de 2014 Página 7 de 30 fabricante para ser utilizado, isoladamente ou em combinação, em seres humanos, para um ou mais dos seguintes propósitos médicos específicos:

• diagnóstico, prevenção, monitoramento, tratamento ou alívio de doenças, • diagnóstico, monitoramento, tratamento, alívio ou compensação de uma lesão, • investigação, substituição, modificação ou suporte da anatomia ou de um processo fisiológico, • suporte ou sustentação da vida, • controle da concepção, • desinfecção de dispositivos médicos, • fornecimento de informações por meio de exame in vitro de espécimes derivadas do corpo humano;

e não alcança sua ação primária pretendida por meios farmacológicos, imunológicos ou metabólicos, no ou sobre o corpo humano, mas que pode ser assistido em sua função pretendida por tais meios.

Nota: Produtos que podem ser considerados dispositivos médicos em algumas jurisdições, mas não em outras, incluem:

• substâncias de desinfecção, • auxílios para pessoas com deficiência, • dispositivos incorporando tecidos animais e/ou humanos, • dispositivos para fertilização in vitro ou tecnologias de reprodução assistida.

#### 3.3.2 Dispositivo Médico de Diagnóstico In Vitro (IVD) "Dispositivo médico de diagnóstico in vitro (IVD)" significa um dispositivo médico, utilizado isoladamente ou em combinação, destinado pelo fabricante para o exame in vitro de espécimes derivadas do corpo humano, exclusiva ou principalmente para fornecer informações para fins de diagnóstico, monitoramento ou compatibilidade.

Nota 1: Dispositivos médicos IVD incluem reagentes, calibradores, materiais de controle, recipientes para espécimes, software e instrumentos, aparelhos ou outros artigos relacionados, e são utilizados, por exemplo, para as seguintes finalidades de teste: diagnóstico, auxílio ao diagnóstico, triagem, monitoramento, predisposição, prognóstico, predição, determinação do estado fisiológico.

Nota 2: Em algumas jurisdições, certos dispositivos médicos IVD podem estar cobertos por outras regulamentações.

#### 3.3.3 Considerações adicionais para SaMD O SaMD também pode:

• Fornecer meios e sugestões para a mitigação de uma doença. • Fornecer informações para determinar compatibilidade, detectar, diagnosticar, monitorar ou tratar condições fisiológicas, estados de saúde, doenças ou malformações congênitas. • Auxiliar no diagnóstico, triagem, monitoramento, determinação de predisposição; prognóstico, predição, determinação do estado fisiológico.

18 de setembro de 2014 Página 8 de 30

### 3.4 Alterações em SaMD

As alterações em SaMD referem-se a quaisquer modificações realizadas ao longo do ciclo de vida do SaMD, incluindo a fase de manutenção.

A manutenção de software⁴ pode incluir manutenção adaptativa (por exemplo, acompanha o ambiente em constante mudança), perfectiva (por exemplo, recodificação para melhorar o desempenho do software), corretiva (por exemplo, corrige problemas descobertos) ou preventiva (por exemplo, corrige falhas latentes no produto de software antes que se tornem falhas operacionais).

Exemplos de alterações em SaMD incluem, mas não se limitam a, correções de defeitos; aprimoramentos estéticos, de desempenho ou de usabilidade; e correções de segurança.

### 4.0 Contexto do SaMD e Aspectos que Influenciam a Segurança do Paciente

Há muitos aspectos em um ambiente de uso clínico cada vez mais complexo que podem aumentar ou diminuir o potencial de criar situações de perigo para os pacientes. Alguns exemplos desses aspectos incluem:

• O tipo de doença ou condição • Fragilidade do paciente em relação à doença ou condição • Progressão da doença ou estágio da doença/condição • Usabilidade da aplicação • Desenvolvimento voltado para um tipo específico de usuário • Nível de dependência ou confiança do usuário nas informações de saída • Capacidade do usuário de detectar uma informação de saída incorreta • Transparência das entradas, saídas e métodos para o usuário • Nível de evidência clínica disponível e confiança nas evidências • O tipo de informação de saída e o nível de influência sobre a intervenção clínica • Complexidade do modelo clínico utilizado para derivar a informação de saída • Especificidade conhecida da informação de saída • Maturidade da base clínica do software e confiança na saída • Benefício da informação de saída versus linha de base

⁴ISO/IEC 14764:2006 Engenharia de Software — Processos do Ciclo de Vida do Software — Manutenção • manutenção adaptativa: a modificação de um produto de software, realizada após a entrega, para manter o produto de software utilizável em um ambiente alterado ou em alteração • manutenção perfectiva: a modificação de um produto de software após a entrega para detectar e corrigir falhas latentes no produto de software antes que se manifestem como falhas • manutenção corretiva: a modificação reativa de um produto de software realizada após a entrega para corrigir problemas descobertos • manutenção preventiva: a modificação de um produto de software após a entrega para detectar e corrigir falhas latentes no produto de software antes que se tornem falhas operacionais

18 de setembro de 2014 Página 9 de 30 • Características tecnológicas da plataforma em que o software se destina a operar • Método de distribuição do software

Embora muitos desses aspectos possam afetar a importância das informações de saída do SaMD, apenas alguns podem ser identificados pelo uso pretendido do SaMD. Em geral, esses aspectos podem ser agrupados nos dois fatores principais a seguir, que fornecem uma descrição adequada do uso pretendido do SaMD:

A. Significância da informação fornecida pelo SaMD à decisão clínica, e B. Estado da situação ou condição de saúde.

Quando esses fatores estão incluídos na descrição do uso pretendido pelo fabricante, eles podem ser utilizados para categorizar o SaMD. A Seção 6.0 fornece uma abordagem estruturada para uma declaração de definição do SaMD a fim de descrever o uso pretendido. A Seção 7.0 fornece um método para categorizar o SaMD com base nos fatores principais identificados na declaração de definição. Outros aspectos não incluídos nos dois fatores principais (por exemplo, transparência das entradas utilizadas, características tecnológicas utilizadas por um SaMD específico etc.), embora ainda importantes, não influenciam a determinação da categoria do SaMD. Esses outros aspectos influenciam a identificação de considerações exclusivas de uma abordagem/método específico utilizado pelo fabricante de uma determinada categoria de SaMD. Por exemplo, o tipo de plataforma, em constante mudança, utilizada na implementação do SaMD pode criar considerações exclusivas para essa implementação. Essas considerações também podem variar de acordo com as capacidades do fabricante ou com o rigor do processo utilizado para implementar o SaMD. Considerações adequadas desses aspectos por fabricantes, usuários e outras partes interessadas podem minimizar significativamente os riscos à segurança do paciente. A Seção 8.0 fornece considerações gerais e a Seção 9.0 fornece considerações específicas que, quando levadas em conta, podem promover a segurança na criação, implementação e uso do SaMD.

### 5.0 Fatores Importantes para a Caracterização do SaMD

### 5.1 Significância da informação fornecida pelo SaMD à decisão clínica

O uso pretendido das informações fornecidas pelo SaMD no gerenciamento clínico tem diferentes significâncias sobre a ação tomada pelo usuário.

#### 5.1.1 Para tratar ou diagnosticar Tratar e diagnosticar implica que as informações fornecidas pelo SaMD serão utilizadas para tomar uma ação imediata ou de curto prazo:

• Para tratar/prevenir ou mitigar, conectando-se a outros dispositivos médicos, produtos medicinais, atuadores de propósito geral ou outros meios de fornecer terapia ao corpo humano

18 de setembro de 2014 Página 10 de 30 • Para diagnosticar/rastrear/detectar uma doença ou condição (ou seja, utilizando sensores, dados ou outras informações de outros dispositivos de hardware ou software, relacionados a uma doença ou condição).

#### 5.1.2 Para orientar o gerenciamento clínico Orientar o gerenciamento clínico implica que as informações fornecidas pelo SaMD serão utilizadas para auxiliar no tratamento, auxiliar no diagnóstico, fazer triagem ou identificar sinais precoces de uma doença ou condição, e serão utilizadas para guiar as próximas intervenções diagnósticas ou terapêuticas:

• Para auxiliar no tratamento, fornecendo suporte aprimorado ao uso seguro e eficaz de produtos medicinais ou de um dispositivo médico.

• Para auxiliar no diagnóstico, analisando informações relevantes para ajudar a prever o risco de uma doença ou condição ou como auxílio para chegar a um diagnóstico definitivo.

• Para fazer triagem ou identificar sinais precoces de uma doença ou condição.

#### 5.1.3 Para informar o gerenciamento clínico Informar o gerenciamento clínico implica que as informações fornecidas pelo SaMD não desencadearão uma ação imediata ou de curto prazo:

• Para informar sobre opções de tratamento, diagnóstico, prevenção ou mitigação de uma doença ou condição.

• Para fornecer informações clínicas pela agregação de informações relevantes (por exemplo, doenças, condições, medicamentos, dispositivos médicos, populações etc.)

### 5.2 Situação ou Condição de Saúde

#### 5.2.1 Situação ou condição crítica Situações ou condições em que um diagnóstico preciso e/ou uma ação terapêutica oportuna são vitais para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde de um paciente individual, ou para mitigar o impacto sobre a saúde pública. O SaMD é considerado utilizado em uma situação ou condição crítica quando:

• O tipo de doença ou condição é: o Estado de saúde com risco de vida, incluindo estados incuráveis, o Requer intervenções terapêuticas maiores, o Às vezes é crítico em termos de tempo, dependendo da progressão da doença ou condição, o que pode afetar a capacidade do usuário de refletir sobre as informações de saída. • A população-alvo pretendida é frágil em relação à doença ou condição (por exemplo, pediatria, população de alto risco etc.) • Destinado a usuários especializados e treinados.

#### 5.2.2 Situação ou condição grave Situações ou condições em que um diagnóstico ou tratamento preciso é de vital importância para evitar intervenções desnecessárias (por exemplo, biópsia) ou em que intervenções oportunas são importantes para mitigar consequências irreversíveis de longo prazo sobre a condição de saúde de um paciente individual ou sobre a saúde pública. O SaMD é considerado utilizado em uma situação ou condição grave quando:

18 de setembro de 2014 Página 11 de 30 • O tipo de doença ou condição é: o Moderado em progressão, frequentemente curável, o Não requer intervenções terapêuticas maiores, o Normalmente não se espera que a intervenção seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde, o que proporciona ao usuário a capacidade de detectar recomendações incorretas. • A população-alvo pretendida NÃO é frágil em relação à doença ou condição. • Destinado a usuários especializados e treinados ou a leigos. Nota: O SaMD destinado a ser utilizado por leigos em uma "situação ou condição grave" conforme descrita aqui, sem o suporte de profissionais especializados, deve ser considerado como SaMD utilizado em uma "situação ou condição crítica".

#### 5.2.3 Situação ou condição não grave Situações ou condições em que um diagnóstico e tratamento precisos são importantes, mas não críticos para que as intervenções mitiguem consequências irreversíveis de longo prazo sobre a condição de saúde de um paciente individual ou sobre a saúde pública. O SaMD é considerado utilizado em uma situação ou condição não grave quando:

• O tipo de doença ou condição é: o De progressão lenta e previsível do estado da doença (pode incluir doenças ou estados crônicos menores), o Pode não ser curável; pode ser gerenciado de forma eficaz, o Requer apenas intervenções terapêuticas menores, e o As intervenções são normalmente não invasivas por natureza, proporcionando ao usuário a capacidade de detectar recomendações incorretas. • A população-alvo pretendida é formada por indivíduos que podem não ser sempre pacientes. • Destinado ao uso por usuários especializados e treinados ou por leigos.

### 6.0 Declaração de Definição do SaMD

O uso pretendido do SaMD é normalmente refletido em diversas fontes, tais como as especificações, instruções e outras informações fornecidas pelo fabricante. O propósito da declaração de definição do SaMD e dos componentes identificados abaixo é fornecer uma estrutura factual organizada. As declarações "A" e "B" visam ajudar o desenvolvedor do SaMD a determinar a categoria do SaMD na estrutura de categorização, enquanto a declaração "C" visa ajudar o fabricante a gerenciar alterações no SaMD que possam resultar em mudança de categoria e a abordar considerações específicas do SaMD. A declaração de definição do SaMD deve incluir uma declaração clara e sólida sobre o uso pretendido, incluindo o seguinte:

A. A "significância da informação fornecida pelo SaMD à decisão clínica", que identifica a finalidade médica pretendida do SaMD. A declaração

18 de setembro de 2014 Página 12 de 30 deve explicar como o SaMD atende a um ou mais dos propósitos descritos na definição de dispositivo médico⁵, por exemplo, fornecendo informações para diagnóstico, prevenção, monitoramento, tratamento etc. Esta declaração deve ser estruturada nos seguintes termos, conforme definido na Seção 5.1:

o Tratar ou diagnosticar o Orientar o gerenciamento clínico o Informar o gerenciamento clínico

B. O "estado da situação ou condição de saúde" para a qual o SaMD é destinado. Esta declaração deve ser estruturada nos seguintes termos, conforme definido na Seção 5.2:

o Situação ou condição crítica o Situação ou condição grave o Situação ou condição não grave

C. Descrição da funcionalidade central⁶ do SaMD, que identifica as características/funções críticas do SaMD que são essenciais para a significância pretendida da informação fornecida pelo SaMD à decisão clínica na situação ou condição de saúde pretendida. Esta descrição deve incluir apenas as características críticas. (Veja a aplicabilidade disso nas Seções 8.0 e 9.0.)

### 7.0 Categorização do SaMD

Esta seção fornece uma abordagem para categorizar o SaMD com base nos fatores identificados na declaração de definição do SaMD.

### 7.1 Princípios de Categorização

A seguir estão os princípios necessários e importantes na abordagem de categorização do SaMD.

• A categorização baseia-se em uma declaração de definição do SaMD precisa e completa.

• A determinação das categorias é a combinação da significância da informação fornecida pelo SaMD à decisão clínica e da situação ou condição de saúde.

• As quatro categorias (I, II, III, IV) são baseadas nos níveis de impacto no paciente ou na saúde pública, onde informações precisas fornecidas pelo SaMD para tratar ou diagnosticar, orientar ou informar o gerenciamento clínico são vitais para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde, mitigando a saúde pública.

• As categorias têm significância relativa entre si. A Categoria IV tem o maior nível de impacto; a Categoria I, o menor.

⁵ Definições-chave finais do IMDRF: "propósitos médicos" também repetidos aqui na Seção 3.3. ⁶ Estes podem incluir funcionalidades específicas críticas para manter o perfil de desempenho e segurança, atributos identificados pelo processo de gestão de riscos realizado pelo fabricante do SaMD.

18 de setembro de 2014 Página 13 de 30 • Quando a declaração de definição do SaMD de um fabricante indica que o SaMD pode ser utilizado em múltiplas situações ou condições de saúde, ele é categorizado na categoria mais alta de acordo com as informações incluídas na declaração de definição do SaMD.

• Quando um fabricante realiza alterações no SaMD⁷, durante o ciclo de vida, que resultam na mudança da declaração de definição, a categorização do SaMD deve ser reavaliada de forma adequada. O SaMD é categorizado de acordo com as informações incluídas na declaração de definição alterada (nova) do SaMD.

• O SaMD terá sua própria categoria de acordo com sua declaração de definição do SaMD mesmo quando um SaMD for interfaceado com outros SaMD, outros dispositivos médicos de hardware ou utilizado como módulo em um sistema maior.

### 7.2 Categorias de SaMD

Significância da informação fornecida pelo SaMD à decisão clínica — Tratar ou diagnosticar

Estado da situação ou condição de saúde

Orientar o gerenciamento clínico

Informar o gerenciamento clínico

| Situação/Condição | Tratar ou diagnosticar | Orientar gerenciamento clínico | Informar gerenciamento clínico |
|---|---|---|---|
| Crítica | IV | III | II |
| Grave | III | II | I |
| Não grave | II | I | I |

### 7.3 Critérios para Determinação da Categoria do SaMD

Critérios para a Categoria IV – i. O SaMD que fornece informações para tratar ou diagnosticar uma doença ou condição em uma situação ou condição crítica é uma Categoria IV e é considerado de impacto muito alto.

Critérios para a Categoria III – i. O SaMD que fornece informações para tratar ou diagnosticar uma doença ou condição em uma situação ou condição grave é uma Categoria III e é considerado de impacto alto.

ii. O SaMD que fornece informações para orientar o gerenciamento clínico de uma doença ou condição em uma situação ou condição crítica é uma Categoria III e é considerado de impacto alto.

Critérios para a Categoria II – i. O SaMD que fornece informações para tratar ou diagnosticar uma doença ou condição em uma situação ou condição não grave é uma Categoria II e é considerado de impacto médio.

⁷ "Alterações em SaMD" são definidas na Seção 3.4.

18 de setembro de 2014 Página 14 de 30 ii. O SaMD que fornece informações para orientar o gerenciamento clínico de uma doença ou condição em uma situação ou condição grave é uma Categoria II e é considerado de impacto médio.

iii. O SaMD que fornece informações para informar o gerenciamento clínico de uma doença ou condição em uma situação ou condição crítica é uma Categoria II e é considerado de impacto médio.

Critérios para a Categoria I – i. O SaMD que fornece informações para orientar o gerenciamento clínico de uma doença ou condição em uma situação ou condição não grave é uma Categoria I e é considerado de impacto baixo.

ii. O SaMD que fornece informações para informar o gerenciamento clínico de uma doença ou condição em uma situação ou condição grave é uma Categoria I e é considerado de impacto baixo.

iii. O SaMD que fornece informações para informar o gerenciamento clínico de uma doença ou condição em uma situação ou condição não grave é uma Categoria I e é considerado de impacto baixo.

### 7.4 Exemplos de SaMD:

Os exemplos abaixo têm a intenção de ilustrar a aplicação da estrutura e as categorias resultantes. Categoria IV:

• SaMD que realiza análise de imagem diagnóstica para tomada de decisões de tratamento em pacientes com acidente vascular cerebral (AVC) agudo, ou seja, onde a diferenciação rápida e precisa entre AVC isquêmico e hemorrágico é crucial para escolher a inicialização precoce da terapia trombolítica intravenosa que salva o cérebro ou a revascularização intervencionista.

Este exemplo utiliza o critério IV.i da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para tratar um paciente frágil em uma condição crítica que apresenta risco de vida, pode requerer intervenção terapêutica maior e é sensível ao tempo.

• SaMD que calcula a dimensão fractal de uma lesão e da pele circundante e constrói um mapa estrutural que revela os diferentes padrões de crescimento para fornecer diagnóstico ou identificar se a lesão é maligna ou benigna.

Este exemplo utiliza o critério IV.i da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para diagnosticar uma doença que pode apresentar risco de vida, pode requerer intervenção terapêutica maior e pode ser sensível ao tempo.

18 de setembro de 2014 Página 15 de 30 • SaMD que realiza análise de dados de espectroscopia do líquido cefalorraquidiano para diagnosticar meningite tuberculosa ou meningite viral em crianças.

Este exemplo utiliza o critério IV.i da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para diagnosticar uma doença em uma população frágil com possível impacto mais amplo na saúde pública, que pode apresentar risco de vida, pode requerer intervenção terapêutica maior e pode ser sensível ao tempo.

• SaMD que combina dados de imunoensaios para rastrear patógenos mutáveis/surtos pandêmicos que podem ser altamente transmissíveis por contato direto ou outros meios.

Este exemplo utiliza o critério IV.i da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para rastrear uma doença ou condição com impacto na saúde pública que pode apresentar risco de vida, pode requerer intervenção terapêutica e pode ser crítica em termos de tempo.

Categoria III:

• SaMD que utiliza o microfone de um dispositivo inteligente para detectar respiração interrompida durante o sono e emite um tom para despertar o dorminhoco.

Este exemplo utiliza o critério III.i da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para tratar uma condição em que normalmente não se espera que a intervenção seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD destinado a fornecer terapia sonora para tratar, mitigar ou reduzir os efeitos do zumbido, para o qual uma intervenção terapêutica menor é útil.

Este exemplo utiliza o critério III.i da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para tratar uma condição que pode ser moderada em progressão, pode não requerer intervenção terapêutica e cujo tratamento normalmente não se espera que seja crítico em termos de tempo.

• SaMD destinado como sistema de planejamento de tratamento por radiação como auxílio no tratamento, utilizando informações de um paciente e fornecendo parâmetros específicos adaptados a um tumor e paciente específicos para tratamento com um dispositivo médico de radiação.

Este exemplo utiliza o critério III.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas como auxílio no tratamento, fornecendo suporte aprimorado ao uso seguro e eficaz de um dispositivo médico a um paciente em condição crítica que pode apresentar risco de vida e requer intervenção terapêutica maior.

• SaMD que utiliza dados de indivíduos para prever pontuação de risco em população de alto risco para o desenvolvimento de estratégias de intervenção preventiva para câncer colorretal.

Este exemplo utiliza o critério III.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para detectar sinais precoces de uma doença para tratar uma condição que pode ser

18 de setembro de 2014 Página 16 de 30 uma doença com risco de vida que impacta populações de alto risco, pode requerer intervenção terapêutica e pode ser crítica em termos de tempo.

• SaMD utilizado para fornecer informações por meio de fotografias, monitoramento do crescimento ou outros dados para complementar outras informações que um profissional de saúde utiliza para diagnosticar se uma lesão cutânea é maligna ou benigna.

Este exemplo utiliza o critério III.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas como auxílio ao diagnóstico de uma condição que pode apresentar risco de vida, pode requerer intervenção terapêutica e pode ser crítica em termos de tempo, pela agregação de informações relevantes para detectar sinais precoces de uma doença.

Categoria II:

• SaMD que analisa dados de frequência cardíaca destinado a um clínico como auxílio no diagnóstico de arritmia.

Este exemplo utiliza os critérios de II.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para auxiliar no diagnóstico de uma doença de uma condição que pode ser moderada em progressão, pode não requerer intervenção terapêutica e cujo tratamento normalmente não se espera que seja crítico em termos de tempo.

• SaMD que interpola dados para fornecer reconstrução em 3D da imagem de tomografia computadorizada de um paciente, para auxiliar no posicionamento de cateteres por visualização do interior da árvore brônquica; no tecido pulmonar; e no posicionamento de marcadores no tecido pulmonar mole para guiar a radiocirurgia e a cirurgia torácica.

Este exemplo utiliza o critério II.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para auxiliar na próxima intervenção terapêutica de um paciente onde a intervenção normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD que utiliza dados de indivíduos para prever pontuação de risco de desenvolver acidente vascular cerebral ou doença cardíaca para criar estratégias de prevenção ou intervenção.

Este exemplo utiliza o critério II.iii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para detectar sinais precoces de uma doença para tratar uma condição que normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD que integra e analisa múltiplos testes utilizando regras padronizadas para fornecer recomendações de diagnóstico em determinadas indicações clínicas, por exemplo, função renal, risco cardíaco, avaliação de ferro e anemia.

Este exemplo utiliza o critério II.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para detectar sinais precoces de uma doença para tratar uma condição que normalmente

18 de setembro de 2014 Página 17 de 30 não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

Nota: Este exemplo inclui condições tanto graves quanto potencialmente não graves, mas de acordo com o princípio de categorização da Seção 7.1, quando a declaração de definição do SaMD de um fabricante indica que o SaMD pode ser utilizado em múltiplas situações ou condições de saúde, ele será categorizado na categoria mais alta de acordo com a declaração de definição do SaMD.

• SaMD que auxilia pacientes diabéticos calculando a dose de insulina em bolus com base na ingestão de carboidratos, glicemia pré-refeição e atividade física antecipada relatada para ajustar a razão de carboidratos e a insulina basal.

Este exemplo utiliza o critério II.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são utilizadas para auxiliar no tratamento de uma condição que normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

Categoria I:

• SaMD que envia frequência de ECG, velocidade de caminhada, frequência cardíaca, distância percorrida e localização de um paciente em reabilitação cardíaca baseada em exercícios para um servidor para monitoramento por um profissional qualificado.

Este exemplo utiliza o critério I.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer informações clínicas que não desencadearão uma ação imediata ou de curto prazo para o tratamento de uma condição de paciente que normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD que coleta dados de medidor de pico de fluxo e diários de sintomas para fornecer informações para antecipar a ocorrência de um episódio de asma.

Este exemplo utiliza o critério I.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer a melhor opção para mitigar uma condição que normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD que analisa imagens, movimentos dos olhos ou outras informações para orientar a próxima ação diagnóstica do astigmatismo.

Este exemplo utiliza o critério I.i da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer informações clínicas que não desencadearão uma ação imediata ou de curto prazo para o tratamento de uma condição de paciente que

18 de setembro de 2014 Página 18 de 30 mesmo que não seja curável pode ser gerenciada eficazmente e cujas intervenções são normalmente não invasivas por natureza.

• SaMD que utiliza dados de indivíduos para prever pontuação de risco (funcionalidade) em populações saudáveis para o desenvolvimento do risco (finalidade médica) de enxaqueca (condição não grave).

Este exemplo utiliza o critério I.i da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer informações clínicas que não desencadearão uma ação imediata ou de curto prazo para o tratamento de uma condição de paciente que mesmo que não seja curável pode ser gerenciada eficazmente e cujas intervenções são normalmente não invasivas por natureza.

• SaMD que coleta saída de um ventilador sobre o nível de dióxido de carbono de um paciente e transmite as informações para um repositório central de dados do paciente para consideração posterior.

Este exemplo utiliza o critério I.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer informações clínicas que não desencadearão uma ação imediata ou de curto prazo para o tratamento de uma condição de paciente que normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD que armazena informações históricas de pressão arterial para revisão posterior por um profissional de saúde.

Este exemplo utiliza o critério I.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer informações clínicas que não desencadearão uma ação imediata ou de curto prazo para o tratamento de uma condição de paciente que normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD destinado à análise de imagens de preparações de fluidos corporais ou lâminas digitais para realizar contagem de células e revisões de morfologia.

Este exemplo utiliza o critério I.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer informações clínicas que não desencadearão uma ação imediata ou de curto prazo para o tratamento de uma condição de paciente que normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD destinado ao uso por pacientes idosos com múltiplas condições crônicas que recebe dados de sensores de saúde vestíveis, transmite dados ao servidor de monitoramento e identifica informações de nível superior, como taquicardia e sinais de infecções respiratórias com base em conhecimento médico estabelecido, e comunica essas informações aos cuidadores.

Este exemplo utiliza o critério I.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer informações clínicas que não desencadearão uma ação imediata ou de curto prazo para o tratamento de uma condição de paciente que

18 de setembro de 2014 Página 19 de 30 normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

• SaMD que utiliza sensibilidade auditiva, fala em ruído e respostas a um questionário sobre situações comuns de escuta para autoavaliação de perda auditiva.

Este exemplo utiliza os critérios de I.ii da Seção 7.3, no sentido de que as informações fornecidas pelo SaMD acima são uma agregação de dados para fornecer informações clínicas que não desencadearão uma ação imediata ou de curto prazo para o tratamento de uma condição de paciente que normalmente não se espera que seja crítica em termos de tempo para evitar morte, incapacidade de longo prazo ou outra deterioração grave da saúde.

### 8.0 Considerações Gerais para SaMD

O SaMD frequentemente integra uma sequência de fluxo de trabalho clínico com a finalidade de melhorar o diagnóstico, o tratamento e o gerenciamento do paciente. No entanto, problemas com o design e/ou a implementação do SaMD em um fluxo de trabalho podem levar os usuários a fazer escolhas/decisões incorretas e podem causar atrasos nas decisões — o que pode trazer consequências adversas para os pacientes.

O desenvolvimento de SaMD seguros implica identificar riscos e estabelecer medidas que deem confiança de que os riscos são aceitáveis. É geralmente aceito que o teste de software não é suficiente para determinar que ele é seguro em operação. Como consequência, reconhece-se que a confiança deve ser incorporada ao software a fim de assegurar sua segurança.

A IEC 62304 é uma norma para o desenvolvimento do ciclo de vida de software de dispositivos médicos. A norma especifica um modelo de decisão baseado em risco, define alguns requisitos de testes e destaca três princípios principais que promovem a segurança relevante para o SaMD:

• Gestão de riscos; • Gestão da qualidade; e • Engenharia de sistemas metódica e sistemática de acordo com as melhores práticas do setor.

A combinação desses conceitos permite que os fabricantes de SaMD sigam um processo de tomada de decisão claramente estruturado e consistentemente repetível para promover a segurança do SaMD.

Informações adicionais sobre esses princípios principais são fornecidas abaixo, seguidas de discussão sobre algumas considerações específicas nas áreas de:

• Ambiente sociotécnico • Ambientes tecnológicos e de sistemas • Segurança da informação com relação à segurança

### 8.1 Design e Desenvolvimento

Os fabricantes devem selecionar e implementar um processo adequado para o planejamento, design, desenvolvimento, implantação e documentação de software robusto e confiável, proporcional

18 de setembro de 2014 Página 20 de 30 ao risco — conforme informado por sua finalidade pretendida, uso razoavelmente previsível e o ambiente sociotécnico de uso compreendido e definido.

A segurança precisa ser abordada no início do processo de design e desenvolvimento.

O desenvolvimento de software de forma assegurada pela qualidade deve considerar a seleção e implementação adequadas de métodos de design e desenvolvimento de sistemas que:

• Incluam um processo de desenvolvimento metódico e sistemático utilizando modelos, métodos, arquitetura e técnicas de modelagem de design adequados para a(s) linguagem(ns) de desenvolvimento e a finalidade pretendida do dispositivo, • Abranjam as diversas fases do ciclo de vida do software por meio da aplicação de normas de desenvolvimento de software, por exemplo, IEC 62304, e do uso de guias de engenharia de software, por exemplo, guia SWEBoK, guia SEBoK, e • Documentem de forma sistemática e metódica o processo de design e desenvolvimento (utilizando ferramentas quando adequado).

#### 8.1.1 Vigilância Pós-Mercado Os riscos do software nunca podem ser totalmente eliminados; portanto, os fabricantes de SaMD devem monitorar continuamente os problemas dos clientes para manter o nível de segurança. Um processo de monitoramento deve incluir formas de capturar o feedback dos clientes, por exemplo, por meio de consultas, reclamações, estudos de mercado, grupos focais, serviços etc. A natureza inerente do software, incluindo o SaMD, permite métodos eficientes para compreender e capturar as experiências dos usuários. Recomenda-se que os fabricantes de SaMD utilizem essas técnicas de feedback para compreender os modos de falha e realizar análises para abordar situações de segurança. Também se recomenda que os fabricantes de SaMD ampliem seu monitoramento para detectar automaticamente erros do software ou do sistema, ou seja, descobrir e se recuperar de um erro antes que uma falha possa ocorrer.

As considerações gerais associadas ao monitoramento do SaMD incluem:

## 1. Devido à sua natureza não física, um SaMD pode ser duplicado e inúmeras cópias podem ser amplamente distribuídas, muitas vezes fora do controle do fabricante.

## 2. Muitas vezes, uma atualização disponibilizada pelo fabricante fica a cargo do usuário do SaMD para instalação. Os fabricantes devem garantir que as mitigações adequadas abordem quaisquer riscos decorrentes da existência de diferentes versões do SaMD no mercado.

18 de setembro de 2014 Página 21 de 30

## 3. As investigações de incidentes devem considerar qualquer caso específico ou combinação de casos de uso que possam ter contribuído para a falha e, conforme apropriado, os fabricantes devem considerar princípios de reconstituição de acidentes, por exemplo, registro de dados, gravador de caixa preta etc.⁸

### 8.2 Alterações

Espera-se que os fabricantes de SaMD tenham um nível adequado de controle para gerenciar as alterações. Devido à natureza não física do software, um processo de gerenciamento de alterações de software precisa de considerações específicas para alcançar o resultado pretendido em relação à rastreabilidade e à documentação.

Essas considerações específicas incluem:

• Considerações sobre o ambiente sociotécnico • Considerações sobre o ambiente tecnológico e de sistemas • Considerações de segurança da informação com relação à segurança

As alterações no SaMD podem ter um efeito significativo e imprevisível na situação ou condição de saúde e no ambiente sociotécnico de uso, se não gerenciadas sistematicamente, não apenas em relação a uma alteração de design em si, mas também ao impacto do software alterado após sua instalação e implementação.

Em qualquer ciclo de vida de produto, a mudança é inevitável. Falhas ocorrem e podem ser decorrentes de erros, ambiguidades, omissões ou interpretação incorreta da especificação que o software pretende satisfazer, descuido ou incompetência na escrita do código, testes inadequados, uso incorreto ou inesperado do software ou outros problemas imprevistos. Um SaMD também pode falhar com alterações no ambiente de execução. Alterações no SaMD ou em seu ambiente operacional podem afetar sua segurança, qualidade e desempenho.

As alterações no SaMD referem-se a quaisquer modificações realizadas ao longo do ciclo de vida do SaMD, incluindo a fase de manutenção. A natureza das alterações de manutenção de software pode incluir adaptativas (por exemplo, acompanha o ambiente em constante mudança), perfectivas (por exemplo, recodificação para melhorar o desempenho do software), corretivas (por exemplo, corrige problemas descobertos) ou preventivas (por exemplo, corrige falhas latentes no produto de software antes que se tornem falhas operacionais). Essas alterações devem ser claramente identificadas e definidas com um método de rastreamento da alteração ao software específico afetado.

A fim de gerenciar efetivamente as alterações e seu impacto, os fabricantes devem realizar uma avaliação de risco para determinar se a(s) alteração(ões) afeta(m) a categorização do SaMD e a funcionalidade central do SaMD conforme descrito na declaração de definição.

⁸ Leveson, N. 2012. Engineering a Safer World: Systems Thinking Applied to Safety. Cambridge, MA, EUA: MIT Press.

18 de setembro de 2014 Página 22 de 30

As alterações devem passar por verificação e validação adequadas antes de serem liberadas pelo fabricante para uso.

Exemplos de alterações de software (algumas podem ser consideradas significativas e outras não):

• Modificação em um algoritmo que afeta o diagnóstico ou a terapia administrada;

• Uma alteração de software que afeta a forma como os dados são lidos ou interpretados pelo usuário, de modo que o tratamento ou diagnóstico do paciente pode ser alterado em comparação com a versão anterior do software;

• Adição de um novo recurso ao software que pode alterar o diagnóstico ou a terapia administrada ao paciente;

• Uma alteração de software que incorpora uma alteração no sistema operacional ou alteração na configuração na qual o SaMD é executado;

• Uma alteração de software que afeta o fluxo de trabalho clínico.

### 9.0 Considerações Específicas para SaMD

### 9.1 Considerações sobre o Ambiente Sociotécnico

O termo ambiente sociotécnico diz respeito ao contexto de uso do SaMD — frequentemente composto por hardware, redes, software e pessoas. De forma mais formal, pode ser caracterizado em componentes espaciais (por exemplo, localização), de atividade (por exemplo, fluxo de trabalho), sociais (por exemplo, responsabilidade), tecnológicos (por exemplo, dispositivos, sistemas, fontes de dados e conexões) e físicos (por exemplo, condições ambientes)⁹.

O SaMD fornece informações e/ou uma estrutura para informações.

O funcionamento adequado e seguro do SaMD é altamente dependente de uma compreensão suficiente e comum do ambiente sociotécnico que inclui o fabricante e o usuário.

Os fabricantes devem estar cientes do ambiente sociotécnico, onde considerações inadequadas podem levar a diagnósticos e tratamentos incorretos, imprecisos e/ou tardios;

⁹ (Adaptado da IEC 62366)

18 de setembro de 2014 Página 23 de 30 e/ou carga cognitiva adicional (que pode, ao longo do tempo, tornar os clínicos mais suscetíveis a cometer erros)¹⁰.

Da mesma forma, os usuários também devem estar cientes do ambiente sociotécnico conforme presumido e projetado (limitações das capacidades do SaMD) e pelo fabricante, pois a falta de consciência pode levar à dependência excessiva ou a outro uso impreciso do SaMD.

Por exemplo:

- Se o usuário não tiver habilidades e conhecimentos suficientes para a operação correta do SaMD, possíveis dados de saída imprecisos podem não ser questionados. O mesmo pode ocorrer se o usuário se habituar e se tornar excessivamente dependente do SaMD ao longo do tempo. - A introdução do SaMD às vezes altera os fluxos de trabalho clínicos de maneiras imprevistas; essas alterações podem ser prejudiciais à segurança do paciente. - O usuário pode buscar caminhos alternativos para atingir uma funcionalidade específica, também chamados de contornos (workarounds). Quando os contornos contornam os recursos de segurança integrados de um produto, a segurança do paciente pode ser comprometida.

Considerações para o fabricante ao identificar efeitos/implicações e medidas adequadas para a segurança e o desempenho do SaMD ao longo do design, desenvolvimento e instalação do produto:

• A transparência das informações sobre as limitações com algoritmos, modelos clínicos, qualidade dos dados utilizados para construir os modelos, suposições feitas etc. pode ajudar os usuários a questionar a validade da saída do SaMD e evitar decisões incorretas ou inadequadas;

• A integração do SaMD nos fluxos de trabalho clínicos do mundo real (incluindo envolvimento suficiente de usuários de todas as disciplinas relevantes) requer atenção ao uso in situ e às tarefas para garantir o uso adequado dos recursos de segurança; • O SaMD (e outros sistemas conectados ao SaMD) pode ser configurado pelo usuário de formas diferentes das pretendidas ou previstas pelo fabricante;

• Embora não seja específico do SaMD, o design da interface do usuário inclui: se os designs são excessivamente complexos (por exemplo, múltiplas telas complicadas), a adequação dos designs à plataforma de destino (por exemplo, tela de smartphone versus monitor de desktop), a natureza dinâmica dos dados (por exemplo, exibir informações no momento adequado e por uma duração adequada);

¹⁰ Leveson, N. 2012. Engineering a Safer World: Systems Thinking Applied to Safety. Cambridge, MA, EUA: MIT Press.

18 de setembro de 2014 Página 24 de 30 • Embora não seja específico do SaMD, a identificação de meios adequados para exibir informações de forma que sejam compreendidas pelo usuário pretendido (por exemplo, usabilidade, incluindo parâmetros de regionalização, tradução de idioma e seleção/exibição de unidades);

• Comunicação de informações relevantes ao usuário (com base nas atividades realizadas acima) com o propósito de:

o Possibilitar ao usuário decidir se pode ou não usar o dispositivo na organização em termos de hardware disponível, competência, rede, qualidade necessária para entrada de dados. E, caso ele/ela decida fazê-lo, informações necessárias para tomar essas medidas a fim de utilizá-lo: informar os usuários, estabelecer rotinas diferentes, obter o hardware necessário.

o Possibilitar a instalação e configuração corretas do SaMD para integração adequada com os fluxos de trabalho clínicos.

### 9.2 Considerações sobre o Ambiente Tecnológico e de Sistemas

O ambiente tecnológico e de sistemas refere-se ao ecossistema onde o SaMD reside, incluindo sistemas instalados, interconexões e plataforma(s) de hardware. Instruções sobre como verificar a adequação da instalação e da atualização do SaMD, bem como quaisquer alterações feitas no ambiente do sistema (por exemplo, hardware e software), devem ser fornecidas ao usuário. A dependência de hardware sobre o qual o fabricante não tem controle (sistemas operacionais não projetados para fins médicos, hardware de propósito geral, redes e servidores, Internet, links) deve ser considerada e abordada pelo fabricante durante o design e o desenvolvimento do SaMD (por exemplo, projetando designs de SaMD robustos e resilientes).

Os SaMDs são sempre dependentes de uma plataforma de hardware e frequentemente de um ambiente conectado. O SaMD pode ser afetado por interconexões de ligação cruzada — tanto conexões físicas quanto interoperabilidade, ou seja, a comunicação contínua entre dispositivos, tecnologia e pessoas.

A interrupção no ecossistema (por exemplo, resultante de interrupções de serviço, manutenção ou atualizações de sistemas, falhas de plataforma) pode resultar em perda de informações, informações atrasadas, corrompidas ou misturadas do paciente, ou informações imprecisas que podem levar a diagnósticos e/ou tratamentos incorretos ou imprecisos. Por exemplo: um diagnóstico incorreto é feito após a conexão com um conjunto de dados clínicos ter sido perdida porque os dados de diagnóstico do paciente não estão disponíveis.

Considerações para o fabricante ao identificar efeitos/implicações para a segurança e o desempenho do SaMD:

• Conexões com outros sistemas (por exemplo, confiabilidade da conexão, resiliência, qualidade do serviço, acesso, segurança, capacidade de carga das conexões com outros sistemas e métodos de conexão, integração do sistema)

18 de setembro de 2014 Página 25 de 30 • Apresentação de informações aos usuários e integradores de sistemas sobre os requisitos do sistema e o desempenho resultante do SaMD (por exemplo, o efeito que as alterações nas regras de firewall podem ter na operação do sistema) • Plataforma(s) de hardware — como smartphones, PCs, servidores — (por exemplo, confiabilidade, dependências e interconexões com outros hardwares e softwares); • Compatibilidade de plataforma de sistema operacional — como Windows, GNU/Linux; e • Modificações e alterações na integração do SaMD (por exemplo, atualizações de plataforma) podem ter efeitos no SaMD que o fabricante não antecipou/previu.

### 9.3 Segurança da Informação com Relação às Considerações de Segurança

A segurança da informação pode ser definida como a preservação da confidencialidade, integridade e disponibilidade da informação¹¹.

O gerenciamento ou a transmissão incorretos de informações por um SaMD pode levar a diagnósticos ou tratamentos incorretos ou tardios.

O SaMD pode ser afetado por fatores específicos relacionados à segurança da informação que podem afetar a integridade, disponibilidade ou acessibilidade das informações de saída do SaMD necessárias para o diagnóstico ou tratamento correto:

• Os SaMDs são tipicamente utilizados por uma variedade de usuários com diferentes necessidades de acesso, por exemplo, acesso restrito ou requisitos variados de segurança da informação • As plataformas onde um SaMD está instalado tipicamente executam muitos outros aplicativos de software.

• Os SaMDs são tipicamente conectados à Internet, redes, bancos de dados ou servidores com requisitos variados de segurança da informação.

Considerações para o fabricante ao identificar implicações para a segurança e o desempenho do SaMD:

• Os requisitos de controle de segurança da informação e privacidade do SaMD podem precisar ser equilibrados com a necessidade de disponibilidade oportuna de informações.

¹¹ (Da ISO/IEC 27000:2009 - Tecnologia da informação — Técnicas de segurança — Sistemas de gestão de segurança da informação — Visão geral e vocabulário)

18 de setembro de 2014 Página 26 de 30 • A segurança da informação requer a identificação e implementação de formas seguras (e formalizadas) para armazenar, converter e/ou transmitir dados.

• O design deve usar medidas de controle adequadas para abordar a integridade dos dados quando informações comuns são acessadas por múltiplas aplicações e usuários.

• Os fabricantes devem tornar viável para os usuários a implementação segura de atualizações de segurança da informação.

• A proteção de informações sensíveis requer suporte para controle de acesso suficiente e restrição adequada às configurações do sistema e aos ativos para dados importantes.

• O design deve abordar possíveis interações adversas do sistema com a inclusão de medidas adequadas de resiliência e robustez.

• As instruções para os usuários relacionadas à segurança da informação devem incluir como realizar com segurança:

o A instalação do SaMD em ambientes operacionais adequados (por exemplo, sistema operacional, integração de outros softwares);

o O gerenciamento de mecanismos de autenticação; e o A atualização de software de segurança/spyware, ambientes operacionais e outros sistemas e aplicativos etc.

### 10.0 Apêndice

### 10.1 Esclarecimento da Definição de SaMD

Este Apêndice fornece uma lista representativa de recursos e funcionalidades que atendem ou não atendem à definição de SaMD. Esta lista não é exaustiva; destina-se apenas a fornecer clareza e assistência para identificar quando um recurso ou funcionalidade é considerado SaMD.

Exemplos de software que são SaMD:

• Software com finalidade médica que opera em uma plataforma computacional de propósito geral, ou seja, uma plataforma computacional que não tem finalidade médica, é considerado SaMD. Por exemplo, software destinado ao diagnóstico de uma condição utilizando o acelerômetro triaxial que opera no processador integrado de uma câmera digital de consumo é considerado SaMD.

• Software que está conectado a um dispositivo médico de hardware, mas não é necessário para que esse dispositivo médico de hardware alcance sua finalidade médica pretendida, é SaMD e não um acessório do dispositivo médico de hardware. Por exemplo, software que permite a um smartphone comercialmente disponível visualizar imagens para fins de diagnóstico obtidas de um dispositivo médico de ressonância magnética (RM) é SaMD e não um acessório do dispositivo médico de RM.

18 de setembro de 2014 Página 27 de 30 • As notas da definição de SaMD indicam que "o SaMD é capaz de funcionar em plataformas computacionais de propósito geral (não médico)". O SaMD em execução nessas plataformas computacionais de propósito geral pode estar localizado em um dispositivo médico de hardware. Por exemplo, software que realiza pós-processamento de imagens com a finalidade de auxiliar na detecção de câncer de mama (software CAD — detecção auxiliada por computador) em execução em uma plataforma computacional de propósito geral localizada no dispositivo médico de hardware de aquisição de imagem é SaMD.

• As notas da definição de SaMD indicam que "o SaMD pode ser interfaceado com outros dispositivos médicos, incluindo dispositivos médicos de hardware e outros softwares SaMD, bem como com software de propósito geral". Software que fornece parâmetros que se tornam a entrada para um dispositivo médico de hardware diferente ou outro SaMD é SaMD. Por exemplo, software de planejamento de tratamento que fornece informações utilizadas em um acelerador linear é SaMD.

Exemplos de software que não são SaMD:

• A definição de SaMD indica que "SaMD é definido como software com a finalidade de ser utilizado para um ou mais propósitos médicos que realiza esses propósitos sem fazer parte de um dispositivo médico de hardware". Exemplos de software considerados "parte de" incluem software utilizado para "acionar ou controlar" os motores e o bombeamento de medicação em uma bomba de infusão; ou software utilizado no controle em malha fechada em um marca-passo implantável ou outros tipos de dispositivos médicos de hardware. Esses tipos de software, às vezes denominados "software embarcado", "firmware" ou "microcódigo", não são SaMD.

• Software exigido por um dispositivo médico de hardware para realizar o uso pretendido do dispositivo médico de hardware não é SaMD, mesmo que/quando vendido separadamente do dispositivo médico de hardware.

• Software que depende de dados de um dispositivo médico, mas não tem finalidade médica, por exemplo, software que criptografa dados para transmissão de um dispositivo médico, não é SaMD.

• Software que possibilita comunicação e fluxo de trabalho clínico, incluindo registro de pacientes, agendamento de consultas, chamadas de voz, videochamadas, não é SaMD.

• Software que monitora o desempenho ou o funcionamento adequado de um dispositivo com a finalidade de fazer a manutenção do dispositivo, por exemplo, software que monitora o desempenho do tubo de raios X para antecipar a necessidade de substituição; ou software que integra e analisa dados de controle de qualidade laboratorial para identificar erros aleatórios aumentados ou tendências de calibração em IVDs, não é SaMD.

• Software que fornece parâmetros que se tornam a entrada para SaMD não é SaMD se não tiver finalidade médica. Por exemplo, um banco de dados incluindo funções de busca e consulta por si só ou quando utilizado pelo SaMD não é SaMD.

18 de setembro de 2014 Página 28 de 30

### 10.2 Análise da Estrutura de SaMD com as Classificações Existentes

Este Anexo tem a intenção de esclarecer o seguinte:

A – Categorização de SaMD em relação à classificação de dispositivos médicos

Existem diferentes esquemas de classificação para diferentes finalidades.

Tipicamente, a classificação é baseada em um conjunto de parâmetros/perguntas que atribui o objeto de interesse a grupos que servem a um determinado propósito.

As classificações podem ter a finalidade de determinar, por exemplo: • Níveis adequados de supervisão regulatória, como requisitos para o Níveis de intervenção de terceiros o Níveis de controles de conformidade o Níveis de sistema de qualidade • Níveis adequados de medidas técnicas, por exemplo o Meios técnicos de proteção, por exemplo para

 Proteção a laser 1, 2 ou 3  Isolamento elétrico, aterramento de proteção ou duplo isolamento  Penetração de líquidos, IP XX

A classificação de dispositivos médicos está comumente focada em controles regulatórios baseados em classes de risco.

A categorização para SaMD, como no caso da proteção a laser, apenas identifica diferentes categorias de SaMD por nível de impacto. A categorização neste documento, por si só, não implica controles regulatórios necessários para gerenciar riscos. Destina-se apenas a fornecer orientação para considerações adequadas para SaMD.

B - Relação entre este documento e os documentos do GHTF.

É importante observar o seguinte para compreender a relação entre a estrutura de categorização deste documento e os princípios de classificação para dispositivos médicos e dispositivos médicos de diagnóstico in vitro:

• Os princípios de classificação do GHTF, ao contrário deste documento, foram destinados a construir regras de classificação para fins de controle regulatório. Conforme explicado anteriormente, este documento identifica diferentes categorias de SaMD por nível de impacto e não aborda as classes de risco regulatório correspondentes identificadas nos documentos do GHTF. • Os princípios de alto nível utilizados para identificar as categorias de SaMD baseiam-se substancialmente nos princípios (fundamentos) subjacentes às regras de classificação estabelecidas nos documentos de princípios de classificação do GHTF. Fatores-chave como riscos individuais, riscos à saúde pública, habilidades dos usuários e importância das informações fornecidas são comuns a ambas as estruturas.

18 de setembro de 2014 Página 29 de 30

### 11.0 Referências

IMDRF SaMD WG N10 / Software as a Medical Device: Key Definitions

GHTF/SG1/N70:2011 "Label and Instructions for Use for Medical Devices"

GHTF/SG1/N71:2012 "Definition of the Terms 'Medical Device' and 'In Vitro Diagnostic (IVD) Medical Device'"

IEC 62304:2006 - Medical device software -- Software life cycle processes

ISO/IEC 14764:2006 Software Engineering — Software Life Cycle Processes — Maintenance

Guide to the Software Engineering Body of Knowledge - SWEBOK (2004), pp. 1-202 por Alain Abran, Pierre Bourque, Robert Dupuis, James W. Moore, Leonard L. Tripp, editado por Alain Abran, Pierre Bourque, Robert Dupuis, James W. Moore, Leonard L. Tripp

[SEBoK] Guide to the Systems Engineering Body of Knowledge (http://www.sebokwiki.org/)

ISO/IEC 27000:2009 - Tecnologia da informação — Técnicas de segurança — Sistemas de gestão de segurança da informação

IEC 62366:2007 Dispositivos médicos — Aplicação de engenharia de usabilidade a dispositivos médicos

Leveson, N. 'Engineering a Safer World: Systems Thinking Applied to Safety, MIT, EUA (2011)

18 de setembro de 2014 Página 30 de 30

---

# Controle de Integridade

## Resultado da Conversão

- Total de páginas identificadas: 30
- Total de páginas processadas: 30
- OCR utilizado: Não
- Falhas de leitura: Não
- Conteúdo parcialmente recuperado: Não

## Status da Conversão

**Tradução Integral PT-BR — Conversão Completa**
