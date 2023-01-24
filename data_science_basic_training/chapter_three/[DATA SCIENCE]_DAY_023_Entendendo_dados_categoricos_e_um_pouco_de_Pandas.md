## 🦀 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### ⛵️ Hoje iremos falar sobre dados categóricos e um pouco de pandas

>📝 **Obs:** _Irei utilizar o jupyter notebook para a fácil visualização dos gráficos, mas fique a vontade para escolher outro ambiente de sua preferência. Uma sugestão caso não conheça nenhum, tem o [colab](https://colab.research.google.com/) do google._


#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e métodos que vamos importar e facilitar a escrita de código:

:computer:
```py
import pandas as pd
import numpy as np
```

📝 **Obs:** 
- _A linha `import pandas as pd` importa a biblioteca pandas para utilizar suas funções para manipular e analisar dados._
- _A linha `import numpy as np` importa a biblioteca nympy para utilizar suas funções para manipular e analisar dados._

<br>
<br>

#### 2 - Após a importação do pandas e numpy, vamos ler um arquivo CSV chamado "mtcars.csv":

>🔍 _Para baixar o arquivo que está sendo usado, clique [aqui](https://drive.google.com/file/d/1Z_B_nGM7O_YfNvtDYLL0PlBHzOX_WmSG/view?usp=sharing)._

:computer:
```py
caminho = 'O-caminho-do-seu-arquivo/mtcars.csv'
carros = pd.read_csv(caminho)
carros.columns = ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'qtd_marchas', 'carb']
carros.index = carros.nomes
```

<br>
<br>

📝 **Obs: O que esse código faz???**
- _O código está definindo uma variável `caminho` que armazena o caminho do arquivo CSV a ser lido, `mtcars.csv`._
- _Ele usa a função `pd.read_csv()` para ler o arquivo e armazenar os dados em um DataFrame chamado `carros`._
- _As colunas do DataFrame são renomeadas através da propriedade `columns` e atribuindo uma lista de novos nomes._
- _O índice do DataFrame é redefinido para ser a coluna `nomes` através da propriedade `index`._
- _Isso faz com que a coluna `nomes` seja usada como índice para o DataFrame, o que pode ser útil para indexação e seleção de linhas específicas._


<br>

#### 3 - Seguindo, vamos criar um novo DataFrame chamado `carros_cat` a partir do DataFrame original `carros` selecionando apenas as colunas especificadas e em seguida visualizar as primeiras linhas:

:computer:
```py
carros_cat = carros[['cyl','vs','am','qtd_marchas','carb']]
carros_cat.head()
```

**Saída do código:**
```py

                   cyl	vs  am	qtd_marchas	carb
nomes					
Mazda RX4	     6	 0   1	          4	   4
Mazda RX4 Wag	     6	 0   1	          4	   4
Datsun 710	     4	 1   1	          4	   1
Hornet 4 Drive	     6	 1   0	          3	   1
Hornet Sportabout    8	 0   0	          3        2
```
<br>
<br>

📝 **Obs: O que esse código faz???**

- _O código está criando um novo DataFrame chamado `carros_cat`._
- _Ele esta selecionando apenas as colunas especificadas `['cyl','vs','am','qtd_marchas','carb']` do DataFrame original `carros` através do operador de indexação `[ ]`._
- _Ele usa colchetes duplos para selecionar múltiplas colunas ao mesmo tempo._
- _O método `.head()` é usado para exibir as primeiras linhas do DataFrame `carros_cat` ou seja, as primeiras 5 linhas das colunas selecionadas._
- _Isso permite obter uma visão geral rápida dos dados das colunas selecionadas._

<br>

#### 4 - Continuando, vamos agrupar o DataFrame `carros_cat` pelo valor da coluna `qtd_marchas` usando o método 'groupby()', utilizar o método '.describe()', e entender a funcionalidade do método '.T':

:computer:
```py
marchas_grupos = carros_cat.groupby('qtd_marchas')
marchas_grupos.describe().T
```
<br>

**Saída do código:**

```py

qtd_marchas             3              4               5
am    count	15.000000      12.000000	5.000000
       mean	 0.000000	0.666667	1.000000
        std	 0.000000	0.492366	0.000000
        min	 0.000000	0.000000	1.000000
        25%	 0.000000	0.000000	1.000000
        50%	 0.000000	1.000000	1.000000
        75%	 0.000000	1.000000	1.000000
        max	 0.000000	1.000000	1.000000
carb  count	15.000000      12.000000	5.000000
       mean	 2.666667	2.333333	4.400000
        std	 1.175139	1.302678	2.607681
        min	 1.000000	1.000000	2.000000
        25%	 2.000000	1.000000	2.000000
        50%	 3.000000	2.000000	4.000000
        75%	 4.000000	4.000000	6.000000
        max	 4.000000	4.000000	8.000000
cyl   count	15.000000      12.000000	5.000000
       mean	 7.466667	4.666667	6.000000
        std	 1.187234	0.984732	2.000000
        min	 4.000000	4.000000	4.000000
        25%	 8.000000	4.000000	4.000000
        50%	 8.000000	4.000000	6.000000
        75%	 8.000000	6.000000	8.000000
        max	 8.000000	6.000000	8.000000
vs    count	15.000000      12.000000	5.000000
       mean	 0.200000	0.833333	0.200000
        std	 0.414039	0.389249	0.447214
        min	 0.000000	0.000000	0.000000
        25%	 0.000000	1.000000	0.000000
        50%	 0.000000	1.000000	0.000000
        75%	 0.000000	1.000000	0.000000
        max	 1.000000	1.000000	1.000000
```

📝 **Obs: O que esse código faz???**

- _O código está agrupando o DataFrame `carros_cat` pelo valor da coluna `qtd_marchas` usando o método `groupby()`._
- _Isso cria grupos de linhas com valores idênticos na coluna `qtd_marchas`._
- _O método `.describe()` é aplicado a cada grupo criado._
- _Ele retorna estatísticas básicas como contagem, média, desvio padrão, valor mínimo e máximo para cada coluna numérica._
- _O método `.T` é usado para transpor o DataFrame, essa ação inverte as linhas e colunas do Dataframe._
- _Isso permite visualizar de maneira mais fácil as estatísticas agrupadas por valor de `qtd_marchas`._

<br>
<br>

#### 5 - Agora, vamos explorar dados categóricos. Para criar uma Serie de dados categóricos, usamos o `pd.Series()` passando um array ou uma série que contém o dado que queremos transformar e o argumento `dtype="category`:

:computer:
```py
carros['grupo'] = pd.Series(carros['qtd_marchas'], dtype="category")
carros['grupo'].dtype
```

**Saída do código:**
```py
category
```

<br>

📝 **Obs: O que esse código faz???**
- _O código está criando uma nova coluna chamada `grupo` no DataFrame `carros`._
- _Essa coluna é definida como uma série, que tem os mesmos valores que a coluna `qtd_marchas`._
- _A série é definida com o tipo de dado `category`, o que significa que os valores são tratados como categorias (ou seja, valores discretos) e não como números._
- _Na segunda linha, a propriedade `.dtype` é usada para verificar o tipo de dado da coluna `grupo`, que deve ser `category`._
- _Isso pode ser útil para economizar espaço em memória e melhorar a performance ao trabalhar com dados categóricos._

<br>

**Vamos ler as primeiras 5 linhas dos valores da coluna `grupo` que são os mesmos da coluna `qtd_marchas` mas agora tratados como categoria:**

:computer:
```py
carros['grupo'].head()
```

**Saída do código:**
```py
nomes
Mazda RX4            4
Mazda RX4 Wag        4
Datsun 710           4
Hornet 4 Drive       3
Hornet Sportabout    3
Name: grupo, dtype: category
Categories (3, int64): [3, 4, 5]
```

**Após a transformar as variáveis em dados categóricos, vamos utilizar o método `.value_counts()`. Este método conta a frequência de cada valor único na coluna 'grupo', e classifica os valores pela contagem `decrescente`. Ele retorna um novo objeto (também uma série) com os valores únicos da coluna `grupo` e suas respectivas contagens:**

:computer:
```py
carros['grupo'].value_counts()
```

**Saída do código:**

```py
3    15
4    12
5     5
Name: grupo, dtype: int64
```

#### 6 - Por último, podemos montar um cruzamento entre váriaveis usando o médodo do Pandas `pd.crosstab()`, assim passando as variáveis que queremos ver no nosso resultado:

:computer:
```py
pd.crosstab(carros['am'], carros['qtd_marchas'])
```
**Saída do código:**
```py

qtd_marchas	3	4	5
am			
        0	15	4	0
        1	0	8	5
```

<br>

📝 **Obs: O que esse código faz???**
- _O código está usando a função `pd.crosstab()` do pacote pandas._
- _Essa função é usada para criar uma tabela de contingência entre duas variáveis categóricas, neste caso `am` e `qtd_marchas` colunas do DataFrame `carros`._
- _A tabela de contingência mostra a frequência de ocorrência de cada combinação de valores entre as duas variáveis._
- _A função retorna uma tabela (DataFrame) com as contagens das combinações de valores._
- _Essa tabela mostra de forma facil de visualizar a relação entre as variaveis `am` e `qtd_marchas`_


#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como calcular o coeficiente de Pearson!

### 🚀 Vejo vocês amanhã, tenham uma ótima semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
