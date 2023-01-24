## 🌴 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 🎯 Hoje iremos dar início ao nosso 3º capítulo chamado "Matemática e Estatística Básica" e falar sobre investigação de valores numéricos como o tema de hoje.

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
<br>


📝 **Obs: O que esse código faz???**
- _O caminho do arquivo é especificado como uma variável chamada `caminho`_
- _O arquivo é lido usando a função `pd.read_csv` e armazenado em uma variável chamada `carros`_
- _As colunas do conjunto de dados são renomeadas para nomes mais significativos usando a propriedade `columns`._
- _O método `head` é usado para exibir as primeiras linhas do conjunto de dados._

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

#### 3 - Agora vamos utilizar o método `sum()`,onde vai ser usado para calcular a soma de todos os valores em cada coluna do conjunto de dados `carros`:

:computer:
```py
carros.sum()
```

📝 **Obs: O que esse código faz???**

- _Retorna um novo conjunto de dados com uma única linha que contém a soma de cada coluna._
- _Funciona somente para colunas com valores numéricos. Se houver colunas com outros tipos de dados (como strings), essas colunas serão ignoradas._

<br>

**Saída do código:**

```py
nomes         Mazda RX4Mazda RX4 WagDatsun 710 Hornet 4 Drive...
mpg                                                        642.9
cyl                                                          198
disp                                                      7383.1
hp                                                          4694
drat                                                      115.09
wt                                                       102.952
qsec                                                      571.16
vs                                                            14
am                                                            13
qtd_marchas                                                  118
carb                                                          90
dtype: object
```

#### 4 - Iremos repetir a questão acima, porem utilizando o parâmetro "axis=1", onde  indica que a operação de soma deve ser realizada ao longo das linhas (em vez das colunas). Se você não especificar o valor de eixo, o padrão é 0 (soma ao longo das colunas):

:computer:
```py
carros.sum(axis=1)
```

📝 **Obs: O que esse código faz???**

- _O método `sum()` é usado para calcular a soma de valores._
- _O parâmetro `axis=1` especifica que a operação de soma deve ser realizada ao longo das linhas (em vez das colunas)._
- _O resultado é uma nova série/coluna com a soma dos valores de cada linha do conjunto de dados `carros`._

**Saída do código:**
```py
0     328.980
1     329.795
2     259.580
3     426.135
4     590.310
5     385.540
6     656.920
7     270.980
8     299.570
9     350.460
10    349.660
11    510.740
12    511.500
13    509.850
14    728.560
15    726.644
16    725.695
17    213.850
18    195.165
19    206.955
20    273.775
21    519.650
22    506.085
23    646.280
24    631.175
...
28    670.690
29    379.590
30    694.710
31    288.890
dtype: float64
```

<br>

#### 5 - Vamos utilizar agora o método `median()`, onde é usado para calcular a mediana de todos os valores em cada coluna do conjunto de dados `carros`. 

>A mediana é o valor central de uma série de dados, ou seja, é o valor que divide os dados em duas partes iguais, metade dos valores está acima e metade está abaixo dele. Isso retornará um novo conjunto de dados com uma única linha que contém a mediana de cada coluna.

:computer:
```py
carros.median()
```

📝 **Obs: O que esse código faz???**
- _O método `median()` é usado para calcular a mediana dos valores em cada coluna do conjunto de dados `carros`._
- _A mediana é o valor central dos dados, dividindo-os em duas partes iguais_
- _O resultado é um novo conjunto de dados com uma única linha que contém a mediana de cada coluna._
- _Note que isso somente funciona para colunas com valores numéricos, colunas com outros tipos de dados serão ignoradas._

<br>

**Saída do código:**
```py
mpg             19.200
cyl              6.000
disp           196.300
hp             123.000
drat             3.695
wt               3.325
qsec            17.710
vs               0.000
am               0.000
qtd_marchas      4.000
carb             2.000
dtype: float64
```

<br>

#### 6 - Irei te mostrar também o método `mean()`, onde é usado para calcular a média de todos os valores em cada coluna do conjunto de dados `carros`:

:computer:
```py
carros.mean()
```

📝 **Obs: O que esse código faz???**
- _O método `mean()` é usado para calcular a média dos valores em cada coluna do conjunto de dados `carros`._
- _A média é calculada como a soma dos valores dividido pelo número de valores_
- _O resultado é um novo conjunto de dados com uma única linha que contém a média de cada coluna._

**Saída do código:**
```py
mpg             20.090625
cyl              6.187500
disp           230.721875
hp             146.687500
drat             3.596563
wt               3.217250
qsec            17.848750
vs               0.437500
am               0.406250
qtd_marchas      3.687500
carb             2.812500
dtype: float64
```

<br>

#### 7 - Por último, vamos ver o método `max()`, onde é usado para encontrar o valor máximo em cada coluna do conjunto de dados `carros`:

:computer:
```py
carros.max()
```

📝 **Obs: O que esse código faz???**
- _O método `max()` é usado para encontrar o valor máximo em cada coluna do conjunto de dados `carros`._
- _O resultado é um novo conjunto de dados com uma única linha que contém o valor máximo de cada coluna._

<br>

**Saída do código:**
```py
nomes          Volvo 142E
mpg                  33.9
cyl                     8
disp                  472
hp                    335
drat                 4.93
wt                  5.424
qsec                 22.9
vs                      1
am                      1
qtd_marchas             5
carb                    8
dtype: object
```

**Uma curiosidade importante é que podemos usar o método idxmax() para encontrar o índice da linha com o valor máximo da coluna "mpg". Isso retornará um índice numérico correspondente à linha com o valor máximo:**

:computer:
```py
mpg = carros.mpg
mpg.idxmax()
```

📝 **Obs: O que esse código faz???**
- _A coluna "mpg" é atribuída a uma nova variável chamada `mpg`._
- _O método `idxmax()` é usado para encontrar o índice da linha com o valor máximo da coluna `mpg`._
- _O resultado é um índice numérico correspondente à linha com o valor máximo da coluna `mpg`._
- _Isso é útil para localizar a linha específica (ou registro) com o maior valor de uma determinada coluna._

#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como investigar a disperção de uma variável!

### 🚀 Vejo vocês amanhã, tenham um ótimo final de semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
