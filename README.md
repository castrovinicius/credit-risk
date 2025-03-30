# Projeto de Previsão de Risco de Crédito

Este projeto tem como objetivo desenvolver um modelo de aprendizado de máquina para prever a probabilidade de inadimplência de clientes com base em diferentes fontes de dados fornecidos pela Home Credit.

## Sumário
- [Visão Geral](#visão-geral)
- [Objetivos](#objetivos)
- [Etapas do Desenvolvimento](#etapas-do-desenvolvimento)
- [Dados Utilizados](#dados-utilizados)
- [Metodologia](#metodologia)
- [Resultados Obtidos](#resultados-obtidos)
- [Conclusão](#conclusão)
- [Como Executar](#como-executar)

## Visão Geral

O projeto aborda a previsão de risco de crédito utilizando dados históricos e estatísticos dos clientes. Foram utilizadas diversas técnicas de pré-processamento, análise exploratória de dados (EDA) e modelagem preditiva para identificar os fatores que influenciam a inadimplência.

## Objetivos

- **Análise Exploratória dos Dados (EDA):** Entender a estrutura dos dados, identificar relationships e detectar possíveis outliers ou inconsistências.
- **Pré-processamento:** Limpeza, tratamento de valores faltantes e transformação das variáveis.
- **Engenharia de Features:** Seleção e criação de novas variáveis a partir dos dados brutos.
- **Modelagem:** Treinamento e avaliação de vários modelos de classificação, incluindo RandomForest, XGBoost, LightGBM e CatBoost.
- **Otimização:** Uso de técnicas de otimização, como o Optuna, para ajuste dos hiperparâmetros.
- **Avaliação:** Medição do desempenho dos modelos por meio de métricas como acurácia, precisão, recall, F1 e AUC-ROC.

## Etapas do Desenvolvimento

1. **Importação e Configuração:**
   - Importação das bibliotecas necessárias, como `pandas`, `numpy`, `matplotlib`, `seaborn` e bibliotecas de machine learning do `scikit-learn`, `xgboost`, `lightgbm` e `catboost`.
   - Configuração das opções de visualização no `pandas`.

2. **Análise Exploratória dos Dados (EDA):**
   - Investigação dos diferentes conjuntos de dados disponíveis.
   - Visualização de distribuições e correlações entre variáveis.
   - Identificação de inconsistências e outliers para ações de limpeza.

3. **Pré-processamento e Engenharia de Features:**
   - Tratamento de valores ausentes utilizando `SimpleImputer` e técnicas similares.
   - Codificação de variáveis categóricas com `OneHotEncoder` e `OrdinalEncoder`.
   - Escalonamento das variáveis contínuas com `StandardScaler` ou `MinMaxScaler`.
   - Combinação e criação de novas features a partir dos dados brutos.

4. **Modelagem Preditiva:**
   - Construção de pipelines de pré-processamento e modelagem.
   - Treinamento de diferentes algoritmos de classificação.
   - Utilização de técnicas de validação cruzada para garantir a robustez dos modelos.

5. **Otimização de Hiperparâmetros:**
   - Emprego do [`optuna`](https://optuna.readthedocs.io) para encontrar a melhor configuração de hiperparâmetros para cada modelo.
   - Comparação dos resultados dos modelos otimizados.

6. **Avaliação dos Modelos:**
   - Cálculo de métricas como acurácia, precisão, recall, F1-score e AUC-ROC.
   - Geração de gráficos de curvas ROC e matrizes de confusão para visualizar a performance dos modelos.

## Dados Utilizados

A estrutura de dados do projeto está organizada da seguinte forma:
- **application_{train|test}.csv:** Dados estáticos dos empréstimos, onde o conjunto de treino contém a variável alvo (`TARGET`).
- **bureau.csv & bureau_balance.csv:** Informações de históricos de crédito dos clientes.
- **installments_payments.csv:** Dados de aplicações anteriores e registros de pagamentos.

Os dados estão na pasta [data/01_raw](data/01_raw).

## Metodologia

A abordagem metodológica do projeto seguiu os seguintes passos:
1. **Importação dos Dados:** Leitura e verificação da integridade dos arquivos de dados.
2. **Exploração Inicial:** Geração de resumos estatísticos e gráficos informativos para entendimento do cenário.
3. **Preparação dos Dados:** Limpeza e preparação através de técnicas de imputação, codificação e escalonamento.
4. **Construção dos Modelos:** Desenvolvimento de pipelines que encapsulam pré-processamento e modelagem.
5. **Validação e Otimização:** Uso de validação cruzada e técnicas de otimização para selecionar os melhores parâmetros.
6. **Análise Final e Interpretação:** Comparação e interpretação dos resultados para definição do melhor modelo.

## Resultados Obtidos

Os experimentos demonstraram que:
- A combinação de técnicas de engenharia de features com otimização de hiperparâmetros melhorou significativamente a performance dos modelos.
- Modelos como o XGBoost e o LightGBM se destacaram na previsão do risco de crédito, apresentando elevados valores de AUC-ROC e F1-score.
- A análise das métricas e das curvas ROC permitiu a identificação dos trade-offs entre diferentes modelos, auxiliando na escolha do modelo mais balanceado para o problema.

## Conclusão

Este projeto evidenciou a importância de uma abordagem estruturada, desde a exploração de dados até a otimização dos modelos preditivos. Através das etapas realizadas, foi possível desenvolver um sistema robusto para avaliação do risco de crédito, com potencial para aplicação em cenários reais de análise financeira. As análises e os resultados obtidos servem como base para aprimoramentos futuros, inclusive a integração de novas fontes de dados e técnicas de explicabilidade dos modelos.

## Como Executar

1. **Pré-requisitos:**
   - Python 3.11
   - Instalar as dependências com:
     ```sh
     pip install -r requirements.txt
     ```
2. **Execução do Notebook:**
   - Abra o arquivo [credit-risk.ipynb](credit-risk.ipynb) no Jupyter Notebook ou JupyterLab e execute as células na ordem para reproduzir a análise.
3. **Interpretação dos Resultados:**
   - A visualização dos gráficos e a saída das métricas possibilitam a avaliação do desempenho dos modelos.

---

Desenvolvido com dedicação e foco na clareza, este projeto busca contribuir para a melhoria das estratégias de análise de crédito no cenário financeiro.