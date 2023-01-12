## 🍄 Saudações pessoal, tudo bem com vocês?

### 🦊 Hoje iremos aprender como transformar dados com python:

🎯 **Objetivo:**
 - Transformar dados;


#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e métodos que vamos importar e facilitar a escrita de código:

:computer:
```py
import numpy as np
import pandas as pd

from pandas import Series, DataFrame
```

#### 2 - Segundo, vamos criar um DataFrame do Pandas com 6 linhas e 6 colunas, preenchendo as células com os valores de 0 a 35, em ordem:

:computer:
```py
df = pd.DataFrame(np.arange(36).reshape(6,6))
print(df)

#saida
	0	1	2	3	4	5
        
0	0	1	2	3	4	5
1	6	7	8	9      10      11
2      12      13      14      15      16      17
3      18      19      20      21      22      23
4      24      25      26      27      28      29
5      30      31      32      33      34      35
```

#### 3 - Para remover linhas do nosso DataFrame podemos usar o método `.drop()` e indicando os índices para as linhas ou colunas que queremos remover.

**Obs:** 
- _Lembre-se, para alterar o objeto ao invés de criar um novo, devemos usar o parâmetro `inplace`;_
- _para remover colunas, lembre de usar o argumento `axis=1`;_
- _Tome cuidado ao remover dados valiosos._

:computer:
```py
df.drop([0,2], inplace=True)
print(df)

#saida
	 0	 1	 2	 3	 4	 5
         
1	 6	 7	 8	 9	10	11
3	18	19	20	21	22	23
4	24	25	26	27	28	29
5	30	31	32	33	34	35
```

:computer:
```py
print(df.drop([0,2], axis=1))

#saida
         1	 3	 4	 5
         
1	 7	 9	10	11
3	19	21	22	23
4	25	27	28	29
5	31	33	34	35
```

#### 4 - Agora vamos criar uma série do Pandas com os valores de 0 a 5, em ordem, utilizando a biblioteca numpy.

:computer:
```py
serie = Series(np.arange(6))
serie.name = "variavel_somada"
print(serie)

#saida
0    0
1    1
2    2
3    3
4    4
5    5
Name: variavel_somada, dtype: int32
```

**Obs:** _O comando `serie.name = "variavel_somada"` atribui o nome `"variavel_somada"` à série. Isso permite que você identifique a série mais facilmente quando ela for exibida ou usada em operações futuras._

#### 5 - Agora podemos usar o método `.join()` para unir dois datasets usando o índice das linhas ou usando uma coluna como chave:

:computer:
```py
variavel_somada = DataFrame.join(df, serie)
print(variavel_somada)

#saida
	 0	 1	 2	 3	 4 	 5	variavel_somada
         
0	 0	 1	 2	 3	 4	 5	              0
1	 6	 7	 8	 9	10	11	              1
2	12	13	14	15	16	17	              2
3	18	19	20	21	22	23	              3
4	24	25	26	27	28	29	              4
5	30	31	32	33	34	35	              5
```

#### 5 - Por último não menos importante, para ordernar os valores das linhas de um DataFrame, de forma ascendente ou descentende, usamos o método `.sort_values()` passando o índice das colunas para ordenar os valores:

:computer:
```py
df_ordenado = variavel_somada.sort_values(by=['variavel_somada'], ascending=[False])
print(df_ordenado)

#saida
         0	 1	 2	 3	 4	 5     variavel_somada
         
5	30	31	32	33	34	35	             5
4	24	25	26	27	28	29	             4
3	18	19	20	21	22	23	             3
2	12	13	14	15	16	17	             2
1	 6	 7	 8	 9	10	11	             1 
0	 0	 1	 2 	 3	 4 	 5	             0 
```

**Obs:** _O argumento `ascending` especifica se a ordenação deve ser crescente ou decrescente. Como o valor é `False`, a ordenação será decrescente._

🌊 **Espero que tenham gostado do conteúdo, amanhã iremos aprender sobre agrumpamentos e agregações dos dados. Assim finalizando o capítulo 1 da nossa jornada!**

🚀 **Vejo vocês amanhã e tenham uma ótima semana!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
