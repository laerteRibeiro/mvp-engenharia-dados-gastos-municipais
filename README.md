# MVP - Gastos e Investimentos das Prefeituras Brasileiras (2025)

## 1. Contexto de Negócio e Perguntas de Investigação
Este projeto investiga como as prefeituras brasileiras alocam seus gastos entre diferentes áreas de atuação (Educação, Saúde, Administração, Previdência Social, entre outras), em relação à sua receita total, tomando como referência o exercício de 2025.

O objetivo é entender padrões regionais e por porte de município, respondendo às seguintes perguntas de investigação:

1. Como se distribui o gasto per capita entre as diferentes áreas (funções de despesa), e quais delas concentram a maior parte da receita municipal?
2. Como o gasto per capita por região se comporta ao comparar a média simples entre municípios e a média ponderada pela população — e por que essas duas visões podem divergir?
3. Como o gasto per capita varia entre municípios de diferentes portes populacionais, incluindo um recorte específico para as capitais?

Não foi realizada, neste MVP, uma comparação entre os rankings de gasto per capita e o PIB municipal, dada a defasagem estrutural de publicação desse indicador pelo IBGE (dados mais recentes disponíveis referem-se a 2023) e o tempo disponível para o desenvolvimento do trabalho.

## 2. Coleta de Dados
Os dados foram coletados de duas fontes públicas oficiais:

- **SICONFI (Tesouro Nacional)**: API REST (`apidatalake.tesouro.gov.br/ords/siconfi/tt/dca`), a partir da Declaração de Contas Anuais (DCA) de 2025. Foram utilizados o Anexo I-E (Despesas por Função de Governo, métrica "Despesas Liquidadas") e o Anexo I-C (Receitas Brutas Realizadas).
- **IBGE**: API de localidades (`servicodados.ibge.gov.br`) para mapeamento de município, UF e região; e estimativas populacionais 2025, para cálculo dos indicadores per capita.

**Metodologia de amostragem**: como o Brasil possui 5.571 municípios e cada um exige uma chamada individual à API do SICONFI (o parâmetro `id_ente` é obrigatório, não havendo endpoint de consulta em lote), optou-se por uma amostra estratificada por porte populacional (Pequeno, Médio, Grande, Metrópole) cruzada com região, garantindo a inclusão total das 27 capitais (26 estados + DF). A amostra final totalizou 486 municípios, dos quais 478 permaneceram após a exclusão de 8 municípios sem retorno de dados de receita (ver seção de Qualidade de Dados).

**Ambiente de execução**: a coleta foi originalmente executada em notebooks no Databricks Free Edition. Devido a uma restrição de acesso à internet imposta pela plataforma em determinado momento do desenvolvimento, uma parte da coleta precisou ser reexecutada em ambiente externo (Google Colab), com o resultado posteriormente ingerido de volta ao pipeline no Databricks — decisão registrada como parte da gestão de riscos de infraestrutura do projeto.

## 3. Modelagem e Catálogo de Dados

## 4. Pipeline de Dados (ETL)

## 5. Qualidade de Dados

## 6. Análise de Dados

## 7. Autoavaliação
