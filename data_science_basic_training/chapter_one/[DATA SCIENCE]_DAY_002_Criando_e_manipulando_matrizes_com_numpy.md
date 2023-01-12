## Fala pessoal, tudo bem com vocês?

### 👨‍💻 Hoje irei falar sobre matrizes, um conjunto de dados organizados em linhas e colunas. Basicamente pode ser representada por uma lista de listas.

:exclamation: **Objetivo:**
- Manipular uma matriz usando numpy;


#### 1 - Primeiro, vamos importar a biblioteca numpy e atribuir um apelido:

:computer:
```import numpy as np```

#### 2 - Agora, iremos utilizar o método set_printoptions como opção de formatação, para o número de casas decimais exibidas:

:computer:
```np.set_printoptions(precision=2)```

#### 3 - Criaremos agora uma variável utilizando o método arange do numpy, onde é usado para criar um array contendo uma sequência de números. Ele funciona de forma semelhante à função range do Python, mas ao invés de retornar uma sequência de números, ele retorna um array numpy. 

:computer:
```a = np.arange(3)```
```print(a)```
>array([0, 1, 2])
       

#### 4 - Vamos criar nossa segunda variável com uma matriz tridimensional usando a biblioteca numpy. O método array é usado para criar uma matriz a partir de uma lista de listas. 

:computer:
```aa = np.array([[2., 4., 6.], [1., 3., 5.], [10., 20., 30.]])```
```print(aa)```
>array([
       [ 2.,  4.,  6.],
       [ 1.,  3.,  5.],
       [10., 20., 30.]
       ])  
      
#### Por último, vamos utilizar os principais métodos aritméticos da matemática para manipular as matrizes:

_multiplicando a variável 'a' com a 'aa', ambas sendo diferente, uma sendo unidimensional e a outra matriz bidimensional, podemos obter o seguinte resultado:_

:computer:
```print(a * aa)```
>array([
       [ 0.,  4., 12.],
       [ 0.,  3., 10.],
       [ 0., 20., 60.]
       ])

_Neste caso abaixo, a chamada np.arange(9) cria uma matriz unidimensional com nove elementos. Agora com método 'reshape', podemos alterar a forma da matriz passando os parâmetros linha e coluna como valor, neste caso, passamos (3, 3)._

:computer:
```bb = np.arange(9).reshape((3,3))```
```print(bb)```
>array([
       [0, 1, 2],
       [3, 4, 5],
       [6, 7, 8]
       ])

_Por último, vamos explorar o método 'dot' do numpy, onde é usado para calcular a multiplicação matricial de duas matrizes com as mesmas quantidades de linhas e colunas._

:computer:
```print(np.dot(aa, bb))```
>array([
       [ 48.,  60.,  72.],
       [ 39.,  48.,  57.],
       [240., 300., 360.]
       ])

:sunny: **Espero que tenham gostado do conteúdo, nada muito complexo, tentando passar da forma mais clara possível!**

**Vejo vocês amanhã com conteúdo sobre valores numéricos...**

🚀 **See you later!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
