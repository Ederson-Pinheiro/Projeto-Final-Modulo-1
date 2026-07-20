# Sistema de Predição de Risco de Crédito com Machine Learning

## ``Sobre o Projeto``

Este projeto foi desenvolvido como atividade avaliativa da disciplina de **Machine Learning e Visão Computacional**. O objetivo é construir um pipeline completo de Ciência de Dados para prever a inadimplência de clientes que solicitam empréstimos, utilizando técnicas de pré-processamento, engenharia de atributos e algoritmos de aprendizado supervisionado.

Durante o desenvolvimento foram aplicadas todas as etapas de um projeto de Machine Learning, desde a análise exploratória dos dados até a avaliação dos modelos e a recomendação de uma solução para o problema de negócio.

---

# ``Objetivo``

Desenvolver um modelo preditivo capaz de classificar clientes com maior probabilidade de inadimplência, auxiliando instituições financeiras na tomada de decisão durante a concessão de crédito.

---

# ``Problema de Negócio``

Instituições financeiras precisam avaliar diariamente milhares de solicitações de empréstimo. Uma decisão incorreta pode gerar impactos financeiros significativos.

Neste contexto, dois tipos de erro podem ocorrer:

* **Falso Positivo:** um cliente considerado inadimplente pelo modelo, mas que pagaria corretamente o empréstimo.
* **Falso Negativo:** um cliente considerado confiável pelo modelo, mas que se tornará inadimplente.

Como a aprovação de crédito para clientes inadimplentes gera perdas financeiras diretas, este projeto prioriza a redução dos **Falsos Negativos**, buscando um modelo que ofereça maior segurança para o negócio.

---

# ``Base de Dados``

Foi utilizada a base de dados de **Risco de Crédito**, composta por informações financeiras e pessoais dos clientes.

A variável alvo do projeto é:

* **loan_status**(``loan_status``)

  * 0 → Cliente adimplente
  * 1 → Cliente inadimplente

---

# ``Tecnologias Utilizadas``
```
* Python 3
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Imbalanced-Learn (SMOTE)
* Google Colab
* Git e GitHub
```
# ``Como Executar o Projeto``

## ``Clonar o repositório``

```bash
git clone https://github.com/SEU-USUARIO/Projeto-ML-Credito.git
```

## ``Instalar as dependências``

```bash
pip install -r requirements.txt
```

## ``Executar o notebook``

Abra o arquivo:

```text
notebook.ipynb
```

utilizando o Jupyter Notebook, JupyterLab, Visual Studio Code ou Google Colab.

---

# ``Dicionário de Dados``
```
| Variável                   | Descrição                        |
| -------------------------- | -------------------------------- |
| person_age                 | Idade do cliente                 |
| person_income              | Renda anual                      |
| person_home_ownership      | Situação da moradia              |
| person_emp_length          | Tempo de emprego                 |
| loan_intent                | Finalidade do empréstimo         |
| loan_grade                 | Classificação do empréstimo      |
| loan_amnt                  | Valor do empréstimo solicitado   |
| loan_int_rate              | Taxa de juros                    |
| loan_percent_income        | Percentual da renda comprometido |
| cb_person_default_on_file  | Histórico de inadimplência       |
| cb_person_cred_hist_length | Tempo de histórico de crédito    |
| loan_status                | Variável alvo                    |
| comprometimento_renda      | Variável criada neste projeto    |
```
---

# Etapas Desenvolvidas

## 1. Análise Exploratória dos Dados (EDA)

Nesta etapa foram realizadas:

* análise da estrutura da base;
* identificação dos tipos das variáveis;
* estatísticas descritivas;
* identificação de valores ausentes;
* identificação de registros duplicados;
* análise da distribuição da variável alvo;
* geração de histogramas;
* geração de boxplots;
* mapa de calor da correlação de Pearson.

---

## 2. Tratamento dos Dados

Foram executadas as seguintes etapas:

* remoção de registros duplicados;
* tratamento de valores ausentes;
* substituição dos valores numéricos pela mediana;
* substituição das variáveis categóricas pela moda;
* identificação e tratamento de outliers utilizando o método IQR.

---

## 3. Engenharia de Atributos

Foi criada a variável:

```text
comprometimento_renda =
(loan_amnt / person_income) × 100
```

Essa variável representa o percentual da renda anual comprometido com o empréstimo solicitado.

---

## 4. Preparação dos Dados

Nesta etapa foram aplicadas as seguintes técnicas:

* One-Hot Encoding;
* separação entre variáveis preditoras e variável alvo;
* divisão entre treino e teste utilizando amostragem estratificada;
* balanceamento das classes utilizando SMOTE apenas no conjunto de treinamento;
* padronização dos dados com StandardScaler exclusivamente para o algoritmo KNN.

---

## 5. Modelagem

Foram avaliados dois algoritmos supervisionados:

### K-Nearest Neighbors (KNN)

Foram testados diferentes valores para o parâmetro:

* K = 3
* K = 5
* K = 7
* K = 9

### Árvore de Decisão

Foram avaliadas diferentes profundidades:

* max_depth = 3
* max_depth = 5
* max_depth = 7
* max_depth = None

Os resultados obtidos nos conjuntos de treinamento e teste foram comparados para identificar possíveis sinais de overfitting.

---

## 6. Avaliação

Os modelos foram avaliados utilizando:

* Accuracy
* Precision
* Recall
* F1-Score
* Classification Report
* Matriz de Confusão

Além das métricas, foi realizada uma análise dos impactos dos Falsos Positivos e Falsos Negativos sob a perspectiva do negócio.

---

# Principais Resultados

Após os experimentos, foi possível comparar o desempenho dos modelos KNN e Árvore de Decisão.

O modelo selecionado apresentou melhor equilíbrio entre capacidade de generalização e desempenho no conjunto de teste, reduzindo os riscos associados à concessão de crédito para clientes inadimplentes.

---

# Conclusão

O desenvolvimento deste projeto permitiu aplicar todas as etapas fundamentais de um pipeline de Machine Learning, incluindo limpeza dos dados, engenharia de atributos, preparação da base, treinamento, validação e interpretação dos resultados.

Além do aspecto técnico, o projeto demonstrou a importância de alinhar as métricas dos modelos às necessidades do negócio. Em aplicações financeiras, reduzir a ocorrência de Falsos Negativos é essencial para minimizar prejuízos decorrentes da concessão de crédito a clientes com elevado risco de inadimplência.

---
