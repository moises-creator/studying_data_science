## 👨‍💼 Bom dia, boa tarde e boa noite pessoal, tudo bem?

### 🌵 Hoje iremos aprender como formatar gráficos.

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
y = [1, 2, 3, 4, 0.5, 4, 3, 2, 1]

plt.bar(x, y)
```

📝 **Obs: **
- _`x = range(1, 10)`: Essa linha de código está criando uma variável chamada "x" e atribuindo a ela uma lista de números inteiros de 1 a 9. Essa lista representa os valores do eixo x no gráfico._

- _`y = [1, 2, 3, 4, 0.5, 4, 3, 2, 1]`: Essa linha de código está criando uma variável chamada `y` e atribuindo a ela uma lista de números inteiros. Essa lista representa os valores do eixo y no gráfico._

- _`plt.bar(x, y)`: Essa linha de código está usando a função `bar` do Matplotlib para criar um gráfico de barras. A função `bar` recebe dois argumentos, `x` e `y`, que são as listas criadas nas linhas anteriores. Essa código que geramos irá plotar um gráfico de barras com as listas `x` e `y`._

**Gráfico gerado:**

![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem6.png?raw=true)


#### 4 - Agora, vamos criar um gráfico de barras com as mesmas informações do gráfico acima, mas iremos colorir de laranja salmão e alinha-las no centro.

:computer:
```py
cor = ['salmon']
plt.bar(x, y, color=cor, align='center')
```

📝 **Obs: **
- _Esse código usa a biblioteca "matplotlib" para criar um gráfico de barras. O gráfico mostra as informações contidas nas variáveis `x` e `y`._
- _As barras do gráfico são coloridas de acordo com a cor especificada na variável `cor`, que contém a string `salmon`._
- _O parâmetro `align` é usado para alinhar as barras no centro do gráfico._


**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem7.png?raw=true)

#### 5 - Podemos também customizar o estilo das linhas. Iremos criar mais duas variáveis, `x1` e `y1` para compararmos e entendermos a diferença entre o gráfico das variáveis já criadas, `x` e `y`:

:computer:
```py
x1 = range(0,10)
y1 = [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]

plt.plot(x, y)
plt.plot(x1,y1)
```

📝 **Obs:**
- _Criação de lista de números: A linha `x1 = range(0,10)` usa a função "range" para criar uma lista de números inteiros de 0 a 9 e atribui essa lista à variável "x1".

- _Definição de valores para o eixo y: A linha `y1 = [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]` define uma lista de valores para o eixo y._

- _Criação do primeiro gráfico: A linha `plt.plot(x, y)` usa a função `plt.plot` para criar o primeiro gráfico de linhas com as informações contidas nas variáveis `x` e `y`._

- _Criação do segundo gráfico: A linha `plt.plot(x1,y1)` usa a função `plt.plot` para criar o segundo gráfico de linhas com as informações contidas nas variáveis `x1` e `y1`._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem8.png?raw=true)


#### 6 - Iremos criar dois gráficos de linhas, o primeiro gráfico irá mostrar as informações contidas nas variáveis "x" e "y" e o segundo gráfico irá mostrar as informações contidas nas variáveis "x1" e "y1", ambos com as linhas customizadas:

:computer:
```py
plt.plot(x, y, ls='steps', lw=5)
plt.plot(x1, y1, ls='--', lw=10)
```

📝 **Obs:**
- _Criação do primeiro gráfico: A linha `plt.plot(x, y, ls='steps', lw=5)` usa a função "plt.plot" para criar o primeiro gráfico de linhas com as informações contidas nas variáveis `x` e `y`._

- _Estilo da linha do primeiro gráfico: O parâmetro `ls` é usado para definir o estilo da linha do primeiro gráfico, no caso, "steps" que é uma representação discreta dos dados._

- _Espessura da linha do primeiro gráfico: O parâmetro `lw` é usado para definir a espessura da linha do primeiro gráfico, no caso, 5._

- _Criação do segundo gráfico: A linha `plt.plot(x1, y1, ls='--', lw=10)` usa a função "plt.plot" para criar o segundo gráfico de linhas com as informações contidas nas variáveis `x1` e `y1`._

- _Estilo da linha do segundo gráfico: O parâmetro `ls` é usado para definir o estilo da linha do segundo gráfico, no caso, `--` que é uma linha tracejada._

- _Espessura da linha do segundo gráfico: O parâmetro `lw` é usado para definir a espessura da linha do segundo gráfico, no caso, 10._

**Gráfico gerado:**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem9.png?raw=true)

#### 7 - Por último, irei mostrar que também é possível colocar marcadores em nossos gráficos gerados:

:computer:
```py
plt.plot(x, y, marker='1', mew=20)
plt.plot(x1, y1, marker='+', mew=15)
plt.show()
```

📝 **Obs:**
    
- _Criação do primeiro gráfico: A linha `plt.plot(x, y, marker='1', mew=20)` usa a função `plt.plot` para criar o primeiro gráfico de linhas com as informações contidas nas variáveis `x` e `y`._

- _Marcação dos pontos do primeiro gráfico: O parâmetro `marker` é usado para definir o tipo de marcação dos pontos no gráfico, no caso, `1` que é um número `1`_

- _Espessura da borda da marcação do primeiro gráfico: O parâmetro `mew` é usado para definir a espessura da borda da marcação dos pontos no primeiro gráfico, no caso, `20`._

- _Criação do segundo gráfico: A linha `plt.plot(x1, y1, marker='+', mew=15)` usa a função `plt.plot` para criar o segundo gráfico de linhas com as informações contidas nas variáveis `x1` e `y1`._

- _Marcação dos pontos do segundo gráfico: O parâmetro `marker` é usado para definir o tipo de marcação dos pontos no gráfico, no caso, `+` que é um sinal de mais `+`_

- _Espessura da borda da marcação do segundo gráfico: O parâmetro `mew` é usado para definir a espessura da borda da marcação dos pontos no segundo gráfico, no caso, `15`._

- _Exibição do gráfico: A linha `plt.show()` é usada para exibir o gráfico criado._

**Gráfico gerado**
![Gráfico gerado so código acima](https://github.com/moises-creator/studying_data_science/blob/main/data_science_basic_training/chapter_two/imagem10.png?raw=true)

#### 🌊 Espero que tenham gostado do conteúdo, amanhã iremos aprender como criar legendas e anotações!

### 🚀 Vejo vocês amanhã, tenham um ótimo final de semana!

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
