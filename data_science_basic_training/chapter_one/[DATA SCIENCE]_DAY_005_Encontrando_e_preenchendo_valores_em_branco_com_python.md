## 🍄 Buenas pessoal, tudo bem com vocês?

### 🔥 Hoje iremos aprender como encontrar e preencher valores em branco

:exclamation:**Objetivo:**
- Encontrar valores em branco e substituir com algum valor;




#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e métodos que vamos importar e facilitar a escrita de código:

:computer:
```py
import numpy as np
import pandas as pd
from pandas import Series, DataFrame
```


#### 2 - O NumPy tem embutido nele um objeto chamado `np.nan` que serve para identificar valores em branco, assim podemos utilizar a nosso favor para colocar valores em branco na variável que iremos criar:

:computer:
```py
em_branco = np.nan

serie = Series(['linha 1', 'linha 2', em_branco, 'linha 4', 'linha 5', 'linha 6', em_branco, 'linha 8'])

print(serie)


#saida
0    linha 1
1    linha 2
2        NaN
3    linha 4
4    linha 5
5    linha 6
6        NaN
7    linha 8
dtype: object
```
**Obs:** _NaN significa not a number_

#### 3 - Em seguida, iremos conhecer o método `.isnull()`, onde retorna valores booleanos (`True` ou `False`) se um item dentro de um objeto Pandas é nulo ou vazio:

:computer:
```py
print(serie.isnull())

#saida
0    False
1    False
2     True
3    False
4    False
5    False
6     True
7    False
dtype: bool
```

#### 4 - Em seguida, vamos criar uma matriz 6x6 de números aleatórios com a biblioteca NumPy, e armazenar esses dados em uma estrutura de dados do Pandas chamada "DataFrame".  em seguida, alterar os valores de algumas células específicas do DataFrame, substituindo-os pelo valor "em_branco":

:computer:
```py
np.random.seed(25)
df = DataFrame(np.random.randn(36).reshape(6,6))
df.loc[3:5, 0] = em_branco
df.loc[1:4, 5] = em_branco
print(df)


#saída
                0	     1	           2	        3	      4	           5
0	 0.228273     1.026890     -0.839585    -0.591182     -0.956888    -0.222326
1	-0.619915     1.837905	   -2.053231	 0.868583     -0.920734          NaN
2	 2.152957    -1.334661	    0.076380	-1.246089      1.202272          NaN
3	      NaN    -0.419678	    2.294842	-2.594487      2.822756	         NaN
4	      NaN    -1.976254	    0.533340	-0.290870     -0.513520	         NaN
5	      NaN    -1.839905	    1.607671	 0.388292      0.399732	    0.405477
```
**Obs:** _O comando `f.loc[3:5, 0] = em_branco` altera os valores das células da linha 3 até a linha 5 da coluna 0 para o valor "em_branco". O comando `f.loc[1:4, 5] = em_branco` altera os valores das células da linha 1 até a linha 4 da coluna 5 para o valor "em_branco"._

#### 5 - O método `.fillna()` encontra os valores nulos do nosso objeto e preenche esses valores com o novo valor que você passar:

:computer:
```py
df_preenchido = df.fillna(0)
print(df_preenchido)

#saida
                0	     1	           2	        3	      4	           5
0	 0.228273     1.026890	   -0.839585	-0.591182     -0.956888	   -0.222326
1	-0.619915     1.837905	   -2.053231	 0.868583     -0.920734	    0.000000
2	 2.152957    -1.334661	    0.076380	-1.246089      1.202272	    0.000000
3	 0.000000    -0.419678	    2.294842	-2.594487      2.822756	    0.000000
4	 0.000000    -1.976254	    0.533340	-0.290870     -0.513520	    0.000000
5	 0.000000    -1.839905	    1.607671	 0.388292      0.399732	    0.405477

```

#### 6 - Por último, você também pode passar um dicionário para o método `.fillna()`. Usando um dicionário, o método entende que cada chave do dicionário corresponde a uma coluna e o seu par o valor a ser substituído na respectiva coluna:

:computer:
```py
dicio = {0: 0.1, 5: 1.25}
df_preenchido = df.fillna(dicio)
print(df_preenchido)

#saida

                0	     1	           2	        3	      4	           5
0	 0.228273     1.026890	   -0.839585	-0.591182     -0.956888	   -0.222326
1	-0.619915     1.837905	   -2.053231	 0.868583     -0.920734	    1.250000
2	 2.152957    -1.334661	    0.076380	-1.246089      1.202272	    1.250000
3	 0.100000    -0.419678	    2.294842	-2.594487      2.822756	    1.250000
4	 0.100000    -1.976254	    0.533340	-0.290870     -0.513520	    1.250000
5	 0.100000    -1.839905	    1.607671	 0.388292      0.399732	    0.405477

```

☀️ **Espero que tenham gostado do conteúdo, amanhã iremos aprender como contar e remover valores em branco!**

🚀 **See you later!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
