## 🐢 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 🎯 Hoje iremos falar sobre desvio padrão, variância, contagem de valores e descritivo estatístico.

>📝 **Obs:** _Irei utilizar o jupyter notebook para a fácil visualização dos gráficos, mas fique a vontade para escolher outro ambiente de sua preferência. Uma sugestão caso não conheça nenhum, tem o [colab](https://colab.research.google.com/) do google._


#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas e métodos que vamos importar e facilitar a escrita de código:

:computer:
```py
import pandas as pd
```

📝 **Obs:** 
- _A linha `import pandas as pd` importa a biblioteca pandas para utilizar suas funções para manipular e analisar dados._

<br>
<br>

#### 2 - Após a importação do pandas, vamos ler um arquivo CSV chamado "mtcars.csv" e através dos dados obtidos, vamos ler os dados iniciais:

>🔍 _Para baixar o arquivo que está sendo usado, clique [aqui](https://drive.google.com/file/d/1Z_B_nGM7O_YfNvtDYLL0PlBHzOX_WmSG/view?usp=sharing)._

:computer:
```py
caminho = 'O-caminho-do-seu-arquivo/mtcars.csv'
carros = pd.read_csv(caminho)
carros.columns = ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'qtd_marchas', 'carb']

carros.head()
```
<br>

**Saída do código:**
```py
	Unnamed: 0	    mpg	     cyl      disp      hp      drat      wt	  qsec      vs      am      gear      carb
        
0	Mazda RX4	    21.0     6	      160.0	110	3.90	  2.620	  16.46     0       1	    4	      4
1	Mazda RX4 Wag	    21.0     6	      160.0	110	3.90	  2.875	  17.02     0	    1	    4	      4
2	Datsun 710	    22.8     4	      108.0	93	3.85	  2.320	  18.61     1	    1	    4	      1
3	Hornet 4 Drive	    21.4     6	      258.0	110	3.08	  3.215	  19.44     1	    0	    3	      1
4	Hornet Sportabout   18.7     8	      360.0	175	3.15	  3.440	  17.02     0	    0	    3	      2
```
<br>
<br>

📝 **Obs: O que esse código faz???**
- _O caminho do arquivo é especificado como uma variável chamada `caminho`_
- _O arquivo é lido usando a função `pd.read_csv` e armazenado em uma variável chamada `carros`_
- _As colunas do conjunto de dados são renomeadas para nomes mais significativos usando a propriedade `columns`._
- _O método `head` é usado para exibir as primeiras linhas do conjunto de dados._

<br>

#### 3 - Iremos abordar o tema `Desvio Padrão`,onde é utilizado como uma medida de dispersão estatística que indica o quão longe os valores estão da média (ou a tendência central) de um conjunto de dados: 

:computer:
```py
carros.std()
```

<br>

**Saída do código:**
```py
mpg              6.026948
cyl              1.785922
disp           123.938694
hp              68.562868
drat             0.534679
wt               0.978457
qsec             1.786943
vs               0.504016
am               0.498991
qtd_marchas      0.737804
carb             1.615200
dtype: float64
```

<br>
<br>

📝 **Obs: O que esse código faz???**
- _O código está usando o método `.std()` do pacote pandas_
- _Quanto maior o desvio padrão, maior a variabilidade dos dados._
- _Esse método calcula o desvio padrão para cada coluna numérica do DataFrame._
- _O resultado final é retornado como um novo DataFrame ou Série com esses valores._


#### 4 - Seguindo, vamos ver Variância, onde é similar ao desvio padrão, mas é expressa em termos dos quadrados dos valores, ao invés da raiz quadrada:

:computer:
```py
carros.var()
```

**Saída dos dados:**
```py
mpg               36.324103
cyl                3.189516
disp           15360.799829
hp              4700.866935
drat               0.285881
wt                 0.957379
qsec               3.193166
vs                 0.254032
am                 0.248992
qtd_marchas        0.544355
carb               2.608871
dtype: float64
```

<br>

📝 **Obs: O que esse código faz???**
- _O código está usando o método `.var()` do pacote pandas._
- _A variância é outra medida de dispersão estatística que indica o quão longe, em geral, os valores estão da média (ou a tendência central) de um conjunto de dados._
- _Esse método calcula a variância para cada coluna numérica do DataFrame._
- _O resultado final é retornado como um novo conjunto de dados com esses valores._

<br>

#### 5 - Seguindo, vamos ver o método `.value_counts()`, onde conta todos os valores em um array ou objeto do tipo Series:

:computer:
```py
marchas = carros.qtd_marchas
marchas.value_counts()
```
**Saída do código:**
```py
3    15
4    12
5     5
Name: qtd_marchas, dtype: int64
```

<br>

📝 **Obs: O que esse código faz???**
- _O código está criando uma nova série chamada `marchas` a partir da coluna `qtd_marchas` do DataFrame ._
- _O método `value_counts()` é aplicado na série `marchas`._
- _Esse método conta a frequência de cada valor único na série, e classifica os valores pela contagem decrescente._
- _Ele retorna um novo objeto (também uma série) com os valores únicos e suas respectivas contagens._
- _O objeto retornado pode ser utilizado para visualizar de maneira facil as contagens de cada valor único da série._


#### 5 - Por último, vamos falar sobre descritivo estatístico, usado para calcular estatísticas básicas, informações como contagem, média, desvio padrão, valor mínimo, valor máximo e quartis (25%, 50% e 75%) dos valores em cada coluna numérica do DataFrame original:

:computer:
```py
carros.describe()
```

**Saída do código:**
```py

        mpg	        cyl	        disp	        hp	        drat	        wt	        qsec	        vs	        am	        qtd_marchas	carb
count	32.000000	32.000000	32.000000	32.000000	32.000000	32.000000	32.000000	32.000000	32.000000	32.000000	32.0000
mean	20.090625	6.187500	230.721875	146.687500	3.596563	3.217250	17.848750	0.437500	0.406250	3.687500	2.8125
std	6.026948	1.785922	123.938694	68.562868	0.534679	0.978457	1.786943	0.504016	0.498991	0.737804	1.6152
min	10.400000	4.000000	71.100000	52.000000	2.760000	1.513000	14.500000	0.000000	0.000000	3.000000	1.0000
25%	15.425000	4.000000	120.825000	96.500000	3.080000	2.581250	16.892500	0.000000	0.000000	3.000000	2.0000
50%	19.200000	6.000000	196.300000	123.000000	3.695000	3.325000	17.710000	0.000000	0.000000	4.000000	2.0000
75%	22.800000	8.000000	326.000000	180.000000	3.920000	3.610000	18.900000	1.000000	1.000000	4.000000	4.0000
max	33.900000	8.000000	472.000000	335.000000	4.930000	5.424000	22.900000	1.000000	1.000000	5.000000	8.0000
```

<br>

📝 **Obs: O que esse código faz???**
- _O código está usando o método `.describe()` do pacote pandas._
- _Isso permite obter uma visão geral rápida das estatísticas dos dados, como tendência central, dispersão, distribuição, etc._
- _O resultado final é retornado como um novo conjunto de dados com essas estatísticas._

#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender sobre dados categóricos e falar um pouco sobre o Pandas!

### 🚀 Vejo vocês amanhã, tenham uma ótima semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
