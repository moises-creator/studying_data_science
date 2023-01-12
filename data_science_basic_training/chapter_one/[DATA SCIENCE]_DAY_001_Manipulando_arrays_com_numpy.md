## Fala pessoal, tudo bem com vocês? Feliz ano novo! 

:bell: Hoje vamos dar início nessa jornada dos dados, começando a utilizar uma biblioteca bem requisitada chamada Numpy.

:exclamation: **Objetivo:**
- Manipular um array usando numpy;


1 - Primeiro, vamos importar a biblioteca numpy e o randn(gera números aleatórios a partir de uma distribuição normal ):

:computer:
```import numpy as np```
```from numpy.random import randn```

2 - Agora, iremos utilizar o método set_printoptions como opção de formatação, para o número de casas decimais exibidas:

:computer:
```np.set_printoptions(precision=2)```

3 - Criaremos agora uma variável utilizando o método arange do numpy, onde é usado para criar um array contendo uma sequência de números. Ele funciona de forma semelhante à função range do Python, mas ao invés de retornar uma sequência de números, ele retorna um array NumPy. 

:computer:
```a = np.arange(3)```
```a```
>array([0, 1, 2])
       

4 - Vamos criar nossa segunda variável com uma matriz tridimensional usando a biblioteca NumPy. O método array do NumPy é usado para criar uma matriz a partir de uma lista de listas. 

:computer:
```aa = np.array([[2., 4., 6.], [1., 3., 5.], [10., 20., 30.]])```
```aa```
>array([
       [ 2.,  4.,  6.],
       [ 1.,  3.,  5.],
       [10., 20., 30.]
       ])


4 - Agora iremos utilizar o método random.seed do NumPy, onde é usado para definir a "semente" do gerador de números aleatórios do NumPy. Isso é útil porque, embora os números gerados pelo gerador de números aleatórios pareçam ser aleatórios, eles são gerados a partir de um algoritmo determinístico.

E logo em seguida criaremos uma segunda variável com o método randn para para gerar números aleatórios:

:computer:
```np.random.seed(25)```
```b = randn(6)```
>array([ 0.22827309,  1.0268903 , -0.83958485, -0.59118152, -0.9568883 ,
       -0.22232569])

5 - Criaremos agora uma variável utilizando o método arange do numpy, onde é usado para criar um array contendo uma sequência de números. Ele funciona de forma semelhante à função range do Python, mas ao invés de retornar uma sequência de números, ele retorna um array NumPy.

:computer:
```c = np.arange(1, 35)```
>array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17,
       18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34])
       
       
Por último, vamos brincar com as variáveis utilizando os principais métodos aritméticos da matemática:

```a + b```
>array([1.23, 3.03, 2.16, 3.41, 4.04, 5.78])

```a * 10```
>array([10, 20, 30, 40, 50, 60])

```a / b```
>array([  4.38,   1.95,  -3.57,  -6.77,  -5.23, -26.99])

```a - b```
>array([0.77, 0.97, 3.84, 4.59, 5.96, 6.22])


:sunny: Espero que tenham gostado do conteúdo, é simples, mas juntos somos a força!
Vejo vocês amanhã com conteúdo sobre matrizes... 

:milky_way: See you later!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
