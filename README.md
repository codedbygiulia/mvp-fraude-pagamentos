# MVP — Detecção de Fraudes em Pagamentos Digitais

Análise exploratória, pré-processamento e modelagem supervisionada sobre transações financeiras simuladas pelo PaySim.

## Sobre o Projeto

Este trabalho foi desenvolvido como MVP da disciplina **Análise de Dados e Boas Práticas**, percorrendo o pipeline completo de ciência de dados: definição do problema, análise exploratória (EDA), pré-processamento e modelagem supervisionada.

O dataset utilizado é uma amostra de **50.000 transações** do [PaySim](https://www.kaggle.com/datasets/ealaxi/paysim1), um simulador de transações financeiras móveis baseado em dados reais. A variável-alvo `isFraud` indica se a transação é fraudulenta (1) ou legítima (0).

## Estrutura do Notebook

| Seção | Descrição |
|---|---|
| **Definição do Problema** | Contexto, hipóteses, tipo de problema e descrição dos atributos |
| **Análise Exploratória (EDA)** | Estatísticas descritivas, distribuições, boxplots, correlações, pairplot e análise temporal |
| **Validação de Hipóteses** | Confirmação das 4 hipóteses com evidências quantitativas e visuais |
| **Pré-Processamento** | Engenharia de features, remoção de colunas, OHE, split treino/teste e 4 versões escalonadas |
| **Modelagem Supervisionada** | Regressão Logística, Árvore de Decisão e Random Forest com `class_weight='balanced'` |
| **Avaliação** | Matrizes de confusão, curva ROC, validação cruzada, importância de features e análise de erros |

## Hipóteses Investigadas

| # | Hipótese | Resultado |
|---|---|---|
| H1 | Fraudes concentram-se em TRANSFER e CASH_OUT | ✅ Confirmada — 100% das fraudes nesses dois tipos |
| H2 | Fraudes zeram o saldo de origem | ✅ Confirmada |
| H3 | Valores de fraudes são mais altos | ✅ Confirmada |
| H4 | Destino com saldo zero antes da fraude (contas mula) | ✅ Confirmada |

## Principais Resultados da Modelagem

| Modelo | Acurácia | Precisão | Recall | F1-score | ROC-AUC |
|---|---|---|---|---|---|
| Regressão Logística | 0.9644 | 0.8365 | 0.9736 | 0.8998 | 0.9937 |
| Árvore de Decisão | 0.9987 | 0.9955 | 0.9968 | 0.9961 | 0.9979 |
| Random Forest | 0.9993 | 0.9996 | 0.9963 | 0.9980 | 0.9991 |

O Random Forest alcançou apenas **9 falsos negativos** em 2.464 fraudes no teste (taxa de 0,37%).

## Tecnologias Utilizadas

- Python 3
- pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn (LogisticRegression, DecisionTree, RandomForest, StandardScaler, MinMaxScaler, RobustScaler)
- Google Colab

## Como Executar

1. Abra o notebook no Google Colab:
   - Acesse https://colab.research.google.com/drive/1M27iTFLXm-MBzv1tXoaTDxvq4NPEI9V1?usp=sharing
   - **File → Open notebook → GitHub** → cole a URL deste repositório
2. Clique em **Runtime → Run all**
3. O dataset é carregado automaticamente via URL do repositório

## Estrutura do Repositório

```
├── README.md
├── fraud_dataset_sample_50000.csv
├── Cópia_de_Trabalho_Giulia_Barros_dos_Reis_Análise_de_Dados_e_Boas_Práticas_(40530010055_20260_01).ipynb
└── Trabalho_Giulia_Barros_dos_Reis_Análise_de_Dados_e_Boas_Práticas.ipynb
```
- Últimos dois arquivos são iguais. 
## Autora

**Giulia Barros dos Reis** — Matrícula 4052025001231
