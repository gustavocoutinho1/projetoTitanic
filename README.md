# 🚢 Projeto Titanic --- Machine Learning

Projeto de **Machine Learning** desenvolvido em Python utilizando o
famoso dataset do **Titanic disponibilizado no Kaggle**.

O objetivo é analisar os dados dos passageiros e criar modelos capazes
de prever se um passageiro **sobreviveu ou não ao naufrágio**.

Este projeto foi desenvolvido como parte dos meus estudos em **Ciência
de Dados**, com foco em aprender, na prática, etapas de análise de
dados, pré-processamento, treinamento, otimização e avaliação de modelos
de classificação.

## 📌 Objetivos

-   Explorar e entender os dados do Titanic;
-   Identificar e tratar valores ausentes;
-   Criar novas variáveis a partir dos dados existentes;
-   Preparar variáveis numéricas e categóricas para Machine Learning;
-   Treinar diferentes modelos de classificação;
-   Otimizar hiperparâmetros utilizando `GridSearchCV`;
-   Comparar o desempenho dos modelos;
-   Utilizar um `VotingClassifier` para combinar diferentes modelos;
-   Gerar previsões para os dados de teste e salvar o resultado em um
    arquivo CSV.

## 📊 Sobre os dados

O projeto utiliza dados do Titanic obtidos a partir do Kaggle.

Entre as informações utilizadas estão:

-   `PassengerId` --- identificador do passageiro;
-   `Pclass` --- classe do passageiro;
-   `Name` --- nome;
-   `Sex` --- sexo;
-   `Age` --- idade;
-   `SibSp` --- número de irmãos/cônjuges a bordo;
-   `Parch` --- número de pais/filhos a bordo;
-   `Ticket` --- número da passagem;
-   `Fare` --- tarifa paga;
-   `Cabin` --- cabine;
-   `Embarked` --- porto de embarque;
-   `Survived` --- variável que indica se o passageiro sobreviveu.

## 🔎 Análise e preparação dos dados

Inicialmente, foi realizada uma exploração dos dados utilizando
**Pandas**, verificando:

-   Estrutura e tamanho do dataset;
-   Tipos das variáveis;
-   Estatísticas descritivas;
-   Valores ausentes;
-   Distribuição de algumas características dos passageiros.

Também foram criadas visualizações para analisar relações entre
sobrevivência e variáveis como:

-   Sexo;
-   Classe;
-   Idade;
-   Porto de embarque;
-   Sexo e classe.

Além disso, foram criadas duas novas variáveis:

-   `familia_tamanho` --- soma de `SibSp` e `Parch`, acrescida de 1 para
    representar o próprio passageiro;
-   `esta_sozinho` --- indica se o passageiro estava viajando sozinho.

## ⚙️ Pré-processamento

O pré-processamento foi estruturado utilizando `Pipeline` e
`ColumnTransformer` do Scikit-learn.

### Variáveis numéricas

Foi utilizado:

-   `SimpleImputer` com estratégia de mediana para valores ausentes;
-   `StandardScaler` para padronização.

### Variáveis categóricas

Foi utilizado:

-   `SimpleImputer` com a categoria mais frequente;
-   `OneHotEncoder` para transformar variáveis categóricas em valores
    numéricos.

Essa estrutura permite que o pré-processamento seja realizado junto com
o treinamento dos modelos.

## 🤖 Modelos utilizados

Foram treinados e comparados três modelos principais:

### Regressão Logística

Utilizada como um modelo de classificação baseado em uma relação entre
as variáveis de entrada e a probabilidade de sobrevivência.

### Árvore de Decisão

Modelo baseado em divisões sucessivas dos dados para realizar a
classificação.

### Random Forest

Conjunto de várias árvores de decisão, buscando melhorar a capacidade de
generalização do modelo.

Também foi utilizado um:

### Voting Classifier

O `VotingClassifier` combina as previsões dos modelos de Regressão
Logística, Árvore de Decisão e Random Forest.

## 🔧 Otimização dos modelos

Foi utilizado o `GridSearchCV` para testar diferentes combinações de
hiperparâmetros e encontrar configurações com melhor desempenho durante
a validação cruzada.

Os modelos foram avaliados principalmente utilizando a métrica:

**Accuracy (Acurácia)**

Também foram analisadas:

-   Precisão;
-   Recall;
-   F1-Score;
-   Matriz de confusão.

## 📈 Resultados

Os resultados obtidos no conjunto de teste foram:

  Modelo                  Acurácia   Precisão   Recall     F1
  --------------------- ---------- ---------- -------- ------
  Regressão Logística         0.82       0.80     0.71   0.75
  Árvore de Decisão           0.78       0.75     0.65   0.70
  Random Forest               0.82       0.80     0.70   0.74
  Voting Classifier           0.81       0.76     0.74   0.75

Na validação cruzada realizada durante o `GridSearchCV`, a Random Forest
apresentou o maior resultado entre os três modelos individuais, com
aproximadamente **0.83 de acurácia média**.

Os resultados acima representam as avaliações realizadas no notebook e
podem variar caso o processamento, os dados ou os parâmetros sejam
alterados.

## 📁 Estrutura do projeto

``` text
projetoTitanic/
│
├── projeto.ipynb
├── README.md
├── resultado.csv
│
└── data/
    ├── test-selected-columns.csv
    └── train.csv
```

### Arquivos

**`projeto.ipynb`**\
Notebook principal contendo a análise dos dados, visualizações,
pré-processamento, treinamento, otimização e avaliação dos modelos.

**`resultado.csv`**\
Arquivo gerado pelo projeto contendo as previsões realizadas para os
dados de teste. O arquivo possui as colunas `PassengerId` e `Survived`.

**`data/train.csv`**\
Dataset utilizado para análise e treinamento dos modelos.

**`data/test-selected-columns.csv`**\
Dados utilizados para realizar as previsões finais.

## 🛠️ Tecnologias utilizadas

-   Python
-   Pandas
-   NumPy
-   Scikit-learn
-   Matplotlib
-   Seaborn
-   DuckDB
-   Jupyter Notebook

## 📚 O que aprendi com este projeto

Este projeto foi desenvolvido durante o início da minha graduação em
**Ciência de Dados** e teve como objetivo principalmente colocar em
prática conceitos estudados.

Entre os principais aprendizados estão:

-   Manipulação de dados com Pandas;
-   Exploração e análise de datasets;
-   Consultas utilizando DuckDB;
-   Visualização de dados;
-   Tratamento de valores ausentes;
-   Engenharia de atributos;
-   `Pipeline` e `ColumnTransformer`;
-   One-Hot Encoding;
-   Padronização de dados;
-   Treinamento de modelos de classificação;
-   Otimização de hiperparâmetros;
-   Validação cruzada;
-   Avaliação de modelos de Machine Learning.

> **Observação:** este é um projeto de estudos e faz parte do meu
> processo de aprendizado em Ciência de Dados. O objetivo principal é
> demonstrar a aplicação prática dos conceitos estudados, e não apenas
> obter a maior acurácia possível.
