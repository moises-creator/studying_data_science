## 👨‍💼 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 📊 Hoje iremos aprender como criar e visualizar Box Plots.

>Um scatter plot, ou gráfico de dispersão, é um tipo de gráfico usado para mostrar como duas variáveis estão relacionadas. Ele mostra cada par de valores (x, y) como um ponto no plano cartesiano. Scatter plots são úteis para mostrar tendências e relações entre variáveis, como se uma variável aumenta ou diminui com a outra. É uma boa ferramenta para visualizar dados e identificar padrões.
>**_Significado da web_**


#### 1 - Primeiro, podemos usar a notação `as` para abreviar o nome das bibliotecas que vamos importar e facilitar a escrita de código:

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


#### 3 - Agora após as configurações, iremos gerar dois gráficos scatter plots para visualizar a distribuição dos dados de formas diferentes:

:computer:
```py
carros.plot(kind='scatter', x='hp', y='mpg', c=['darkgray'], s=150)
```

📝 **Obs: O que esse código faz???**
- _O código está criando um gráfico de dispersão usando os dados `carros`._
- _O eixo x representa o cavalo de potência `hp` dos carros nos dados._
- _O eixo y representa o consumo de combustível em milhas por galão `mpg` dos carros nos dados._
- _A cor dos pontos no gráfico é `cinza escuro` `(c=['darkgray'])`._
- _O tamanho dos pontos no gráfico é 150 `(s=150)`._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem21.png?raw=true)


**Agora utilizando vamos criar um gráfico de dispersão com uma linha de regressão linear usando a biblioteca seaborn:**

:computer:
```py
sns.regplot(x='hp', y='mpg', data=carros, scatter=True)
```

📝 **Obs: O que esse código faz???**
- _O código está criando um gráfico de dispersão com uma linha de regressão linear usando a biblioteca seaborn._
- _Os dados utilizados são do `carros`._
- _O eixo x representa o cavalo de potência `hp` dos carros nos dados._
- _O eixo y representa o consumo de combustível em milhas por galão `mpg` dos carros nos dados._
- _O parâmetro `scatter=True` indica que é desenhado um gráfico de dispersão juntamente com a linha de regressão._


**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem22.png?raw=true)

**Obs:**

>Regressão linear é um método estatístico utilizado para encontrar a relação entre uma variável dependente (y) e uma ou mais variáveis independentes (x). Ele tenta encontrar uma equação matemática que melhor se ajusta aos dados fornecidos, para prever a variação da variável dependente (y) com base na(s) variável(is) independente(s) (x). É chamado de "linear" porque a relação entre as variáveis é representada por uma reta.


#### 🌊 Espero que tenham gostado do conteúdo! Caso queiram um assunto mais detalhado sobre regressão linear, comentem aí!

### 🚀 Vejo vocês amanhã, tenham uma ótima semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
