## 👨‍💼 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 🍄 Hoje iniciamos o capítulo 2: Visualização de dados.

#### Para ficar um pouco mais claro sobre o assunto, irei explicar como funciona essa etapa:

📝
- A visualização de dados é a técnica de representar informações numéricas e categóricas através de gráficos e outras representações visuais.
-  Isso ajuda a tornar os dados mais fáceis de entender e interpretar, e permite que os cientistas de dados identifiquem tendências, padrões e outliers nos dados. 
-  Alguns exemplos de tipos comuns de visualização de dados incluem gráficos de barras, gráficos de linhas, gráficos de dispersão e mapas.

### 👨‍💻 Agora, seguimos para o código:


📝 **Obs:** _Irei utilizar o júpiter notebook, mas fique a vontade para escolher outro ambiente de sua preferência. Uma sugestão caso não conheça nenhum, tem o [colab](https://colab.research.google.com/) do google._

#### 1 - Primeiro, podemos usar a notação as para abreviar o nome das bibliotecas que vamos importar e facilitar a escrita de código:

:computer:
```py
import pandas as pd

from matplotlib import pyplot as plt
from matplotlib import rcParams
import seaborn as sns
```


📝 **Obs:** 
- _A primeira linha `import pandas as pd` importa a biblioteca pandas para utilizar suas funções para manipular e analisar dados._
- _A segunda linha `from matplotlib import pyplot as plt` importa o módulo pyplot da biblioteca matplotlib para criar gráficos._
- _A terceira linha `from matplotlib import rcParams` importa as configurações de parâmetros padrão da biblioteca matplotlib._
- _A quarta linha `import seaborn as sns` importa a biblioteca seaborn que fornece uma interface mais fácil para criar gráficos estatísticos atraentes e informativos, e também estende as funcionalidades de matplotlib._

**Essas linhas de código preparam as bibliotecas necessárias para serem utilizadas na visualização de dados.**


#### 2 - Agora vamos ajustar as configurações de visualização para se adequar ao ambiente do Jupyter Notebook e estabelecer um estilo de gráfico padrão para ser usado ao longo do código:

:computer:
```py
%matplotlib inline
rcParams['figure.figsize'] = 10, 8
sns.set_style('whitegrid')
```


📝 **Obs:** 
- _A primeira linha `%matplotlib inline` é um comando específico do Jupyter Notebook que permite que os gráficos sejam exibidos diretamente no notebook._
- _A segunda linha`rcParams['figure.figsize'] = 10, 8` define o tamanho padrão da figura em 10 polegadas de largura e 8 polegadas de altura._
- _A terceira linha `sns.set_style('whitegrid')` define o estilo padrão do gráfico como "whitegrid", que adiciona grade branca ao fundo do gráfico._


#### 3 - Com essas configurações já feitas, vamos gerar um gráfico simples, onde os valores de x são os eixos x e os valores de y são os eixos y, conectando os pontos com uma linha:

:computer:
```py
x = range(1, 10)
y = [1, 2, 3, 4, 0, 4, 3, 2, 1]

plt.plot(x, y)
```


📝 **Obs:**
- _A primeira linha "x = range(1, 10)" define uma lista de valores inteiros de 1 a 9 para serem usados no eixo x do gráfico._
- _A segunda linha "y = [1, 2, 3, 4, 0, 4, 3, 2, 1]" define uma lista de valores inteiros para serem usados no eixo y do gráfico._
- _A terceira linha "plt.plot(x, y)" chama a função plot() do módulo pyplot da biblioteca matplotlib para criar um gráfico de linha com os valores de x e y._

**Gráfico gerado:**

![gráfico 1 gerado pelo código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem1.png?raw=true)

#### 4 - Por último vamos desenhar um gráfico de linhas utilizando um objeto Pandas,onde vamos ler os dados de um arquivo CSV e armazená-los em um dataframe do pandas, e renomear as colunas para facilitar a manipulação e visualização dos dados.

🔍 _Para baixar o arquivo que está sendo usado, clique [aqui](https://drive.google.com/file/d/1Z_B_nGM7O_YfNvtDYLL0PlBHzOX_WmSG/view?usp=sharing)._

:computer:
```py
caminho = 'O-caminho-do-seu-arquivo/mtcars.csv'

carros = pd.read_csv(caminho)
carros.columns = ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']
```


📝 **Obs:**
- _A primeira linha "caminho = '/home/moisa/Downloads/dados/mtcars.csv'" define uma variável chamada "caminho" que armazena o caminho do arquivo CSV com os dados dos carros._
- _A segunda linha "carros = pd.read_csv(caminho)" usa a função read_csv() do pandas para ler os dados do arquivo CSV especificado pelo caminho e armazená-los no dataframe chamado "carros"._
- _A terceira linha "carros.columns = ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']" define os nomes das colunas para o dataframe "carros"._

**Dando continuidade,será gerado um gráfico de linhas com base nas colunas selecionadas 'cyl', 'wt', 'mpg' do dataframe original "carros" e mostrarei como eles se relacionam entre si.**

:computer:
```py
df = carros[['cyl', 'wt', 'mpg']]
df.plot()
```


📝 **Obs:**
- _A primeira linha `df = carros[['cyl', 'wt', 'mpg']]` cria um novo dataframe "df" selecionando as colunas 'cyl', 'wt', 'mpg' do dataframe original "carros"._
- _A segunda linha `df.plot()` usa a função `plot()` do pandas para criar um gráfico de linhas com base nos dados do dataframe `df`, essa função utiliza o módulo pyplot da biblioteca matplotlib para criar o gráfico._

**Gráfico gerado:**

![gráfico gerado pelo código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem2.png?raw=true)


#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como criar gráficos de barras!

### 🚀 Vejo vocês amanhã!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
