# 🧠 One-vs-Rest — Simple Perceptron

Neste repositório, realizei a implementação manual daquele que foi o antecessor das redes neurais modernas: o **Perceptron**.

Utilizei conhecimentos teóricos estudados sobre esse algoritmo juntamente com a biblioteca **NumPy**, adotando o paradigma da **Programação Orientada a Objetos**. O objetivo foi criar uma abstração do modelo que pudesse ser ajustada para diferentes necessidades.

---

## ⚠️ Limitações do Perceptron

A rede Perceptron possui uma limitação importante: ela é **incapaz de aprender padrões de dados não lineares**.

Ainda assim, optei por utilizar o **conjunto de dados Iris** devido à sua estrutura relativamente próxima de uma separação linear entre as classes.

---

## 🔄 Classificação Multiclasse com One-vs-Rest

O Perceptron é naturalmente um classificador **binário**. Para resolver o problema da **classificação multiclasse** (já que o dataset Iris possui três classes: *setosa*, *versicolor* e *virginica*), utilizei a técnica **One-vs-Rest (OvR)**.

Essa técnica consiste em treinar um modelo para cada classe, distinguindo se a amostra pertence ou não a ela. Por exemplo:

- 🟢 Um Perceptron determina se a amostra é *setosa* ou não.
- 🔵 Um Perceptron determina se a amostra é *versicolor* ou não.
- 🔴 Um Perceptron determina se a amostra é *virginica* ou não.

> ⚙️ **Na prática, treinei apenas dois modelos**: um para *setosa* e outro para *virginica*.  
> Se a amostra não for *setosa* nem *virginica*, ela é *versicolor*.  
> Essa abordagem economiza **tempo e memória**.

---

## 📊 Métricas e Visualização

Durante o treinamento, a implementação **armazena as métricas em cada época**, possibilitando análises gráficas e comparativas do desempenho do modelo.

Métricas salvas:
- ✅ Acurácia  
- 📌 Precisão  
- 🔁 Recall  
- 🎯 F1-Score

---

## 🧩 Funcionamento do Perceptron

![Rede Perceptron](./img/perceptron.png)

Para entender o Perceptron, é importante compreender primeiro o conceito de **neurônio artificial**. Nosso cérebro é composto por bilhões de neurônios conectados. O neurônio artificial é uma **abstração matemática** desses neurônios biológicos. Quando interligados, esses neurônios artificiais formam uma **rede neural**.

### 🧱 Estrutura do Perceptron

1. **Recebe entradas** (valores numéricos dos dados)
2. Cada entrada é **multiplicada por um peso** (importância da informação)
3. Soma-se um valor chamado **bias**, que desloca a função de ativação
4. O resultado passa por uma **função de ativação**

> 🧮 **Função degrau**:
> - Se o valor > 0 → saída = 1  
> - Caso contrário → saída = 0

---

### ⚙️ Parâmetros importantes

| Parâmetro          | Função                                                                 |
|--------------------|------------------------------------------------------------------------|
| **Pesos**          | Representam a importância de cada entrada                              |
| **Bias**           | Valor constante que desloca a função de ativação                       |
| **Taxa de aprendizado** | Define a velocidade de aprendizado do modelo                        |

- Taxa **alta**: aprendizado rápido, risco de **overfitting**
- Taxa **baixa**: aprendizado lento, risco de **underfitting**

---

### 🔁 Processo de Aprendizado

Durante o treinamento:

- Pesos iniciados com **valores pequenos aleatórios**
- Bias geralmente começa como **zero**
- Para cada amostra:

```text
1. resultado = soma(peso * entrada) + bias
2. aplica função de ativação
3. erro = valor_esperado - valor_previsto
4. novo_peso = peso_antigo + taxa_aprendizado * erro * entrada
5. novo_bias = bias_antigo + taxa_aprendizado * erro
