# 💳 Credit Scoring com Machine Learning - Home Credit

Este projeto foi desenvolvido como parte dos meus estudos em **Engenharia de Computação na UFES**. O objetivo é prever a probabilidade de inadimplência de clientes com pouco ou nenhum histórico de crédito, utilizando técnicas avançadas de IA e Machine Learning.

## 🤖 Abordagem de Machine Learning

O coração deste projeto é a utilização do algoritmo **LightGBM (Light Gradient Boosting Machine)**. A escolha por esta técnica de *Gradient Boosting* baseou-se em:
* **Lidar com dados faltantes:** O dataset original possui muitos valores nulos, que o LightGBM trata nativamente sem a necessidade de imputações que poderiam enviesar o modelo.
* **Eficiência e Escala:** Capacidade de processar centenas de variáveis e milhares de linhas com baixo custo computacional.
* **Otimização de AUC:** O modelo foi treinado focando na métrica *Area Under the Curve*, garantindo a melhor separação possível entre perfis de risco.

## 🛠️ Metodologia e Feature Engineering

Além do algoritmo o modelo também se diferencia pelo tratamento de dados:
1. **Tratamento de Anomalias:** Correção de inconsistências em dados de tempo de emprego (`DAYS_EMPLOYED`).
2. **Engenharia de Atributos:** Criação da variável **`CREDIT_TERM`** (razão entre anuidade e crédito total), que se provou o preditor mais forte do modelo, superando scores externos de birôs de crédito.
3. **One-Hot Encoding:** Transformação de variáveis categóricas para processamento matemático.
4. **Validação Estratificada:** Divisão dos dados garantindo que a proporção de inadimplentes (8%) fosse mantida nos conjuntos de treino e validação, evitando o viés de seleção.

## 📊 Resultados

* **Métrica Final (AUC): 0.77**
* O modelo demonstrou uma capacidade robusta de distinção de risco, sendo a variável sintética `CREDIT_TERM` a de maior importância no processo de decisão da IA (Feature Importance).

## 🧰 Tecnologias Utilizadas

* **Linguagem:** Python
* **Bibliotecas:** Pandas, NumPy, Scikit-Learn
* **IA/ML:** LightGBM
* **Visualização:** Matplotlib, Seaborn

---
*Desenvolvido como projeto pessoal e acadêmico para a disciplina de Data Science.*
