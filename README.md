# Classificação de Risco de Doenças Cardiovasculares (DCV) com Machine Learning

## Objetivo do Projeto

Este projeto de Trabalho de Conclusão de Curso (TCC) tem como objetivo principal **aplicar e comparar** a performance de diferentes algoritmos de *Machine Learning* na classificação do risco de Doenças Cardiovasculares (DCV).

O foco é identificar o modelo preditivo mais **robusto e clinicamente seguro** para o diagnóstico precoce, priorizando a métrica **Recall** e a minimização dos **Falsos Negativos (FN)**, o erro mais crítico no contexto da saúde cardiovascular.

---

## Dataset e Pré-processamento

### Dataset
Os modelos foram treinados e avaliados em um conjunto de dados abrangente sobre saúde cardiovascular (disponível publicamente no **Kaggle** sob o nome `Cardiovascular Disease dataset` de Svetlana Ulianova), composto por aproximadamente 70.000 instâncias de exames médicos de rotina.

### Descrição das Variáveis

O *dataset* contém 12 variáveis preditoras e a variável alvo (`cardio`), categorizadas da seguinte forma:

#### 1. Características Demográficas e Fisiológicas (Numéricas)

| Variável | Descrição | Unidade | Observações de Pré-processamento |
| :--- | :--- | :--- | :--- |
| **age** | Idade do paciente. | Anos | Originalmente em dias; convertida para anos e padronizada. |
| **height** | Altura. | cm | Padronizada via `StandardScaler`. |
| **weight** | Peso. | kg | Padronizado via `StandardScaler`. |

#### 2. Resultados de Exames Clínicos (Numéricas e Categóricas)

| Variável | Descrição | Unidade | Níveis Categóricos |
| :--- | :--- | :--- | :--- |
| **ap\_hi** | Pressão Arterial Sistólica. | mmHg | **Numérica:** Alvo de limpeza de *outliers* extremos. |
| **ap\_lo** | Pressão Arterial Diastólica. | mmHg | **Numérica:** Alvo de limpeza de *outliers* e inconsistências (ap_hi e ap_lo). |
| **cholesterol** | Nível de Colesterol. | Nível | 1: Normal, 2: Acima do Normal, 3: Bem Acima do Normal. |
| **gluc** | Nível de Glicose. | Nível | 1: Normal, 2: Acima do Normal, 3: Bem Acima do Normal. |

#### 3. Informações de Hábito (Binárias/Categóricas)

| Variável | Descrição | Valores | Tipo de Dado |
| :--- | :--- | :--- | :--- |
| **gender** | Gênero. | 1 ou 2 | Categórica Nominal. |
| **smoke** | Tabagismo. | 0 ou 1 | 1: Fuma, 0: Não Fuma. |
| **alco** | Consumo de Álcool. | 0 ou 1 | 1: Consome, 0: Não Consome. |
| **active** | Atividade Física. | 0 ou 1 | 1: Ativo, 0: Não Ativo. |

#### Variável Alvo

| Variável | Descrição | Valores | Tipo de Dado |
| :--- | :--- | :--- | :--- |
| **cardio** | Presença de Doença Cardiovascular. | 0 ou 1 | **0: Saudável**; **1: Doente**. |

---
---

### Algoritmos Comparados

Foram avaliados quatro modelos de *Machine Learning* para cobrir abordagens lineares e baseadas em *Ensemble*:
* **Regressão Logística (LR):** Utilizado como modelo *baseline* linear.
* **Support Vector Machine (SVM/SVC):** Classificador não-linear baseado em hiperplano de margem máxima.
* **Random Forest (RF):** Modelo de *Ensemble* baseado em **Bagging** (múltiplas árvores).
* **XGBoost:** Modelo de *Ensemble* baseado em **Gradient Boosting** (conhecido pela alta performance e eficiência).
