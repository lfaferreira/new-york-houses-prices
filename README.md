# new-york-houses-prices
O projeto atual tem como objetivo a resolução do case de pré-seleção para a posição de ciência de dados na Indicium, referente ao ano de 2024. Ele consiste em um problema de previsão relacionado aos preços de aluguel de casas em Nova York. Uma empresa expressou interesse em analisar as projeções futuras dos preços de aluguel de casas e contratou nossa consultoria para fornecer suporte nesse aspecto.

![vist Card](https://cdn.discordapp.com/attachments/1204200810813329468/1204200844510371880/47bce2e842d48c6469583cea1bcf0002.jpg?ex=65d3de6e&is=65c1696e&hm=d4e9765aa9f4796fccdacd35f56230ce5e03dc688eae2a0c208b43a4809c14d1&)


## Índice

- [1. Proposta de Negócios](#1-proposta-de-negócios)

- [2. Compreensão dos Dados](#2-compreensão-dos-dados)

- [3. Plano de Ação](#3-plano-de-ação)

- [4. Insights Extraídos](#4-insights-extraídos)

- [5. Modelos de Machine Learning e métricas de avaliação](#5-modelos-de-machine-learning-e-métricas-de-avaliação)

- [6. Resultados de Negócios](#6-resultados-de-negócios)

- [7. Trabalho Futuro](#7-trabalho-futuro)


## 1. Proposta de Negócios
Você foi alocado(a) em um time da Indicium que está trabalhando atualmente junto a um cliente no processo de criação de uma plataforma de aluguéis temporários na cidade de Nova York. Para o desenvolvimento de sua estratégia de precificação, pediu para que a Indicium fizesse uma análise exploratória dos dados de seu maior concorrente, assim como um teste de validação de um modelo preditivo.

Seu objetivo é desenvolver um modelo de previsão de preços a partir do dataset oferecido, e avaliar tal modelo utilizando as métricas de avaliação que mais fazem sentido para o problema. O uso de outras fontes de dados além do dataset é permitido (e encorajado).

## 2. Compreensão dos Dados
O conjunto de dados **New York Rant Houses**, disponível em **[teste_indicium_precificacao.csv](https://github.com/lfaferreira/new-york-houses-prices/tree/main/data/raw)**, foi fornecido pela própria empresa para o processo seletivo. Trata-se de um arquivo CSV com **48.894** linhas e **16** colunas, onde os dados são categorizados entre numéricos e categóricos, apresentando também a presença de dados ausentes, sem duplicatas.

O dicionário de nomes para o arquivo é o seguinte:

| Variável                       | Descrição                                                              | Tipo    |
|--------------------------------|------------------------------------------------------------------------|---------|
| id                             | Atua como uma chave exclusiva para cada anúncio nos dados do aplicativo | int64   |
| nome                           | Representa o nome do anúncio                                           | object  |
| host_id                        | Representa o ID do usuário que hospedou o anúncio                       | int64   |
| host_name                      | Contém o nome do usuário que hospedou o anúncio                         | object  |
| bairro_group                   | Contém o nome do bairro onde o anúncio está localizado                 | object  |
| bairro                         | Contém o nome do bairro onde o anúncio está localizado                 | object  |
| latitude                       | Contém a latitude do local                                             | float64 |
| longitude                      | Contém a longitude do local                                            | float64 |
| room_type                      | Contém o tipo de espaço de cada anúncio                                | object  |
| price                          | Contém o preço por noite em dólares listado pelo anfitrião             | int64   |
| minimo_noites                  | Contém o número mínimo de noites que o usuário deve reservar           | int64   |
| numero_de_reviews              | Contém o número de comentários dados a cada listagem                   | int64   |
| ultima_review                  | Contém a data da última revisão dada à listagem                        | object  |
| reviews_por_mes                | Contém o número de avaliações fornecidas por mês                       | float64 |
| calculado_host_listings_count  | Contém a quantidade de listagens por host                               | int64   |
| disponibilidade_365            | Contém o número de dias em que o anúncio está disponível para reserva  | int64   |


## 3. Plano de ação


### 3.1. Meta final
O produto final será o modelo de machine learning utilizado para avaliar as previsões em conjunto com o dataset final, apresentando as previsões, os erros e a taxa de erro das predições.

### 3.2. Ferramentas e Frameworks

Escopo das ferramentas usadas no projeto:

- Python 3.10.0
- Jupyter Notebook
- Git & GitHub
- Kaggle
- Pandas
- Numpy
- Hyperparameter Tuning
- Pickle
- Feature Selection Attributes
    - Boruta
    - Random Forest Regressor
- Machine Learning Regression Models

### 3.3. Instalação do Projeto

1. **Clonar o Repositório (se necessário):**

   Se o projeto estiver hospedado em um repositório git, você pode cloná-lo para o seu ambiente local. Use o seguinte comando no terminal:

   ```bash
   git clone git@github.com:lfaferreira/new-york-houses-prices.git
   ```

2. **Navegar até o Diretório do Projeto:**

   Mude para o diretório do projeto usando o comando `cd`:

   ```bash
   cd new-york-houses-prices
   ```

3. **Criar um Ambiente Virtual (opcional, mas recomendado):**

   Crie um ambiente virtual para isolar as dependências do projeto. Isso é especialmente útil para evitar conflitos entre diferentes projetos. Use o seguinte comando:

   ```bash
   python -m venv nome-do-ambiente
   ```

   Ative o ambiente virtual:

   - No Windows:

     ```bash
     nome-do-ambiente\Scripts\activate
     ```

4. **Instalar as Dependências:**
   Agora, você pode instalar as dependências do projeto usando o arquivo `requirements.txt`. Execute o seguinte comando:

   ```bash
   pip install -r requirements.txt
   ```

   Isso instalará todas as bibliotecas e versões específicas listadas no arquivo `requirements.txt`.

5. **Verificar a Instalação:**
   Após a instalação, você pode verificar se todas as dependências foram instaladas corretamente:

   ```bash
   pip freeze
   ```

### 3.4. Processo CRISP-DM
A metodologia [CRIPS-DM](https://www.ibm.com/docs/en/spss-modeler/saas?topic=dm-crisp-help-overview) foi aplicada para traçar meu plano de ação. Este é o processo, passo a passo:

<p align="center">
 <img src="https://cdn.discordapp.com/attachments/1181695164633329824/1181695982753304697/CRISP-DM_Flowchart_ElderResearch_Circular-1.png?ex=6581ff25&is=656f8a25&hm=978e079ffa29bbb54af68d891c7318a2bb1f9a30f3ac0c144434b96df3e2a367&"  style="zoom:65%"/>
</p>


**Passo 1. Entendimento do Negócio:**
- Uma empresa busca um modelo preditivo para ajudar na tomada de decisão no mercado de alugueis de casas.

**Passo 2. Compreensão dos Dados:**
- O conjunto de dados foi disponibilizado pelo contratante e importado para o Jupyter Notebook.
- Os dados foram estudados para entender o impacto de cada variável no preço das casas.
- Os dados tem 37.457 anfitriões diferentes, distribuidos entre 48.894 dados.

**Passo 3. EDA:**
- A EDA é útil para investigar os dados e resumir as principais percepções.
- Ela proporciona uma compreensão básica dos dados, sua distribuição, valores nulos e muito mais.
- Gráficos e funções python foram usados para extrair os principais insights.

**Passo 4. Preparação dos Dados:**
- A preparação de dados permite uma análise eficiente, limita os erros e as imprecisões que podem ocorrer, tornando todos os dados processados mais acessíveis aos usuários.
- A seleção de dados para treinamento e teste do modelo foi feita separando as últimas 6 semanas de dados para o conjunto de teste e usando o restante para o conjunto de treinamento, resultando em:
  - Um total de 43.005, equivalente a 88% do banco de dados usado para treinamento.
  - Um total de 3.368, equivalente a 12% do banco de dados usado para teste.
- A modelagem de dados foi realizada considerando sua natureza, em que todas as variáveis foram colocadas em uma escala comparável, mas com tratamentos individuais.
  - Redimensionamento, transformação de recursos, codificação, conversão de atributos categóricos em atributos numéricos e criação de novos atributos.

**Passo 5. Seleção de Features:**
- A seleção de recursos é o método de escolha de recursos relevantes para o modelo de aprendizado de máquina.
- É criada uma lista com a relevância estimada dos atributos para o aprendizado dos modelos.
- Para isso, foi utilizado o Boruta e o Random Forest Regressor.
- Features:
    01. `room_type_Entire home/apt`
    02. `bairro_media`
    03. `disponibilidade_365`
    04. `host_id`
    05. `latitude`
    06. `longitude`
    07. `nome`
    08. `host_name`
    09. `minimo_noites`
    10. `calculado_host_listings_coun`
    
**Passo 6. Modelagem de Machine Learning:**
- Foram criados 5 modelos de regressão de Machine Learning para encontrar a melhor solução para a proposta de negócios.
- Modelos criados:
  1. Average
  2. Linear Regressor
  3. Lasso
  4. Random Forest Regressor
  5. XGBoost Regressor

**Passo 7. Avaliação:**
- As métricas de avaliação são úteis para determinar o melhor modelo de aprendizado de máquina, dentre os cinco criados anteriormente
- As métricas seguintes foram usadas para avaliar os modelos:
  1. MAE - Mean Absolute Error
  2. MAPE - Mean Absolute Percentage Error
  3. RMSE - Root Mean Squared Error
- Para garantir que nossos modelos sejam boas ferramentas de generalização, foi utilizada a validação cruzada, bem como o ajuste de hiperparâmetros.
- A validação cruzada é útil para reduzir o viés do treinamento dos dados, pois utiliza todo o conjunto de dados como dados de treinamento.
- O ajuste de hiperparâmetros é bom para extrair os melhores parâmetros, que maximizam os resultados da avaliação.


## 4. Insights Extraídos
**1** Existe mais casas disponiveis com menos quantidade de noites exigidas para o aluguel

**2** O preço das casas aumenta com o passar dos anos

**3** Casas com maior tempo de anuncio, tem o menor  numero de reviews

**4** Apartamentos inteiros são mais caros que os outros tipos de casas

**5** Casas com maior quantidade de reviews tem preços maiores

**6** Manhatam é o bairro mais caro

## 5. Modelos de Machine Learning e métricas de avaliação
Como dito anteriormente, foram criados 5 modelos de aprendizado de máquina de regressão para prever as vendas das lojas nas próximas 6 semanas. Essas são suas métricas finais com validação cruzada:

| Model Name               | MAE CV           | MAPE CV              | RMSE CV               |
|--------------------------|------------------|----------------------|-----------------------|
| Random Forest Regressor  | 49.99+/-7.3      | 0.33+/-0.02          | 230.49+/-141.75       |
| XGBoost Regressor        | 51.97+/-7.23     | 0.33+/-0.02          | 232.24+/-141.11       |
| Linear Regression        | 51.49+/-7.34     | 0.33+/-0.02          | 233.1+/-140.37        |
| Lasso                    | 53.13+/-7.91     | 0.36+/-0.03          | 235.37+/-139.13       |


O modelo **Random Forest Regressor** teve o melhor desempenho. Entretanto, devido ao tempo necessário para obter resultados com o Random Forest Regressor durante a primeira passagem do CRISP-DM, optei por usar o **XGBoost Regressor**. Para ajustar os hiperparâmetros do modelo XGBoost Regressor, foi empregado o **Random Search**. Abaixo estão suas métricas:

| Model Name          | MAE        | MAPE      | RMSE        |
|---------------------|------------|-----------|-------------|
| XGBoost Regressor   |64.051151 | 0.394168	  | 208.365855 |


## 6. Resultados de Negócios

### Objetivo

O foco do projeto é entregar um modelo que seja capaz de fazer previsões dos valores dos algueis e que auxilie gerentes em suas tomadas de decisões. Algumas perguntas sobre o projeto:

**1.** Supondo que alguém esteja considerando investir em um apartamento para alugar na plataforma, onde seria mais indicado realizar a compra?
- Em Manhattan, devido ao maior número de apartamentos na região, o que aumenta a competitividade e resulta em preços mais favoráveis.

**2.** O número mínimo de noites e a disponibilidade ao longo do ano impactam no preço?
- Sim, conforme demonstrado na Análise Exploratória de Dados (EDA), tanto o número mínimo de noites quanto a disponibilidade ao longo do ano interferem nos preços dos hotéis.

**3.** Há algum padrão nos nomes dos locais associados a valores mais elevados?
- Nada foi identificado na primeira análise do CRISP-DM, pois a correlação foi realizada entre variáveis categóricas com categóricas e numéricas com numéricas. Este tópico será explorado mais a fundo em um segundo ciclo do CRISP-DM.

**4.** Explique como a previsão de preços a partir dos dados seria feita. Quais variáveis e/ou transformações foram utilizadas e por quê?
- Optei por criar variáveis que expressassem o tempo e demonstrassem como os preços afetavam os bairros, visando aprimorar a Análise Exploratória de Dados (EDA). Além disso, foram realizadas reescala e transformações (encoding, transformação cíclica e log-transformação). O encoding foi aplicado em variáveis categóricas, e os modelos foram escolhidos com base na quantidade e nos estados que elas representavam. A transformação cíclica é utilizada para garantir uma representação temporal adequada, considerando a distância correta entre os dias da semana. O reescalonamento foi aplicado para tratar dados numéricos com escalas discrepantes.

**5.** Que tipo de problema estamos abordando (regressão, classificação)?
- Estamos lidando com um problema de regressão para a previsão de valores.

**6.** Qual modelo se aproxima melhor dos dados e quais são seus prós e contras?
- Entre os modelos utilizados, o Random Forest Regressor apresentou uma performance inicial superior. No entanto, ele demanda considerável poder de processamento e tempo para atingir ótimos desempenhos. Nesse contexto, optamos por um modelo menos custoso, mantendo resultados próximos.

**7.** Qual medida de desempenho do modelo foi escolhida e por quê?
- Escolhemos Mean Absolute Error (MAE) e Mean Absolute Percentage Error (MAPE). O MAE possui uma interpretação intuitiva, representando a média dos erros absolutos. Já o MAPE, em termos percentuais, facilita a compreensão do erro médio relativo do modelo, proporcionando uma visão abrangente do desempenho.

### Model Performance Metrics

Em nossa busca por previsões de preços, nosso modelo não apenas fornece previsões gerais do valor das casas, mas também estabelece os piores (desvalorização) e melhores (valorização) cenários com base no erro absoluto médio (MAE). Além disso, avaliamos a precisão da previsão por meio do erro percentual absoluto médio (MAPE).Essas métricas nos permitem classificar as casas de acordo com suas taxas de precisão.

A tabela a seguir ilustra as previsões das 5 lojas mais bem classificadas de acordo com o MAPE

| host_id | Predictions    | Worst Scenario | Best Scenario | MAE      | MAPE (%) |
|---------|----------------|----------------|---------------|----------|----------|
 1097753  | $125.00        | $125.00        | $125.01       | 0.00     | 0.00     |
 18416970 | $103.00        | $102.99        | $103.00       | 0.00     | 0.00     |
 13907788 | $95.00         | $95.00         | $95.00        | 0.00     | 0.00     |
 22663500 | $74.99         | $74.99         | $75.00        | 0.01     | 0.01     |
 73618889 | $65.01         | $65.00         | $65.01        | 0.01     | 0.01     |

### Casa Especifica
| host_id | Predictions    | Worst Scenario | Best Scenario | MAE      | MAPE (%) |
|---------|----------------|----------------|---------------|----------|----------|
 2845     | $1058.24       | $691.12        | $1425.35      | 367.12   | 276.45   |

O gráfico a seguir ilustra a comparação das vendas reais com a previsão do modelo: 

 <p align="center">
 <img src="https://cdn.discordapp.com/attachments/1204245004948865106/1204245034841538632/image.png?ex=65d40796&is=65c19296&hm=c2826a4612b0bb2390bd0b0293f482fc64a4e3cf4c56b7440873476ae270116f&"  style="zoom:65%"/>
</p>

### Total do alugel na rede

Além disso, apresentamos os valores totais de alugueis diarios para toda a rede, tanto no melhor quanto no pior cenário:

| Scenarios       | Values               |
|-----------------|----------------------|
| Predictions     | $5,422,212.50        |
| Worst Scenario  | $3,465,185.05        |
| Best Scenario   | $7,379,239.60        |


Esses resultados fornecem informações valiosas sobre o desempenho financeiro esperado da rede de alugueis em New York.

## 7. Trabalho Futuro

- Implementar um novo ciclo CRISP-DM, usando o Regressor Random Forest em vez do Regressor XGBoost, para melhorar o desempenho do modelo final.

- Criar um painel no Power BI ou Tablue com as informações do modelo implementado e da EDA.
