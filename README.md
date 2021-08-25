# índices financeiros vs pandemia
### Analisando o comportamento dos principais índices financeiros diante da pandemia

O intuito desta análise, inicialmente, é observar o comportamento de alguns dos principais índices financeiros mundiais diante da chegada da pandemia. O intervalo a ser analisado compreenderá o período entre 01/10/2019 e 01/08/2021, e para fins de estudo se adotará 01/03/2020 como marco da pandemia.

<u>Índice observados:</u><br>
Nasdaq (EUA) <br>
Dow Jones (EUA)<br>
S&P 500 (EUA)<br>
Nikkei (Japão)<br>
Hang Seng (China)<br>
FTSE 100 (Reino Unido)<br>
DAX (Alemanha)<br>

Posteriormente, a análise trará um confronto entre um compilado destes índices supracitados com o nosso:<br>
Ibov (Brasil)


## 1) Aquisição dos dados
```
Para obter os dados, foi usada a API do yahoo
finances obtida através do comando

!pip install yfinance --upgrade --no-cache-dir

Através dela, foram importados os tickers referentes aos
índices estudados

import yfinance as yf

# Tickers Mundo
tickers = "^IXIC ^DJI ^GSPC ^N225 ^GDAXI ^FTSE ^HSI"                   
mundo = yf.download(tickers, start="2019-10-01", 
end="2021-08-01")["Adj Close"]

# Ticker Ibov
ibov = yf.download("^BVSP", start="2019-10-01", 
end="2021-08-01")["Adj Close"]

```

## 2) Estudo dos gráficos

O primeiro gráfico trás para o plano cartesiano os índices, cada qual com seu valor de pontos:

![screenshot1](https://github.com/igorcabralbr/pandas_analise_mercado/tree/main/imagens/img1.png)

Para efeito de comparação esse gráfico não serve muito, pois cada índice tem sua própria pontuação e comparar diretamente os valores entre índices diferentes seria um erro.

Para tanto, é necessário normalizar os índices, tornando suas pontuações proporcionais e partindo de um mesmo ponto, assim temos o seguinte gráfico:

![screenshot2](https://github.com/igorcabralbr/pandas_analise_mercado/tree/main/imagens/img2.png)

Uma vez normalizados, um índice chamado 'índices mundo' é criado, composto justamente pelos índices trabalhados anteriormente.<br>
Com este super-índice em mãos, é feita a comparação contra o Ibov brasileiro.

![screenshot3](https://github.com/igorcabralbr/pandas_analise_mercado/tree/main/imagens/img3.png)

Finalmente é observado o comportamento do índice brasileiro perante os principais índices mundiais durante o período de pandemia.

## 3) Conclusão

Através do estudo notamos particularidades interessantes, o índice IBOV apresenta queda mais acentuada que os índices fora do Brasil, mas a sua retomada, mesmo que com menos pontos, segue a mesma linha, indicando uma 'amarração' com o exterior.
Nota-se também que no ínicio do ano de 2021 os índices praticamente já tinham se recuperado da pandemia, mesmo com relatos de uma economia severamente prejudicada. Essa ingestão de capital nos índices em uma economia ainda debilitada pode representar uma aposta no reaquecimento da economia ou evidenciar uma bolha dos ativos podendo ser o prelúdio da próxima crise monetária global.
