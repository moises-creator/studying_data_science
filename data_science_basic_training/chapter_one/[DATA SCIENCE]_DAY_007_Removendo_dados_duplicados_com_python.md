## 🐍 Opa pessoal, tudo bem com vocês?

### 🐨 Hoje iremos aprender como remover dados duplicados com python:

🎯 **Objetivo:**
- remover dados duplicados;


🔍 **Observação:**
- É necessário tomar cuidado ao remover os dados duplicados, tendo como possibilidade de eliminar informações importantes do dataset.

- Nunca poderá aplicar esta função se não souber a ideia completa do que está sendo removido.



#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e métodos que vamos importar e facilitar a escrita de código:

:computer:
```py
import numpy as np
import pandas as pd

from pandas import DataFrame
```

#### 2 - Iremos criar agora um DataFrame do Pandas a partir de um dicionário de dados. O dicionário terá três entradas, cada uma representando uma coluna do DataFrame:

:computer:
```py
dados = {
    'coluna 1': [1, 1, 2, 2, 3, 3, 3],
    'coluna 2': ['a', 'a', 'b', 'b', 'c', 'c', 'c'],
    'coluna 3': ['A', 'A', 'B', 'B', 'C', 'C', 'C'],
}

df = DataFrame(dados)
print(df)


#saida

   coluna 1	coluna 2     coluna 3
0         1	       a	    A
1         1	       a	    A
2         2	       b	    B
3	  2	       b	    B
4	  3	       c	    C
5	  3	       c	    C
6	  3	       c	    C
```

#### 3 - Agora iremos conferir os dados duplicados utilizando o método `.duplicated()` que confere se cada linha é uma duplicata de uma linha anterior e cria uma Serie de valores` True ou False` indicando se a linha é uma linha duplicada ou não no dataframe:

:computer:
```py
print(df.duplicated())

#saida
0    False
1     True
2    False
3     True
4    False
5     True
6     True
dtype: bool
```

#### 4 - Para remover todas as linhas repetidas, usamos o método `.drop_duplicates()`:

:computer:
```py
print(df.drop_duplicates())

#saida

   coluna 1	coluna 2      coluna 3
0	  1	       a	     D
1	  1	       a	     A
2	  2	       b	     B
4	  3	       c	     C

print(df)

    coluna 1	coluna 2    coluna 3
0	   1	       a	   D
1	   1	       a	   A
2	   2	       b	   B
3	   2	       b 	   B
4	   3	       c	   C
5	   3	       c	   C
6	   3	       c	   C
```

**Obs:** _Lembre-se para alterar o objeto ao invés de criar um novo, devemos usar o parâmetro `inplace`, no código ficaria `df.drop_duplicates(inplace=False)`._

#### 5 - Para remover linhas repetidas considerando apenas uma coluna, passamos para o método `.drop_duplicates()` uma lista com o nome da coluna que ele deverá considerar:

:computer:
```py
dados = {
    'coluna 1': [1, 1, 2, 2, 3, 3, 3],
    'coluna 2': ['a', 'a', 'b', 'b', 'c', 'c', 'c'],
    'coluna 3': ['D', 'A', 'B', 'B', 'C', 'C', 'C'],
}

df = DataFrame(dados)
print(df)

#saida

   coluna 1	coluna 2     coluna 3
0	  1	       a            D
1	  1	       a            A
2	  2	       b            B
3	  2	       b            B
4	  3	       c            C
5	  3	       c            C
6	  3	       c            C

#agora passando a coluna como parâmetro
print(df.drop_duplicates(['coluna 3']))

#saida da coluna específica
    coluna 1	coluna 2    coluna 3
0	   1	       a	   D
1	   1	       a	   A
2	   2	       b	   B
4	   3	       c	   C
```


☀️ **Espero que tenham gostado do conteúdo, amanhã iremos aprender como concatenar dados!**

🚀 **Vejo vocês amanhã e tenham um ótimo final de semana!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
