# Classificação de Risco de Doenças Cardiovasculares (DCV) com Machine Learning

## Objetivo do Projeto

Este projeto de Trabalho de Conclusão de Curso (TCC) tem como objetivo principal **aplicar e comparar** a performance de diferentes algoritmos de *Machine Learning* na classificação do risco de Doenças Cardiovasculares (DCV).

O foco é identificar o modelo preditivo mais **robusto e clinicamente seguro** para o diagnóstico precoce, priorizando a métrica **Recall** e a minimização dos **Falsos Negativos (FN)**, o erro mais crítico no contexto da saúde cardiovascular.

---

## Dataset e Pré-processamento

### Dataset
Os modelos foram treinados e avaliados em um conjunto de dados abrangente sobre saúde cardiovascular (disponível publicamente no **Kaggle** sob o nome `Cardiovascular Disease dataset` de Svetlana Ulianova), composto por aproximadamente 70.000 instâncias de exames médicos de rotina.

### Pré-processamento e Limpeza
Foi realizado um pré-processamento rigoroso para garantir a integridade e a validade fisiológica dos dados:
1.  **Limpeza Fisiológica:** Remoção de *outliers* clinicamente inviáveis, incluindo registros onde a pressão diastólica ($\text{ap\_lo}$) era maior que a sistólica ($\text{ap\_hi}$), e valores de pressão arterial na ordem dos milhares (erros de digitação).
2.  **Padronização e Codificação:** Utilização do **`ColumnTransformer`** e **`Pipeline`** para aplicar o **`StandardScaler`** (em variáveis numéricas) e o **`OneHotEncoder`** (em variáveis categóricas), garantindo a prevenção de *Data Leakage*.

---

### Algoritmos Comparados

Foram avaliados quatro modelos de *Machine Learning* para cobrir abordagens lineares e baseadas em *Ensemble*:
* **Regressão Logística (LR):** Utilizado como modelo *baseline* linear.
* **Support Vector Machine (SVM/SVC):** Classificador não-linear baseado em hiperplano de margem máxima.
* **Random Forest (RF):** Modelo de *Ensemble* baseado em **Bagging** (múltiplas árvores).
* **XGBoost:** Modelo de *Ensemble* baseado em **Gradient Boosting** (conhecido pela alta performance e eficiência).
