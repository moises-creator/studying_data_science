## 👨‍💼 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 🍁 Hoje iremos aprender como criar gráficos em barras com python.

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
rcParams['figure.figsize'] = 5, 4
sns.set_style('whitegrid')
```

📝 **Obs:** 
- _`%matplotlib inline`: Essa linha de código é usada para exibir gráficos dentro do notebook Jupyter. Isso significa que, em vez de abrir uma nova janela para exibir o gráfico, ele será exibido diretamente no notebook._

- _`rcParams['figure.figsize'] = 5, 4`: Essa linha de código define o tamanho da figura como 5x4. Isso significa que a largura será de 5 unidades e a altura será de 4 unidades._

- _`sns.set_style('whitegrid')`: Essa linha de código é parte do seaborn, uma biblioteca de visualização de dados baseada em Matplotlib. Ele define o estilo de grade como branco. Isso adiciona linhas brancas às suas visualizações de dados, o que pode ajudar a tornar os gráficos mais legíveis e fáceis de interpretar._


#### 3 - Com as configurações já feitas, iremos gerar um gráfico de barras simples utilizando o Matplotlib. 

:computer:
```py
x = range(1, 10)
y = [1, 2, 3, 4, 0, 4, 3, 2, 1]

plt.bar(x, y)
```

📝 **Obs: **
- _`x = range(1, 10)`: Essa linha de código está criando uma variável chamada "x" e atribuindo a ela uma lista de números inteiros de 1 a 9. Essa lista representa os valores do eixo x no gráfico._

- _`y = [1, 2, 3, 4, 0, 4, 3, 2, 1]`: Essa linha de código está criando uma variável chamada `y` e atribuindo a ela uma lista de números inteiros. Essa lista representa os valores do eixo y no gráfico._

- _`plt.bar(x, y)`: Essa linha de código está usando a função `bar` do Matplotlib para criar um gráfico de barras. A função `bar` recebe dois argumentos, `x` e `y`, que são as listas criadas nas linhas anteriores. Essa código que geramos irá plotar um gráfico de barras com as listas `x` e `y`._

**Gráfico gerado:**

![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem3.png?raw=true)


#### 4 - Após entendermos como funciona gerar um gráfico de barras utilizando dados rasos, iremos aprender sobre a criação de gráficos de barras utilizando um objeto Pandas:

🔍 _Para baixar o arquivo que está sendo usado, clique [aqui](https://drive.google.com/file/d/1Z_B_nGM7O_YfNvtDYLL0PlBHzOX_WmSG/view?usp=sharing)._

:computer:
```py
caminho = 'O-caminho-do-arquivo/mtcars.csv'

carros = pd.read_csv(caminho)
carros.columns = ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']
mpg = carros['mpg']

mpg.plot(kind='bar')
```

📝 **Obs: **
- _caminho: A variável `caminho` é atribuída com o caminho '/home/moisa/Downloads/dados/mtcars.csv'._

- _carros = pd.read_csv(caminho): A função `pd.read_csv()` é utilizada para ler o arquivo de dados e criar um dataframe com as informações contidas nele salvando em uma variável chamada carros._

- _carros.columns: As colunas do dataframe são renomeadas com os nomes especificados na lista ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']_

- _Seleção de coluna: A coluna `mpg` é selecionada e atribuída à variável mpg._

- _A função plot() é utilizada para gerar um gráfico de barras com os dados da coluna 'mpg'. A opção kind='bar' especifica que é um gráfico de barras que esta sendo criado._

**Em resumo, essas linhas de código estão lendo um arquivo CSV, renomeando as colunas e selecionando uma coluna específica para armazenar em uma variável.**

**Gráfico gerado:**
![Grafico gerado com o codigo acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem4.png?raw=true)

📝 **Obs:**
- _Podemos brincar um pouco e enxergar os dados por um outro ângulo. A opção kind='barh' especifica que é um gráfico de barras horizontais que esta sendo criado._

:computer:
```py
mpg.plot(kind='barh')
```

![Gráfico gerado com o codigo acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem5.png?raw=true)

- _Existem inúmeras formas, recomendo vocês lerem a [documentação](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.plot.html) e se divertirem com a variedade._

#### 5 - Por último, irei mostrar para vocês a possibilidade de salvar um gráfico em sua máquina local:

:computer:
```py
plt.savefig('grafico_de_barras.png')
```

📝 **Obs:**
- _A função savefig() do módulo pyplot (plt) é utilizada para salvar o gráfico gerado anteriormente para um arquivo de imagem. O argumento 'grafico_de_barras.png' especifica o nome do arquivo de imagem e o formato de imagem deve ser PNG._

- _Dando o comando `!dir`, você consegue visualizar seu gráfico salvo com o respectivo nome que você o atribuiu._

:computer:
```py
grafico_de_barras.png
```

#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como formatar gráficos!

### 🚀 Vejo vocês amanhã, tenham um ótimo final de semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
