## Fala pessoal, tudo tranks?

### Hoje irei falar sobre manipulação de dados utilizando pandas e numpy

:exclamation:**Objetivo:**
- Selecionar dados e gerar valores 


#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e médotos que vamos importar e facilitar a escrita de código:

:computer:
```py
import numpy as np
import pandas as pd
from pandas import Series, DataFrame
```


#### 2 - Em seguida, vamos criar dados utilizando o método arange para gerar valores em um intervalo que retorna um array unidimensional:

:computer:
```py
dados = np.arange(8)
print(dados)
```
>array([0, 1, 2, 3, 4, 5, 6, 7])

#### 3 - Agora iremos utilizar o método reshape para remodelar o formato de um array. Se nós temos um array unidimensional com 8 itens, podemos regorganizá-lo em um conjunto de arrays de dois itens cada. Assim trasnformando um array em uma matriz.

:computer:
```py
print(np.arange(8).reshape((4, 2)))
```
>array([
       [0, 1],
       [2, 3],
       [4, 5],
       [6, 7]
       ])
       


#### 4 - Utilizando o método Series, podemos armazenar dados de qualquer tipo (inteiro, string, float, objetos python, etc.). Os rótulos dos eixos são chamados coletivamente de índices. Primeiro, vamos criar uma variável chamada indice e armazenar valores dentro dela.

:computer:
```py
indice = ['linha 1', 'linha 2', 'linha 3', 'linha 4', 'linha 5', 'linha 6', 'linha 7', 'linha 8']
serie = Series(np.arange(8), index=indice)
print(serie)
```
>linha 1    0
linha 2    1
linha 3    2
linha 4    3
linha 5    4
linha 6    5
linha 7    6
linha 8    7
dtype: int64

Espero que tenham gostado do conteúdo, até amanhã!

🚀 **See you later!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
