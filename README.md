# Previsão de Inadimplência em Concessão de Crédito

##  Sobre o projeto

Este projeto tem como objetivo prever a inadimplência de clientes no momento da concessão de crédito, utilizando técnicas de análise de dados e machine learning.

A inadimplência é definida como atraso igual ou superior a 90 dias em um período de 12 meses.

O modelo desenvolvido auxilia na tomada de decisão, permitindo equilibrar **risco (prejuízo)** e **retorno (aprovação de crédito)**.

---

## Problema de negócio

Na concessão de crédito, existem dois erros críticos:

* **Falso positivo** → Aprovar cliente inadimplente → prejuízo financeiro
* **Falso negativo** → Recusar cliente bom → perda de receita

O objetivo do modelo é **minimizar esses riscos**, com foco maior na identificação de clientes inadimplentes.

---

## Dataset

* ~16.650 registros
* 16 variáveis (demográficas, financeiras e comportamentais)
* Variável alvo: `mau` (inadimplente = 1, adimplente = 0)
* Base altamente desbalanceada (~2% inadimplentes)

---

## Tecnologias utilizadas

* Python
* Pandas
* NumPy
* Seaborn / Matplotlib
* Scikit-learn

---

## Etapas do projeto

### 1. Entendimento dos dados

* Análise exploratória (EDA)
* Identificação de inconsistências (ex: tempo de emprego negativo)

### 2. Preparação dos dados

* Tratamento de valores inválidos
* Criação de variável indicadora de ausência (`sem_emprego_info`)
* Codificação de variáveis categóricas (one-hot encoding)

### 3. Modelagem

* Algoritmo: Random Forest
* Ajuste para desbalanceamento com `class_weight='balanced'`
* Divisão treino/teste com `stratify`

### 4. Avaliação

* Métricas utilizadas:

  * Recall
  * Precision
  * ROC-AUC
* Curva ROC
* Matriz de confusão
* Feature importance

### 5. Ajuste de decisão (diferencial do projeto)

* Uso de probabilidades (`predict_proba`)
* Ajuste de threshold para controle de risco

---

## Resultados

* O modelo conseguiu identificar padrões relevantes de inadimplência
* Acurácia isolada se mostrou inadequada devido ao desbalanceamento
* O recall da classe inadimplente foi priorizado

### Trade-off de negócio

Ajustando o threshold:

* Threshold menor → maior detecção de inadimplentes (↓ prejuízo)
* Threshold maior → maior aprovação de clientes (↑ receita)

---

## Principais aprendizados

* Métricas tradicionais podem ser enganosas em dados desbalanceados
* Modelos não tomam decisões — **o negócio define o threshold**
* Explicabilidade (feature importance) é essencial em crédito
* Pequenos ajustes podem gerar grande impacto financeiro

---

## Próximos passos

* Balanceamento com SMOTE
* Otimização de hiperparâmetros (GridSearch)
* Teste com outros modelos (XGBoost, Logistic Regression)
* Simulação de impacto financeiro

---

## Estrutura do projeto

```bash
├── data/
│   └── demo01.csv
├── notebook/
│   └── projeto_credito.ipynb
├── script/
│   └── projeto_credito.py
└── README.md
```

---

## Contato

Se quiser trocar ideias ou discutir o projeto:

* LinkedIn: https://www.linkedin.com/in/leonelucio/

---

## ⭐ Considerações finais

Este projeto foi desenvolvido com foco em conectar análise de dados com tomada de decisão de negócio, especialmente em um contexto realista de crédito.

Mais do que construir um modelo, o objetivo foi entender **como ele pode ser utilizado na prática**.
