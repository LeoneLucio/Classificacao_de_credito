# Previsão de Inadimplência em Concessão de Crédito

## Contexto

Conceder crédito sem avaliar risco é uma das formas mais rápidas de gerar prejuízo em uma instituição financeira.

Neste projeto, desenvolvi um modelo de machine learning para prever inadimplência no momento da solicitação de um cartão de crédito, com foco em apoiar decisões mais seguras e orientadas por dados.

A inadimplência é definida como atraso igual ou superior a 90 dias em um período de 12 meses.

---

## Problema de Negócio

Na concessão de crédito, decisões incorretas geram impacto direto no resultado financeiro:

- **Falso positivo**: conceder crédito a um cliente inadimplente → prejuízo  
- **Falso negativo**: recusar um bom cliente → perda de receita  

O desafio é equilibrar risco e retorno, priorizando a identificação de clientes com maior probabilidade de inadimplência.

---

## Dataset

- ~16.650 registros  
- 16 variáveis (demográficas, financeiras e comportamentais)  
- Variável alvo: `mau` (1 = inadimplente, 0 = adimplente)  
- Base altamente desbalanceada (~2,3% inadimplentes)  

---

## Tecnologias Utilizadas

- Python  
- Pandas / NumPy  
- Seaborn / Matplotlib  
- Scikit-learn  

---

## Etapas do Projeto (CRISP-DM)

1. **Entendimento do negócio**  
2. **Análise exploratória (EDA)**  
3. **Preparação dos dados**  
4. **Modelagem (Random Forest)**  
5. **Avaliação do modelo**  

---

## Resultados do Modelo

- Acurácia: **~97%** *(não confiável isoladamente devido ao desbalanceamento)*  
- Recall (inadimplentes): **~23%**  
- Precision: **~19–24%**  

> O modelo apresentou boa capacidade geral, porém com limitações na identificação da classe minoritária (inadimplentes), o que é esperado em bases altamente desbalanceadas.

---

## 📌 Principais Insights

- Clientes com **menor tempo de emprego** apresentam maior probabilidade de inadimplência  
- A **ausência de informação sobre emprego** pode indicar risco elevado  
- Variáveis isoladas possuem baixo poder preditivo, mas ganham força quando combinadas  
- O forte **desbalanceamento da base** impacta diretamente a escolha de métricas e abordagem do modelo  

---

## 🤖 Modelagem

- Algoritmo: **Random Forest**  
- Tratamento de variáveis categóricas com **one-hot encoding**  
- Separação treino/teste  
- Avaliação com múltiplas métricas (Recall, Precision, ROC-AUC)

---

## ⚖️ Trade-off de Negócio

O modelo permite ajustar o nível de risco através da definição de threshold:

- Threshold menor → maior detecção de inadimplentes (↓ prejuízo)  
- Threshold maior → maior aprovação de clientes (↑ receita)  

---

## 💡 Aplicação no Negócio

O modelo pode ser utilizado como ferramenta de apoio na decisão de crédito, permitindo ajustar o nível de risco aceitável pela empresa.

Mais importante que o modelo em si, é como ele é utilizado:  
a definição do threshold impacta diretamente o equilíbrio entre risco e retorno.

---

## Simulação de Impacto Financeiro

Considerando:

- Cliente adimplente: +5 unidades de lucro  
- Cliente inadimplente: -100 unidades de prejuízo  

A aplicação do modelo demonstrou potencial para redução de perdas financeiras ao evitar concessões de alto risco.

---

## 🚀 Próximos Passos

- Balanceamento da base (SMOTE)  
- Otimização de hiperparâmetros (GridSearch)  
- Teste com modelos mais robustos (XGBoost, Logistic Regression)  
- Simulação mais detalhada de impacto financeiro  

---

## 📁 Estrutura do Projeto
