# 📊 TelecomX – Predição de Evasão de Clientes (Churn) | Parte 2

## 🧠 Descrição do Projeto

A **TelecomX** segue enfrentando o desafio da evasão (churn) de clientes. Após o diagnóstico inicial, este projeto avança para a construção de **modelos preditivos** capazes de antecipar quais clientes têm maior risco de cancelar seus serviços.  
O objetivo é transformar dados comportamentais e contratuais em **ação estratégica de retenção**, apoiando a empresa com decisões baseadas em ciência de dados.

---

## 🎯 Objetivos

- Preparar dados para Machine Learning (tratamento, encoding, normalização)
- Selecionar e criar variáveis relevantes
- Treinar e comparar modelos de classificação
- Avaliar desempenho dos modelos com métricas apropriadas para churn
- Gerar insights para apoiar as estratégias de retenção

---

## 📦 Etapas do Projeto

### 1. Pré-processamento e Feature Engineering
- Limpeza de inconsistências e tratamento de tipos
- Codificação de variáveis categóricas (`OneHotEncoder`)
- Padronização das variáveis numéricas
- Criação de novas features (ex: `possivel_upgrade_recente`, `servico_por_real`)
- Remoção de variáveis com alta multicolinearidade

### 2. Balanceamento das Classes
- Aplicação de técnicas de oversampling/undersampling (SMOTEENN, Tomek Links) para corrigir o desbalanceamento de churn

### 3. Modelagem e Avaliação
- Modelos: **Regressão Logística, Random Forest, XGBoost**
- Ajuste de hiperparâmetros com GridSearchCV
- Seleção de variáveis com SelectFromModel
- Avaliação de desempenho: **F1-score, Recall, Precision e Accuracy** (com foco em F1 e recall para churn)
- Comparação de resultados antes e depois do balanceamento

### 4. Interpretação e Insights
- Análise da importância das variáveis (feature importance)
- Geração de recomendações práticas para o negócio

---

## 📊 Principais Métricas dos Modelos

### Antes do Balanceamento

| Modelo                | Precision (churn) | Recall (churn) | F1-score (churn) | Acurácia |
|-----------------------|-------------------|----------------|------------------|----------|
| Regressão Logística   |      0.65         |     0.53       |     0.58         |   0.80   |
| Random Forest         |      0.63         |     0.51       |     0.56         |   0.79   |
| XGBoost               |      0.60         |     0.52       |     0.56         |   0.78   |

### Após o Balanceamento

| Modelo                | Precision (churn) | Recall (churn) | F1-score (churn) | Acurácia |
|-----------------------|-------------------|----------------|------------------|----------|
| Regressão Logística   |      0.50         |     0.79       |     0.61         |   0.73   |
| Random Forest         |      0.52         |     0.75       |     0.62         |   0.75   |
| XGBoost               |      0.53         |     0.76       |     0.62         |   0.75   |

> **Obs:** Métricas calculadas sobre o conjunto de teste, linha da classe 1 (`churn`). O foco está no recall e F1-score, fundamentais para identificar clientes em risco real.

---

## 📈 O que significam as métricas?

- **Recall (churn):** Proporção dos clientes que realmente evadiram e foram corretamente identificados pelo modelo. Quanto maior, menos clientes “escapam” do radar da retenção.
- **Precision (churn):** Proporção dos clientes previstos como churn que realmente evadiram. Indica o quanto das ações tomadas são direcionadas corretamente.
- **F1-score (churn):** Equilíbrio entre recall e precision – principal métrica de desempenho em churn.
- **Acurácia:** Percentual total de acertos, **mas não é o foco em churn** (por conta do desbalanceamento).

---

## 💡 Insights & Fatores de Risco Identificados

| Fator                              | Impacto na Evasão |
|-------------------------------------|-------------------|
| Contratos mensais                   | Aumentam o churn  |
| Pouco tempo de cliente              | Aumenta o churn   |
| Pagamentos digitais/automáticos     | Aumentam o churn  |
| Upgrades recentes                   | Aumentam o churn  |
| Poucos serviços contratados         | Aumentam o churn  |
| Multi-serviços, maior tempo de casa | Diminuem o churn  |

---

## 🧭 Recomendações Estratégicas

- Estimular contratos de maior duração (anuais/bienais)
- Oferecer promoções para clientes em upgrades recentes
- Criar programas de fidelidade para multi-serviços
- Ações proativas para clientes identificados como risco (contrato mensal, pouco tempo de empresa, conta alta)
- Campanhas para engajar clientes com serviços adicionais

---

## 💻 Como Executar

1. Acesse o [Google Colab](https://colab.research.google.com/)
2. Carregue o notebook `TelecomX_parte2.ipynb`
3. Execute célula por célula para reproduzir toda a análise e os experimentos com modelos.
4. Os dados já estão disponíveis junto ao repositório/notebook.

📎 Notebook: [`TelecomX_parte2.ipynb`](./TelecomX_parte2.ipynb)

---

## 📚 Habilidades Aplicadas

- Pré-processamento e análise exploratória de dados
- Feature engineering e seleção de variáveis
- Construção e avaliação de modelos preditivos
- Interpretação de métricas e resultados para negócios
- Comunicação de insights estratégicos

---

## 👨‍💻 Autor

Desenvolvido por [Ricardo Hamada](https://github.com/vthamada)  
Challenge 3 – Data Science  
[Alura + Oracle Next Education (ONE)](https://www.oracle.com/br/education/oracle-next-education/)

📬 [LinkedIn](https://www.linkedin.com/in/ricardohamada)

---

> **Observação:** Os dados utilizados neste projeto são fictícios e têm fins educacionais.
