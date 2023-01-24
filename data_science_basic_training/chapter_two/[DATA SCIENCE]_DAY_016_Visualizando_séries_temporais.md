## 👨‍💼 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 🐍 Hoje iremos aprender como visualizar séries temporais.


>As séries temporais são importantes na ciência de dados porque permitem entender como os dados variam ao longo do tempo. Isso é útil em muitas áreas, como finanças, meteorologia e saúde, para prever tendências futuras e tomar decisões informadas. As técnicas de análise de séries temporais, como a decomposição e a previsão, são amplamente utilizadas para analisar esses dados.

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


#### 3 - Após ter feito as configurações iniciais, vamos ler arquivo CSV chamado "Superstore-Sales.csv" e importar os dados para um Dataframe:
>🔍 _Para baixar o arquivo que está sendo usado, clique [aqui](https://drive.google.com/file/d/1KV9_9dVeAfWth6ijDjPw7dmZu32Grigj/view?usp=sharing)._


```py
caminho = 'O-caminho-do-seu-arquivo/Superstore-Sales.csv'
df = pd.read_csv(caminho, index_col='Order Date', parse_dates=True, 
                 encoding='ISO-8859-1')
df.head(3)
```

📝 **Obs: O que esse código faz???** 
- _Definindo caminho para o arquivo: A primeira linha define uma variável chamada `caminho` que contém o caminho para o arquivo CSV `Superstore-Sales.csv` que está localizado no desktop do usuário na pasta `roteiros/dados`._
- _Lendo arquivo CSV: A segunda linha utiliza a biblioteca pandas para ler o arquivo CSV especificado na variável `caminho` e armazena os dados em um dataframe chamado `df`._
- _Indexando o Dataframe: A terceira linha define a coluna `Order Date` como o índice do dataframe `df` e converte essas entradas para objetos de data e hora._
- _Codificação do arquivo: A quarta linha especifica a codificação do arquivo como `ISO-8859-1`._
- _Visualização dos dados: A quinta linha utiliza o método `head()` para visualizar as primeiras 3 linhas do dataframe `df`._

**Saída dos dados:**
|Order Date|Row ID|Order ID|Order Priority|Order Quantity|Sales|Discount|Ship Mode|Profit|Unit Price|Shipping Cost|Customer Name|Province|Region|Customer Segment|Product Category|Product Sub-Category|Product Name|Product Container|Product Base Margin|Ship Date|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|2010-10-13 00:00:00|1|3|Low|6|261\.54|0\.04|Regular Air|-213\.25|38\.94|35\.0|Muhammed MacIntyre|Nunavut|Nunavut|Small Business|Office Supplies|Storage & Organization|Eldon Base for stackable storage shelf, platinum|Large Box|0\.8|10/20/2010|
|2012-10-01 00:00:00|49|293|High|49|10123\.02|0\.07|Delivery Truck|457\.81|208\.16|68\.02|Barry French|Nunavut|Nunavut|Consumer|Office Supplies|Appliances|1\.7 Cubic Foot Compact "Cube" Office Refrigerators|Jumbo Drum|0\.58|10/2/2012|
|2012-10-01 00:00:00|50|293|High|27|244\.57|0\.01|Regular Air|46\.71|8\.69|2\.99|Barry French|Nunavut|Nunavut|Consumer|Office Supplies|Binders and Binder Accessories|Cardinal Slant-D® Ring Binder, Heavy Gauge Vinyl|Small Box|0\.39|10/3/2012|


#### 4 - Agora vamos utilizar o método `plot()` para plotar os dados da coluna `Order Quantity` do dataframe `df`. Isso gera um gráfico de linha mostrando como a quantidade de pedidos varia ao longo do tempo. Este gráfico pode ajudar a visualizar tendências e padrões nos dados de quantidade de pedidos:

```py
df['Order Quantity'].plot()
```

📝 **Obs: O que esse código faz???** 
- _Acessando coluna específica do Dataframe: Essa linha de código acessa a coluna "Order Quantity" do dataframe `df` usando notação de colchetes `[]`_
- _Plotando gráfico: Utiliza o método `plot()` para plotar os dados da coluna `Order Quantity` acessada anteriormente._
- _Visualizando tendências e padrões: O gráfico gerado mostra como a quantidade de pedidos varia ao longo do tempo, o que pode ajudar a visualizar tendências e padrões nos dados de quantidade de pedidos._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem14.png?raw=true)


#### 5 - Por último, vamos plotar um gráfico de linha com os dados de quantidade de pedidos de uma amostra aleatória com o objetivo de visualizar as tendências e padrões dos dados de quantidade de pedidos:

```py
df2 = df.sample(n=100, random_state=25, axis=0)

plt.xlabel('Order Date')
plt.ylabel('Order Quantity')
plt.title('Superstore Sales')

df2['Order Quantity'].plot()
```

📝 **Obs: O que esse código faz???** 
- Amostrando dados: A primeira linha do código cria uma nova variável chamada `df2` que contém uma amostra aleatória de 100 linhas do dataframe `df`. O argumento `random_state` é usado para garantir que a mesma amostra seja selecionada cada vez que o código é executado.
- _Configurando gráfico: As próximas três linhas usam o módulo `plt` da biblioteca matplotlib para rotular o eixo x como `Order Date`, o eixo y como `Order Quantity` e definir o título do gráfico como `Superstore Sales`._
- _Plotando gráfico: A última linha usa o método `plot()` para plotar os dados da coluna `Order Quantity` da amostra `df2` gerada anteriormente._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem15.png?raw=true)

#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como criar histogramas!

### 🚀 Vejo vocês amanhã, tenham uma ótima semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
