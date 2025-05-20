# One-vs-Rest — Simple Perceptron

Neste repositório, realizei a implementação manual daquele que foi o antecessor das redes neurais modernas: o **Perceptron**.

Utilizei conhecimentos teóricos estudados sobre esse algoritmo juntamente com a biblioteca **NumPy**, adotando o paradigma da **Programação Orientada a Objetos**. O objetivo foi criar uma abstração do modelo que pudesse ser ajustada para diferentes necessidades.

## Limitações do Perceptron

Sabemos que a rede Perceptron possui uma limitação importante: ela é **incapaz de aprender padrões de dados não lineares**. Ainda assim, optei por utilizar o **conjunto de dados Iris** devido à sua estrutura relativamente próxima de uma separação linear entre as classes.

## Classificação Multiclasse com One-vs-Rest

O Perceptron é naturalmente um classificador **binário**. Para resolver o problema da **classificação multiclasse** (já que o dataset Iris possui **três classes**: *setosa*, *versicolor* e *virginica*), utilizei a técnica **One-vs-Rest (OvR)**.

Essa técnica é amplamente utilizada para adaptar classificadores binários a tarefas multiclasse. Ela consiste em treinar um modelo para cada classe, distinguindo se a amostra pertence ou não a ela. Por exemplo:

- Um Perceptron determina se a amostra é *setosa* ou não.
- Um Perceptron determina se a amostra é *versicolor* ou não.
- Um Perceptron determina se a amostra é *virginica* ou não.

No entanto, **na prática treinei apenas dois modelos**: um para *setosa* e outro para *virginica*. Isso porque, como temos três classes, podemos inferir que, se a amostra não for *setosa* nem *virginica*, então ela é *versicolor*. Com isso, economizamos tempo e memória.

## Métricas e Visualização

Durante o treinamento, a implementação **armazena as métricas em cada época**:

- Acurácia  
- Precisão  
- Recall  
- F1-Score

Essas métricas são armazenadas para possibilitar **análises gráficas e comparativas do desempenho do modelo** ao longo do tempo.

---

Sinta-se à vontade para explorar o código e adaptá-lo para outras bases de dados ou aplicações de aprendizado supervisionado com modelos lineares.
