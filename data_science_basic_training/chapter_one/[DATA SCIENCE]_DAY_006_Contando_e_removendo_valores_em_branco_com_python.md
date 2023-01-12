## 🐍 Faaala pessoal, tudo bem com vocês?

### 🐱 Hoje iremos aprender como contar e remover valores em branco

🎯 **Objetivo:**
- Contar valores em branco e removê-los;


#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e métodos que vamos importar e facilitar a escrita de código:

:computer:
```py
import numpy as np
import pandas as pd
from pandas import Series, DataFrame
```

#### 2 - Iremos agora criar uma variável chamada `em_branco` que irá armanezar o método `.nan` do numpy, onde iremos utilizar para substituir dados com valores NaN(Not a Number). E logo em seguida criar uma matriz 6x6 de números aleatórios com a biblioteca NumPy, e armazenar esses dados em um DataFrame,onde vamos alterar os valores de algumas células específicas do DataFrame, substituindo-os pelo valor NaN.

:computer:
```py
em_branco = np.nan
np.random.seed(25)
df = DataFrame(np.random.randn(36).reshape(6,6))
df.loc[3:5, 0] = em_branco
df.loc[1:4, 5] = em_branco
print(df)

#saida
          0	       1	   2	        3	     4	          5
0  0.228273	1.026890   -0.839585    -0.591182    -0.956888    -0.222326
1 -0.619915     1.837905   -2.053231	 0.868583    -0.920734          NaN
2  2.152957    -1.334661    0.076380	-1.246089     1.202272          NaN
3	NaN    -0.419678    2.294842	-2.594487     2.822756	        NaN
4	NaN    -1.976254    0.533340	-0.290870    -0.513520	        NaN
5	NaN    -1.839905    1.607671	 0.388292     0.399732     0.405477
```

#### 3 - Para calcular a quantidade de valores nulos que o nosso DataFrame tem por coluna, podemos usar o método `.isnull()`, e então usar o método `.sum()` a partir da matriz de valores Booleanos:

:computer:
```py
qtd_nulo = df.isnull().sum()
print(qtd_nulo)

#saida

0    3
1    0
2    0
3    0
4    0
5    4
dtype: int64
```

#### 4 - Para identificar e remover as linhas que contém qualquer valor nulo, usamos o método `.dropna()`:

**Obs:** _Se você quiser remover as colunas que apresentam valores nulos, basta passar `axis=1` como argumento para o método para que ele considere colunas ao invés de linhas._

:computer:
```py
df_limpo = df.dropna(axis=1)
print(df_limpo)

#saida
               1               2	       3	       4
0	1.026890       -0.839585       -0.591182       -0.956888
1	1.837905       -2.053231        0.868583       -0.920734
2      -1.334661	0.076380       -1.246089	1.202272
3      -0.419678	2.294842       -2.594487	2.822756
4      -1.976254	0.533340       -0.290870       -0.513520
5      -1.839905	1.607671	0.388292	0.399732
```

☀️ **Espero que tenham gostado do conteúdo, amanhã iremos aprender como remover dados duplicados!**

🚀 **Vejo vocês amanhã e tenham um ótimo final de semana!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
