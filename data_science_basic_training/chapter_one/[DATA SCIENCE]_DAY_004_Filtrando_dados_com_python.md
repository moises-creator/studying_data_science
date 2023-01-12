## Fala pessoal, tudo bem com vocês?

### 🧑‍💻 Hoje iremos aprender como filtrar dados utilizando pandas e numpy

:exclamation:**Objetivo:**
- Filtrar dados e extrair resultados


#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e métodos que vamos importar e facilitar a escrita de código:

:computer:
```py
import numpy as np
import pandas as pd
from pandas import Series, DataFrame
```


#### 2 - Em seguida, vamos utilizar como nos posts anteriores o `np.random.seed()`, onde define a semente para o gerador de números aleatórios do numpy. Logo em seguida, vamos criar duas variáveis e utilizar o método DataFrame do pandas:

:computer:
```py
np.random.seed(25)

indice = ['linha 1', 'linha 2', 'linha 3', 'linha 4', 'linha 5', 'linha 6']
colunas = ['coluna 1', 'coluna 2', 'coluna 3', 'coluna 4', 'coluna 5', 'coluna 6']

df = DataFrame(np.random.rand(36).reshape((6,6)),
               index=indice,
               columns=colunas)

print(df)


#saida
	coluna 1	coluna 2	coluna 3	coluna 4	coluna 5	coluna 6
linha 1	0.870124	0.582277	0.278839	0.185911	0.411100	0.117376
linha 2	0.684969	0.437611	0.556229	0.367080	0.402366	0.113041
linha 3	0.447031	0.585445	0.161985	0.520719	0.326051	0.699186
linha 4	0.366395	0.836375	0.481343	0.516502	0.383048	0.997541
linha 5	0.514244	0.559053	0.034450	0.719930	0.421004	0.436935
linha 6	0.281701	0.900274	0.669612	0.456069	0.289804	0.525819

```

#### 3 - Agora, você pode usar operadores de comparação (maior que e menor que) para obter `True` / `False` para todos os registros para indicar a comparação entre cada elemento e o valor de interesse:

:computer:
```py
df < .2

#saida
        coluna 1  coluna 2  coluna 3  coluna 4  coluna 5  coluna 6
linha 1	False	  False	    False     True      False     True
linha 2	False	  False	    False     False     False     True
linha 3	False	  False	    True      False     False     False
linha 4	False	  False	    False     False     False     False
linha 5	False	  False	    True      False     False     False
linha 6	False	  False	    False     False     False     False
```    

#### 4 - Em seguida, você também pode usar operadores de comparação e valores escalares para filtrar apenas aqueles registros que satisfazem a comparação.

:computer:
```py
indice = ['linha 1', 'linha 2', 'linha 3', 'linha 4',
          'linha 5', 'linha 6', 'linha 7', 'linha 8']
series_obj = Series(np.arange(8), index=indice)
filtro = series_obj > 6
print(series_obj[filtro])
```
>linha 8    7
dtype: int64


#### 5 - Por último, você também pode atualizar todos os valores de um conjunto de índices:

```py
series_obj['linha 1', 'linha 5', 'linha 8'] = 8
print(series_obj)
```
>linha 1    8
linha 2    1
linha 3    2
linha 4    3
linha 5    8
linha 6    5
linha 7    6
linha 8    8
dtype: int64


🧐 _Curiosidades: O DataFrame é uma estrutura de dados bidimensional do Python, com linhas e colunas, que é usada para armazenar dados tabulares. Ela é uma das estruturas de dados mais populares do pacote de análise de dados pandas._

**Espero que tenham gostado do conteúdo, amanhã iremos aprender como encontrar e preencher valores em branco!**

🚀 **See you later!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
