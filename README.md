# One-vs-Rest---Simple_perceptron

Nesse repositório realizei a implementação manual daquele que foi o antecessor das redes neurais modernas: o perceptron.

Utilizei conhecimentos teóricos estudados sobre esse algoritmo juntamente com conhecimentos da biblioteca Numpy para implementar utilizando o paradigma da programação orientada  a objetos, a fim de criar uma abstração do modelo que pudesse ser ajustada para as necessidades específicas.

Sabemos que a rede perceptron possui uma limitação: ela é incapaz de aprender padrões de dados não lineares.

mesmo assim, optei pelo uso do dataset pela grande proximidade de uma estrutura linear nos dados.

Para testar a implementação, optei por utilizar o conjunto de dados Iris, mesmo sabendo que o perceptron é ideal para classificação binária... e aqui temos 3 classes.

Para resolver o problema da classificação multiclasse basicamente utilizei a técnica One vs Rest, muito utilizada em modelos que são originalmente de classificação binária, a técnica consiste em treinar um perceptron para distinguir cada uma das classes, por exemplo:

sabemos que no conjunto de dados iris temos as classes setosa, versicolor e virginica, teriamos aqui então 3 perceptron diferentes, aplicados em um contexto adaptado de classificação binária:

1 perceptron determina se a amostra é setosa ou não
1 perceptron determina se a amostra é versicolor ou não
1 perceptron determina se a amostra é virginica ou não


No entanto, na prática treinei 2 perceptrons, 1 para setosa e outro para virginica, pois são apenas 3 classes.

Obviamente se não é setosa ou virginica ela é versicolor, então para economizar tempo e memória, utilizei apenas 2 modelos.

Essa implementação armazena as métricas em cada uma das épocas (Acurácia, Precisão, Recall e F1-Score) para que seja possível a análise gráfica dos dados.

