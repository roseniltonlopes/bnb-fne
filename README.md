# BNB | FNE Analytics
### Business Intelligence aplicado às operações de crédito do Banco do Nordeste

Projeto de **Business Intelligence e Análise de Dados** desenvolvido em dupla como parte da formação em Análise de Dados da Digital College, com foco na exploração de operações de crédito vinculadas ao Fundo Constitucional de Financiamento do Nordeste (FNE).

O projeto transforma dados de operações de crédito em informações analíticas para investigar a distribuição dos recursos, o perfil dos beneficiários, a capilaridade regional e a qualidade dos dados, utilizando modelagem dimensional, métricas DAX e dashboards interativos no Power BI.

---

## 🎯 Objetivo do projeto

Desenvolver uma solução analítica capaz de responder a perguntas relevantes sobre as operações de crédito:

- Como os recursos financeiros estão distribuídos entre pessoas físicas e jurídicas?
- Qual é a participação das operações realizadas no interior?
- Como os valores contratados evoluem ao longo do tempo?
- Quais diferenças existem entre as taxas médias simples e ponderadas?
- Existem inconsistências cadastrais ou divergências que precisam ser investigadas?
- Como os indicadores podem apoiar decisões relacionadas à governança e à distribuição regional do crédito?

A proposta vai além da visualização de indicadores: busca transformar dados em evidências para análise, investigação e proposição de melhorias.

## 📊 Dashboards

### 01. Dashboard Geral

Visão executiva das operações de crédito, com indicadores financeiros, operacionais e regionais.

Principais análises:
- Valor total contratado e quantidade de operações.
- Ticket médio das operações.
- Evolução temporal dos contratos e valores.
- Distribuição geográfica das operações.
- Comparação entre pessoas físicas (PF) e pessoas jurídicas (PJ).
- Perfil dos clientes e distribuição por gênero.
- Participação dos produtos e das linhas de financiamento do FNE.

### 02. Detalhe & Auditoria

Visão analítica voltada à investigação dos registros, das condições financeiras e da qualidade dos dados.

Principais análises:
- Taxas de juros, prazos e períodos de carência.
- Divergências entre identificadores de contratos e datas de contratação.
- Verificação de registros associados à linha FNE-Mulher.
- Consulta detalhada das operações.
- Identificação de situações que demandam validação.
- Recomendações para melhoria da governança de dados.

## 🔎 Principais insights identificados

Os indicadores preliminares do projeto apontaram os seguintes resultados, sujeitos à validação na versão final do relatório:

| Indicador | Resultado |
|---|---:|
| Valor contratado | R$ 2,03 bilhões |
| Quantidade de operações | 1.000 |
| Agências e cobertura geográfica | 50 agências em 10 UFs |
| Participação de PF no número de contratos | 68,5% |
| Participação de PJ no volume financeiro | 97,2% |
| Operações realizadas no interior | 81,2% |
| Taxa média ponderada | 8,68% a.a. |
| Taxa média simples | 7,27% a.a. |
| Registros sinalizados na auditoria do FNE-Mulher | 24 contratos |
| Valor associado aos registros sinalizados | R$ 2,01 milhões |
| Divergências entre o ano do identificador e a data de contratação | 746 contratos |

### O que esses números revelam?

**1. Quantidade de contratos não representa necessariamente volume financeiro**

A participação de PF no número de operações contrasta com a concentração do valor contratado em PJ. Essa diferença demonstra a importância de analisar simultaneamente volume financeiro e quantidade de beneficiários.

**2. A distribuição territorial merece uma análise multidimensional**

A participação das operações no interior permite investigar a capilaridade regional do crédito. Para avaliar o alcance dos recursos, é importante combinar esse indicador com valores contratados, perfil dos clientes e distribuição entre estados e regiões.

**3. A ponderação altera a interpretação das taxas**

A taxa média ponderada considera o peso financeiro das operações, enquanto a média simples considera as taxas individuais sem essa ponderação. A diferença entre os resultados reforça a importância de selecionar a métrica adequada para cada análise.

**4. Qualidade dos dados também é parte do negócio**

Os registros sinalizados na auditoria demonstram como regras de validação podem identificar situações que precisam ser investigadas. Uma sinalização não comprova, isoladamente, fraude ou irregularidade: os registros precisam ser confrontados com os critérios e documentos aplicáveis.

## 🛠️ Tecnologias e ferramentas

- **Power BI:** desenvolvimento dos dashboards e visualização dos indicadores.
- **DAX:** criação de medidas e métricas analíticas.
- **Power Query / Linguagem M:** preparação e transformação dos dados.
- **Modelagem dimensional:** organização do modelo em Star Schema.
- **PBIR (Power BI Enhanced Report Format):** estruturação das páginas, dos visuais e dos recursos do relatório.

## 🧱 Arquitetura de dados

O modelo semântico utiliza uma arquitetura Star Schema, separando a tabela de fatos das dimensões analíticas.

**Tabela fato**
- `fOperacoesCredito`: operações de crédito e informações relacionadas às contratações.

**Tabelas de dimensão**
- `dCalendario`: análises temporais.
- `dLocalidade`: informações geográficas e de agências.
- `dCliente`: perfil e características dos clientes.
- `dProdutoFNE`: produtos, fontes de financiamento e setores econômicos.
- `dFaixaTicket`: classificação das operações por faixa de valor.

**Camada de medidas**
- `_Medidas`: organização das métricas e dos cálculos DAX.

Essa estrutura facilita a análise por diferentes perspectivas, favorece a reutilização das medidas e melhora a organização do modelo semântico.

## ⚙️ Desafios técnicos

Durante o desenvolvimento, foram trabalhados aspectos importantes para a construção de uma solução de BI confiável:

- Organização de uma base originalmente estruturada em formato tabular.
- Padronização de dados e tratamento de questões relacionadas à cultura de formatação numérica.
- Construção de relacionamentos entre fatos e dimensões.
- Desenvolvimento de medidas financeiras e operacionais em DAX.
- Comparação entre métricas simples e ponderadas.
- Criação de regras para sinalização de divergências cadastrais.
- Organização das análises em páginas com objetivos distintos: visão executiva e auditoria.

## 💡 Recomendações propostas

A partir dos achados preliminares, o projeto apresenta três frentes de melhoria:

**1. Validação preventiva de regras de elegibilidade**

Avaliar controles preventivos para operações da linha FNE-Mulher, com revisão dos registros sinalizados e aplicação dos critérios oficiais de elegibilidade.

**2. Análise de oportunidades regionais**

Investigar diferenças de captação entre estados, considerando o perfil econômico, a demanda, a distribuição dos contratos e o potencial de financiamento.

**3. Fortalecimento da governança de dados**

Aprimorar a geração e a validação dos identificadores de contratos, além de estabelecer controles de consistência entre datas e códigos.

As recomendações são propostas analíticas e não representam ações já implementadas pelo Banco do Nordeste.

## 📈 Resultados esperados

- Maior clareza na interpretação dos indicadores de crédito.
- Análises integradas de volume financeiro, quantidade de operações e distribuição regional.
- Identificação de registros que demandam investigação.
- Melhor organização das métricas e dos relacionamentos do modelo semântico.
- Apoio à discussão de oportunidades de melhoria na qualidade e na governança dos dados.

## 👥 Desenvolvimento

Projeto acadêmico desenvolvido em dupla no contexto da formação em Análise de Dados da Digital College.

O trabalho integra modelagem de dados, transformação, construção de métricas, visualização analítica e interpretação de resultados.

## ⚠️ Observações

Este projeto tem finalidade educacional e analítica. Os resultados apresentados dependem da base utilizada, das regras de negócio implementadas e da validação das métricas no relatório final.

Os achados não constituem auditoria oficial, parecer institucional ou declaração de irregularidade por parte do Banco do Nordeste.

## 🚀 Próximos passos

- Validar os indicadores na versão final do dashboard.
- Refinar as regras de qualidade e auditoria.
- Ampliar as análises temporais e regionais.
- Documentar as medidas DAX e as regras de negócio.
- Evoluir a solução com novos indicadores e análises comparativas.

---

**BNB | FNE Analytics — Transformando dados de crédito em informação para análise e tomada de decisão.**
