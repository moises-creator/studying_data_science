## 👨‍💼 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 📊 Hoje iremos aprender como criar e visualizar Box Plots.

>O boxplot é uma ferramenta gráfica que mostra a distribuição dos dados. Ele mostra a mediana (a mediana é a medida de tendência central, que divide um conjunto de dados ordenado em duas metades), os quartis (os quartis dividem um conjunto de dados ordenados em quartos) e os valores máximo e mínimo. Os pontos fora da caixa são outliers, ou seja, valores fora da distribuição. Eles são mostrados como pontos individuais no gráfico.
**_significado da web._**

📝 **Obs:** _Irei utilizar o jupyter notebook para a fácil visualização dos gráficos, mas fique a vontade para escolher outro ambiente de sua preferência. Uma sugestão caso não conheça nenhum, tem o [colab](https://colab.research.google.com/) do google._


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


#### 3 - Agora após as configurações, iremos gerar dois gráficos de box plots para visualizar a distribuição dos dados de formas diferentes:

```py
carros.boxplot(column='mpg', by='am')
```

📝 **Obs: O que esse código faz???**
- _O código está criando um boxplot para a coluna `mpg` de uma tabela de dados chamada `carros`._
- _O boxplot é dividido entre transmissão automática e manual, usando a coluna `am` como critério de divisão._
- _O boxplot mostra a distribuição dos dados, incluindo mediana, quartis, valor máximo e mínimo._
- _Os pontos fora da caixa são outliers, ou seja, valores fora da distribuição._
- _O objetivo é comparar como a distribuição dos dados de mpg é diferente entre transmissão automática e manual._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem18.png?raw=true)

**Agora iremos visualizar o segundo gráfico utilizando os dados da coluna "wt" , onde estão sendo divididos entre transmissão automática e manual. Com isso, o boxplot mostra como a distribuição dos dados de `wt` é diferente entre essas duas categorias:**

```py
carros.boxplot(column='wt', by='am')
```
📝 **Obs: O que esse código faz???**

- _O código está criando um boxplot para a coluna `wt` de uma tabela de dados chamada `carros`._
- _O boxplot é dividido entre transmissão automática e manual, usando a coluna `am` como critério de divisão._
- _O boxplot mostra a distribuição dos dados, incluindo mediana, quartis, valor máximo e mínimo._
- _Os pontos fora da caixa são outliers, ou seja, valores fora da distribuição._
- _O objetivo é comparar como a distribuição dos dados de `wt` é diferente entre transmissão automática e manual._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem19.png?raw=true)


#### Por último, vamos criar um boxplot usando a biblioteca `seaborn`, para comparar a coluna `mpg` com a coluna `am` na tabela de dados `carros`:

```py
sns.boxplot(x='am', y='mpg', data=carros, palette='hls')
```

📝 **Obs: O que esse código faz???**
- _O boxplot está comparando as colunas `mpg` e `am` na tabela de dados `carros`._
- _A variável `x` está definida como `am` e a variável `y` está definida como `mpg`._
- _Os dados são passados para o gráfico através da variável `data` como `carros`._
- _Uma paleta de cores `hls` é definida._
- _O objetivo é mostrar como a distribuição da coluna `mpg` varia entre transmissão automática e manual._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem20.png?raw=true)

#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como criar scatter plots!

### 🚀 Vejo vocês amanhã, tenham uma ótima semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
