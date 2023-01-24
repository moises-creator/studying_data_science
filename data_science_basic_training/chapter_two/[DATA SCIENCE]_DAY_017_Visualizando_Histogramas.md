## 👨‍💼 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 📊 Hoje iremos aprender como criar e visualizar histogramas.

>O histograma é uma ferramenta importante na análise exploratória de dados, pois permite visualizar a distribuição de frequência de um conjunto de dados. Ele mostra como os dados estão distribuídos em diferentes intervalos ou classes, o que pode ajudar a identificar tendências, outliers e padrões.

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


>**Essas linhas de código preparam as bibliotecas necessárias para serem utilizadas na visualização de dados.**

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

#### 3 - Após as configurações iniciais, vamos ler um arquivo CSV chamado "mtcars.csv" e através dos dados obtidos, vamo utilizar a função `plt.hist ()` do matplotlib e desesenhar um histograma:

>🔍 _Para baixar o arquivo que está sendo usado, clique [aqui](https://drive.google.com/file/d/1Z_B_nGM7O_YfNvtDYLL0PlBHzOX_WmSG/view?usp=sharing)._

```py
caminho = 'O-caminho-do-seu-arquivo/mtcars.csv'
carros = pd.read_csv(caminho)
carros.columns = ['nomes','mpg','cyl','disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']
carros.index = carros.nomes
mpg = carros['mpg']

plt.hist(mpg)
plt.plot()
plt.show()
```

📝 **Obs: O que esse código faz???**
- _Caminho do arquivo: a variável `caminho` é atribuída com o caminho do arquivo mtcars.csv, que se encontra na máquina local do usuário._

- _Importação de dados: A função `pd.read_csv()` é utilizada para importar o conteúdo do arquivo `mtcars.csv` e armazená-lo na variável `carros`._

- _Renomeando colunas: As colunas do dataframe `carros` são renomeadas com novos nomes através da atribuição da lista de nomes de colunas à propriedade `columns` do dataframe._

- _Definição do índice: O índice do dataframe `carros` é definido como sendo a coluna `nomes` através da atribuição da coluna `nomes` à propriedade `index` do dataframe._

- _Seleção de dados: A coluna `mpg` é selecionada do dataframe `carros` e armazenada na variável `mpg`._

- _Plotagem do histograma: A função `plt.hist()` é utilizada para plotar o histograma dos dados contidos na variável `mpg` As funções `plt.plot()` e `plt.show()` são utilizadas para exibir o gráfico gerado._


**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem16.png?raw=true)

#### 4 - Para termos uma visualização mais completa da distribuição dos dados, podemos utilizar o método  sns.distplot() do Seaborn onde você vai obter um gráfico com o histograma dos dados e a curva de densidade de probabilidade, o que pode ser útil para analisar a distribuição dos dados e obter informações adicionais:

```py
sns.distplot(mpg)
```

📝 **Obs: O que esse código faz???**

- _Utilização do pacote seaborn: O pacote seaborn é importado para utilizar sua função `sns.distplot()`._

- _Plotagem do histograma e curva de densidade: A função `sns.distplot()` é utilizada para plotar tanto um histograma quanto uma curva de densidade de probabilidade dos dados contidos na variável `mpg`. Isso permite uma visualização mais completa da distribuição dos dados._

- _Análise da distribuição: O gráfico gerado pela função `sns.distplot()` pode ser utilizado para analisar a distribuição dos dados e obter informações adicionais sobre a mesma._


**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem17.png?raw=true)

#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como criar box plots!

### 🚀 Vejo vocês amanhã, tenham uma ótima semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
