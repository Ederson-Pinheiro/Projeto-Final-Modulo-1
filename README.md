# Projeto-Final-Modulo-1
# Sistema de Predição de Risco de Crédito com Machine Learning

## Descrição

Este projeto tem como objetivo desenvolver um pipeline completo de Machine Learning capaz de prever a probabilidade de inadimplência de clientes que solicitam empréstimos.

Foram aplicadas técnicas de Análise Exploratória de Dados (EDA), tratamento e preparação dos dados, engenharia de atributos, balanceamento das classes e treinamento de modelos supervisionados utilizando KNN e Árvore de Decisão.

---

## Objetivo

Construir um modelo preditivo que auxilie instituições financeiras na tomada de decisão sobre concessão de crédito, reduzindo riscos de inadimplência.

---

## ``Problema de Negócio``

Conceder crédito para clientes inadimplentes gera prejuízos financeiros.

Negar crédito para bons clientes reduz a receita da instituição.

O objetivo do modelo é minimizar principalmente os falsos negativos.

---

## ``Tecnologias utilizadas``

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Imbalanced-Learn (SMOTE)

---

## ``Dicionário de Dados``

| Coluna | Descrição |
|---------|-----------|
| person_age | Idade do cliente |
| person_income | Renda anual |
| person_home_ownership | Situação da moradia |
| person_emp_length | Tempo de emprego |
| loan_intent | Finalidade do empréstimo |
| loan_grade | Classificação do empréstimo |
| loan_amnt | Valor solicitado |
| loan_int_rate | Taxa de juros |
| loan_percent_income | Percentual da renda comprometido |
| cb_person_default_on_file | Histórico de inadimplência |
| cb_person_cred_hist_length | Tempo de histórico de crédito |
| loan_status | Variável alvo |
| comprometimento_renda | Nova variável criada |

---

## Etapas do Projeto

- Análise Exploratória (EDA)
- Tratamento de Dados
- Engenharia de Atributos
- One-Hot Encoding
- Balanceamento com SMOTE
- StandardScaler
- KNN
- Árvore de Decisão
- Avaliação dos Modelos

---

## Como executar

Clone o projeto

```bash
git clone https://github.com/SEU_USUARIO/projeto-credito.git
```

Instale as dependências

```bash
pip install -r requirements.txt
```

Execute

```bash
jupyter notebook
```

Abra

```
notebook.ipynb
```

---

## Principais Resultados

Foram comparados dois algoritmos supervisionados:

- KNN
- Árvore de Decisão

Após otimização dos hiperparâmetros, a Árvore de Decisão apresentou melhor capacidade de generalização, menor overfitting e melhor equilíbrio entre precisão e recall.

---

## Conclusão

A Árvore de Decisão foi recomendada para implantação devido ao melhor desempenho na identificação de clientes inadimplentes, reduzindo os riscos financeiros associados à concessão de crédito.
