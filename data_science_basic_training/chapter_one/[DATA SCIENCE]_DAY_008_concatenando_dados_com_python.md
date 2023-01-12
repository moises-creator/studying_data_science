## 🧑‍💻 Aooba pessoal, tudo bem com vocês?

### 🐳 Hoje iremos aprender como concatenar dados com python:

🎯 **Objetivo:**
- concatenar dados;

#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e métodos que vamos importar e facilitar a escrita de código:

:computer:
```py
import numpy as np
import pandas as pd

from pandas import DataFrame
```

#### 2 - Agora iremos criar duas variáveis, uma recebendo um DataFrame do Pandas com 6 linhas e 6 colunas, preenchendo as células com os valores de 0 a 35,  e outra recebendo um DataFrame do Pandas com 5 linhas e 3 colunas, preenchendo as células com os valores de 0 a 14, em ordem:

:computer:
```py
df = pd.DataFrame(np.arange(36).reshape(6,6))
print(df)


#saida
        0	1	2	3	4	5
0	0	1	2	3	4	5
1	6	7	8	9	10	11
2	12	13	14	15	16	17
3	18	19	20	21	22	23
4	24	25	26	27	28	29
5	30	31	32	33	34	35
```

:computer:
```py
df2 = pd.DataFrame(np.arange(15).reshape(5,3))
print(df2)


#saida
        0	1	2
0	0	1	2
1	3	4	5
2	6	7	8
3	9	10	11
4	12	13	14
```

#### 3 - O método `concat()` junta dados de duas fontes diferentes em uma única tabela. O comportamento padrão é juntar as fontes considerando os índices das colunas:

:computer:
```py
print(pd.concat([df, df2]))


#saida
	0	1	2	3	4	5
0	0       1	2     3.0     4.0     5.0
1       6       7	8     9.0    10.0    11.0
2      12      13      14    15.0    16.0    17.0
3      18      19      20    21.0    22.0    23.0
4      24      25      26    27.0    28.0    29.0
5      30      31      32    33.0    34.0    35.0
0	0	1	2     NaN     NaN     NaN
1	3	4	5     NaN     NaN     NaN
2	6	7	8     NaN     NaN     NaN
3	9      10      11     NaN     NaN     NaN
4      12      13      14     NaN     NaN     NaN
```

#### 4 - E por último,passando o argumento `axis=1` para o método, o Python entende que deve juntar essas fontes usando o índice das linhas de ambas fontes:

:computer:
```py
print(pd.concat([df, df2], axis=1))


#saida
        0	1	2	3	4	5	0	1	2
0	0	1	2	3	4	5     0.0     1.0     2.0
1	6	7	8	9      10      11     3.0     4.0     5.0
2      12      13      14      15      16      17     6.0     7.0     8.0
3      18      19      20      21      22      23     9.0    10.0    11.0
4      24      25      26      27      28      29    12.0    13.0    14.0
5      30      31      32      33      34      35     NaN     NaN     NaN
```


🌊 **Espero que tenham gostado do conteúdo, amanhã iremos aprender como transformar dados!**

🚀 **Vejo vocês amanhã e tenham uma ótima semana!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
