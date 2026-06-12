# Detecção de Fraudes em Transações Financeiras com Machine Learning

Este projeto aborda o desenvolvimento de um pipeline de Ciência de Dados para identificar transações bancárias fraudulentas. O principal desafio técnico envolveu o tratamento de um desbalanceamento severo de classes, onde fraudes representam apenas 0,13% do volume total de dados (mais de 6,3 milhões de registros).

## Dataset utilizado:
* Fraud Detection Dataset: https://www.kaggle.com/datasets/amanalisiddiqui/fraud-detection-dataset?resource=download

## 🛠️ Tecnologias e Bibliotecas Utilizadas
* **Linguagem:** Python
* **Manipulação e Análise:** Pandas, NumPy
* **Visualização de Dados:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (Logistic Regression, Random Forest, HistGradientBoosting)

## 📊 Análise Exploratória de Dados (EDA)
* **Volume:** Dataset robusto com 6.362.620 de transações financeiras.
* **Desbalanceamento:** 99,87% das transações são legítimas e 0,13% são fraudes, exigindo métricas de avaliação rigorosas (Precision, Recall e F1-Score) além da Acurácia convencional.
* **Engenharia de Recursos:** Codificação de variáveis categóricas via `LabelEncoder` e exclusão de identificadores textuais irrelevantes (`nameOrig`, `nameDest`) para adequação aos modelos.
* **Padronização:** Aplicação de `StandardScaler` para normalização das escalas das variáveis financeiras.

## 🤖 Modelagem e Resultados

Foram testadas três abordagens para mitigar o impacto do desbalanceamento de classes:

1. **Regressão Logística (com pesos balanceados):** Obteve alta acurácia (99,95%), com Precision de 0,90 e Recall de 0,75 para a classe de fraude.
2. **Random Forest Classifier (com pesos balanceados):** Apesar do Recall alto (0,96), apresentou uma taxa elevada de falsos positivos, reduzindo a Precision para 0,03.
3. **HistGradientBoostingClassifier (Vencedor):** Demonstrou o melhor equilíbrio operacional para o negócio, alcançando **90% de Precision** e **75% de Recall** na detecção de transações fraudulentas, minimizando o bloqueio indevido de clientes legítimos (apenas 131 falsos positivos em mais de 1,2 milhão de testes).

## 📈 Conclusão do Negócio
O modelo final oferece uma solução robusta para automação de segurança financeira, permitindo interceptar 75% das tentativas de fraude em tempo real com alta confiabilidade operacional.
