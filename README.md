# 🚢 Previsão de Sobrevivência no Titanic

Projeto de Machine Learning desenvolvido com o dataset do Titanic, com o objetivo de analisar os dados dos passageiros e criar modelos capazes de prever a sobrevivência.

O projeto foi desenvolvido como parte dos meus estudos em **Ciência de Dados**, passando por etapas de análise exploratória, tratamento dos dados, engenharia de atributos, treinamento, otimização e avaliação de modelos de Machine Learning.

---

## 📌 Objetivos

- Explorar e compreender os dados do Titanic;
- Realizar análise exploratória dos dados;
- Identificar padrões relacionados à sobrevivência;
- Realizar tratamento e pré-processamento dos dados;
- Criar novas variáveis para melhorar os modelos;
- Treinar diferentes algoritmos de Machine Learning;
- Utilizar `GridSearchCV` para otimização dos modelos;
- Comparar o desempenho dos modelos;
- Criar um `VotingClassifier`;
- Gerar previsões para submissão no Kaggle.

---

## 📊 Sobre o Dataset

O dataset contém informações sobre passageiros do Titanic, incluindo características como:

- Classe do passageiro;
- Sexo;
- Idade;
- Número de familiares;
- Tarifa paga;
- Porto de embarque;
- Número do bilhete;
- Sobrevivência.

A variável **`Survived`** é utilizada como variável alvo:

- `0` → Não sobreviveu
- `1` → Sobreviveu

---

## 🔎 Análise Exploratória

Antes da criação dos modelos, foram realizadas análises para compreender melhor os dados.

Entre as análises realizadas estão:

- Quantidade de sobreviventes;
- Sobreviventes por porto;
- Distribuição das faixas etárias;
- Percentual de sobrevivência por porto;
- Percentual de sobrevivência por classe;
- Percentual de sobrevivência por sexo;
- Relação entre sexo e classe.

Também foram utilizadas visualizações gráficas para facilitar a interpretação dos dados.

---

## 🧹 Tratamento dos Dados

Durante o pré-processamento foram realizadas algumas etapas para preparar os dados para os modelos.

### Remoção de colunas

As colunas com mais de **20% de valores ausentes** foram removidas. Nesse caso, a coluna `Cabin` foi retirada.

Para a modelagem, também foram removidas:

- `PassengerId`
- `Embarked`

### Engenharia de atributos

Foram criadas novas variáveis a partir dos dados existentes, incluindo:

- `familia_tamanho` → tamanho da família do passageiro;
- `esta_sozinho` → indica se o passageiro estava viajando sozinho.

---

## ⚙️ Pré-processamento

Foi utilizado o `ColumnTransformer` juntamente com `Pipeline` do Scikit-learn para organizar o processo de preparação dos dados.

O pré-processamento inclui tratamento das variáveis numéricas e categóricas antes do treinamento dos modelos.

A utilização de pipelines ajuda a manter o processo de transformação dos dados organizado e evita a necessidade de realizar manualmente cada etapa para os diferentes modelos.

---

## 🤖 Modelos Utilizados

Foram treinados e comparados quatro modelos:

### Regressão Logística

Modelo utilizado como uma abordagem inicial para classificação binária.

### Árvore de Decisão

Modelo baseado em regras de decisão construídas a partir das características dos passageiros.

### Random Forest

Conjunto de várias árvores de decisão, buscando melhorar a capacidade de generalização do modelo.

### Voting Classifier

Modelo de ensemble que combina as previsões de diferentes modelos para realizar a classificação final.

---

## 🔧 Otimização dos Modelos

Foi utilizado o **GridSearchCV** para testar diferentes combinações de hiperparâmetros e encontrar configurações mais adequadas para os modelos.

O processo foi aplicado aos modelos:

- Regressão Logística;
- Árvore de Decisão;
- Random Forest;
- Voting Classifier.

---

## 📈 Desempenho dos Modelos

Após o treinamento e otimização, os modelos foram avaliados no conjunto de teste utilizando:

- Acurácia;
- Precisão;
- Recall;
- F1-Score.

| Modelo | Acurácia | Precisão | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Regressão Logística | **0.83** | **0.84** | 0.73 | 0.78 |
| Árvore de Decisão | 0.80 | 0.80 | 0.69 | 0.74 |
| Random Forest | 0.81 | 0.82 | 0.69 | 0.75 |
| Voting Classifier | 0.82 | 0.83 | 0.72 | 0.77 |

Além das métricas, foram utilizadas **matrizes de confusão** para visualizar os acertos e erros de classificação de cada modelo.

> As métricas acima correspondem à avaliação realizada no conjunto de teste utilizado no notebook.

---

## 🌲 Importância das Variáveis

Também foi analisada a importância das características utilizadas pelo modelo de **Random Forest**.

Essa etapa permite observar quais atributos tiveram maior influência nas decisões realizadas pelo modelo.

---

## 🧪 Previsão no Dataset de Teste

Após o treinamento dos modelos, o dataset de teste foi preparado utilizando o mesmo processo de pré-processamento.

Em seguida, o modelo `VotingClassifier` foi utilizado para gerar as previsões.

O resultado final foi salvo no arquivo:

```text
resultado.csv
