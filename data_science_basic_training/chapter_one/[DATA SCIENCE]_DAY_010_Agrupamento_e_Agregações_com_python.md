## 👽 Saudações pessoal, tudo bem com vocês?

### 🪴 Hoje iremos aprender sobre agrupamentos e agregações dos dados com python:

🎯 **Objetivo:**
 - agrupamentos e agregações;


#### 1 - Primeiro, vamos importar a biblioteca Pandas e dar um apelido a ela:

:computer:
```py
import pandas as pd
```

#### 2 - Agora, iremos utilizar arquivos csv(comma-separated-value) como dados externos e manipulá-los. Com o método `read_csv`, conseguimos ler os dados dentro do arquivo:


:computer:
```py
caminho = 'O-caminho-do-seu-arquivo/mtcars.csv'

carros = pd.read_csv(caminho)
print(carros.head())

#saida
	Unnamed: 0	    mpg	     cyl      disp      hp      drat      wt	  qsec      vs      am      gear      carb
        
0	Mazda RX4	    21.0     6	      160.0	110	3.90	  2.620	  16.46     0       1	    4	      4
1	Mazda RX4 Wag	    21.0     6	      160.0	110	3.90	  2.875	  17.02     0	    1	    4	      4
2	Datsun 710	    22.8     4	      108.0	93	3.85	  2.320	  18.61     1	    1	    4	      1
3	Hornet 4 Drive	    21.4     6	      258.0	110	3.08	  3.215	  19.44     1	    0	    3	      1
4	Hornet Sportabout   18.7     8	      360.0	175	3.15	  3.440	  17.02     0	    0	    3	      2
```

**Obs:** 
- _Para baixar o arquivo `mtcars.csv`, acesse este link externo para [Download aqui](https://drive.google.com/drive/u/0/folders/1CsW4fw92Kk0otd4OXH_d3IGswGqDH7Nk);_
- _Atente-se a passar o endereço correto, caso esteja usando o jupiter Notebook, suba o arquivo na plataforma._
- _`carros.head()` retorna somente a `cabeça` do arquivo, os 5 primeiros._


#### 3 - Podemos manipular os dados do arquivo `mtcars.csv` substituindo os nomes das colunas:


:computer:
```py
carros.columns = ['nomes','mpg','cyl','disp', 'hpt', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']
print(carros.head())

#saida
        nomes               mpg	     cyl      disp      hpt     drat      wt	  qsec      vs      am      gear      carb
        
0	Mazda RX4	    21.0     6	      160.0	110	3.90	  2.620	  16.46     0       1	    4	      4
1	Mazda RX4 Wag	    21.0     6	      160.0	110	3.90	  2.875	  17.02     0	    1	    4	      4
2	Datsun 710	    22.8     4	      108.0	93	3.85	  2.320	  18.61     1	    1	    4	      1
3	Hornet 4 Drive	    21.4     6	      258.0	110	3.08	  3.215	  19.44     1	    0	    3	      1
4	Hornet Sportabout   18.7     8	      360.0	175	3.15	  3.440	  17.02     0	    0	    3	      2
```

#### 4 - Por último, podemos agrupar os dados de um DataFrame considerando uma coluna em particular, usando o método `.groupby()` e passando o nome da coluna que queremos executar o agrupamento:


:computer:
```py
coluna_agrupamento = carros['cyl']
grupos_carros = carros.groupby(coluna_agrupamento)
print(grupos_carros.mean())

#saida
cyl     mpg	        disp	        hpt	        drat	        wt	        qsec	        vs	        am	        gear	        carb
										
4	26.663636	105.136364	82.636364	4.070909	2.285727	19.137273	0.909091	0.727273	4.090909	1.545455
6	19.742857	183.314286	122.285714	3.585714	3.117143	17.977143	0.571429	0.428571	3.857143	3.428571
8	15.100000	353.100000	209.214286	3.229286	3.999214	16.772143	0.000000	0.142857	3.285714	3.500000
```


🌊 **Espero que tenham gostado do conteúdo, hoje finalizamos o capítulo 1 com 10 posts! Amanhã damos início ao capítulo 2 com conteúdos voltado para visualização de dados!**

🚀 **Vejo vocês amanhã e tenham uma ótima semana!**

![Data Science](https://media.licdn.com/dms/image/C4D12AQGD_su1k14bYA/article-cover_image-shrink_600_2000/0/1583217311227?e=2147483647&v=beta&t=s_7cvkGjyfNTp2x6mnsiPFUfbPhWyvnMIavE_na62bE)
