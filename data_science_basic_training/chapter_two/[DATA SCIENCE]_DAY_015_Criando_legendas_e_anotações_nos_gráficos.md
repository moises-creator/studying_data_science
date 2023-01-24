## 👨‍💼 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 🦥 Hoje iremos aprender como formatar gráficos.

📝 **Obs:** _Irei utilizar o jupyter notebook, mas fique a vontade para escolher outro ambiente de sua preferência. Uma sugestão caso não conheça nenhum, tem o [colab](https://colab.research.google.com/) do google._

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
rcParams['figure.figsize'] = 8, 4
sns.set_style('whitegrid')
```

📝 **Obs:** 
 - _`%matplotlib inline:` É usado para exibir gráficos dentro do notebook Jupyter. Ele permite que os gráficos sejam exibidos diretamente na célula do notebook, sem precisar abrir uma janela separada._

- _`rcParams ['figure.figsize']`: É usado para definir o tamanho da figura. No caso, está definindo o tamanho como 8 polegadas de largura e 4 polegadas de altura._

- _`sns.set_style ('whitegrid')`: É usado para definir o estilo do gráfico. O estilo 'whitegrid' adiciona grade na cor branca na figura. Ele pode ser usado para ajudar na leitura do gráfico._


#### 3 - Agora iremos ler um arquivo CSV chamado "mtcars.csv" que provavelmente estará localizado em sua máquina local:

🔍 _Para baixar o arquivo que está sendo usado, clique [aqui](https://drive.google.com/file/d/1Z_B_nGM7O_YfNvtDYLL0PlBHzOX_WmSG/view?usp=sharing)._

```py
caminho = 'O-caminho-do-arquivo/mtcars.csv'
carros = pd.read_csv(caminho)
carros.columns = ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']
mpg = carros['mpg'] 
```

📝 **Obs: O que esse código faz???** 
- _Atribuição de caminho do arquivo: O caminho para o arquivo `mtcars.csv` é armazenado na variável `caminho`._

- _Leitura do arquivo CSV: O método `pd.read_csv(caminho)` é usado para ler o arquivo `mtcars.csv` e armazenar os dados em uma variável chamada `carros`._

- _Renomeando colunas: As colunas do DataFrame `carros` são renomeadas usando a atribuição `carros.columns = ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']`._

- _Seleção de coluna: A coluna `mpg` é selecionada do DataFrame `carros` e armazenada na variável `mpg`._


#### 4 - Após lermos o arquivo `CSV` e  renomearmos as colunas, vamos aprender a colocar títulos nos eixos do gráfico gerado:

```py
x = range(1, 10)
y = [1, 2, 3, 4, 0.5, 4, 3, 2, 1]
plt.bar(x, y)

plt.xlabel('nossa legenda no eixo X')
plt.ylabel('nossa legenda no eixo Y')
plt.show()
```

📝 **Obs: O que esse código faz???** 
- _Criação de dados para o eixo x: A função `range(1,10)` é usada para criar uma lista de números inteiros de 1 a 9, que serão usados como valores no eixo `x` do gráfico._

- _Criação de dados para o eixo y: Uma lista de valores é criada com os valores `[1, 2, 3, 4, 0.5, 4, 3, 2, 1]`, que serão usados como valores no eixo `y` do gráfico._

- _Criação do gráfico de barras: O método `plt.bar(x, y)` é usado para criar um gráfico de barras com os dados dos eixos `x` e `y`._

- _Adicionando rótulos aos eixos: O método `plt.xlabel()` é usado para adicionar um rótulo ao eixo `x`, enquanto o método `plt.ylabel()` é usado para adicionar um rótulo ao eixo `y`._

- _Exibindo o gráfico: O método `plt.show()` é usado para exibir o gráfico na tela._


**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem11.png?raw=true)


#### 5 - Agora que enxergamos a possibilidade de colocar títulos nos eixos do gráfico, vamos explorar as demais funcionalidades desses eventos:

```py
import matplotlib.patches as mpatches

plt.plot(mpg)
plt.title('Consumo de gasolina')
plt.xlabel('nomes dos carros')
plt.ylabel('millhas/galão')
plt.xticks(mpg.index, carros.nomes, rotation=45)


legenda = mpatches.Patch(label='mpg')
plt.legend(handles=[legenda])

plt.show()
```

📝 **Obs: O que esse código faz???** 
- _Importação da biblioteca matplotlib.patches: A biblioteca `matplotlib.patches` é importada com o nome `mpatches` para permitir a criação de legendas personalizadas._

- _Criação do gráfico de linha: O método `plt.plot(mpg)` é usado para criar um gráfico de linha com os dados da coluna `mpg` do DataFrame `carros`._

- _Adicionando título ao gráfico: O método `plt.title()` é usado para adicionar um título ao gráfico, `Consumo de gasolina`._

- _Adicionando rótulos aos eixos: O método `plt.xlabel()` é usado para adicionar um rótulo ao eixo `x`, `nomes dos carros` e o método `plt.ylabel()` é usado para adicionar um rótulo ao eixo `y`, `millhas/galão`._

- _Rotacionando as etiquetas do eixo x: O método `plt.xticks(mpg.index, carros.nomes, rotation=45)` é usado para adicionar as etiquetas do eixo `x` como os nomes dos carros e rotacionando em 45 graus._

- _Criação de legenda personalizada para o gráfico: O objeto `legenda` é criado com o método `mpatches.Patch(label='mpg')` e adicionado ao gráfico com o método `plt.legend(handles=[legenda])`._

- _Exibindo o gráfico: O método `plt.show()` é usado para exibir o gráfico na tela._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem12.png?raw=true)

#### 6 - Por último, temos a possibilidade de colocar anotações no gráfico, assim ficando legível alguns pontos que queremos destacar:

```py
plt.plot(mpg)
plt.title('Milhas por galão por carro em mtcars')
plt.xlabel('nomes dos carros')
plt.ylabel('millhas/galão')
plt.xticks(mpg.index, carros.nomes, rotation=45)
plt.annotate('Toyota Corolla', xy=(19,33.9), xytext = (21,33),
           arrowprops=dict(facecolor='black', shrink=0.05))
plt.show()
```

📝 **Obs: O que esse código faz???** 
- _Criação do gráfico de linha: O método `plt.plot(mpg)` é usado para criar um gráfico de linha com os dados da coluna `mpg` do DataFrame "carros"._

- _Adicionando título ao gráfico: O método `plt.title()` é usado para adicionar um título ao gráfico, `Milhas por galão por carro em mtcars`._

- _Adicionando rótulos aos eixos: O método `plt.xlabel()` é usado para adicionar um rótulo ao eixo x, `nomes dos carros` e o método `plt.ylabel()` é usado para adicionar um rótulo ao eixo y, `milhas/galão`._

- _Rotacionando as etiquetas do eixo x: O método `plt.xticks(mpg.index, carros.nomes, rotation=45)` é usado para adicionar as etiquetas do eixo x como os nomes dos carros e rotacionando em 45 graus._

- _Anotando no gráfico: O método `plt.annotate()` é usado para adicionar uma anotação no ponto específico do gráfico, no caso, no ponto onde ocorre o `consumo máximo` de gasolina que é `Toyota Corolla`, e `adicionando seta` para esse ponto com as `especificações de cor` e `tamanho`._

- _Exibindo o gráfico: O método `plt.show()` é usado para exibir o gráfico na tela._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem13.png?raw=true)


#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como visualizar séries temporais!

### 🚀 Vejo vocês amanhã, tenham uma ótima semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
