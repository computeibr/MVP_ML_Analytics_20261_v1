# MVP — Machine Learning & Analytics

MVP da Sprint de Machine Learning & Analytics da Pós-graduação em Ciência de
Dados e Analytics (PUC-Rio).

**Autor:** Leonardo Valério Rodrigues Pires

## O problema

O ciclo El Niño/La Niña (ENSO) é monitorado pela rede de boias TAO Array no
Pacífico equatorial, cuja variável central é a temperatura da superfície do
mar (SST). Sensores falham e deixam lacunas nas medições — este trabalho
constrói e avalia modelos de **regressão** para estimar a SST a partir das
demais medições da boia (ventos, umidade, temperatura do ar) e do contexto
espacial e temporal (latitude, longitude, mês), apoiando o preenchimento de
lacunas e o controle de qualidade da rede.

## Resultado

O modelo final — **HistGradientBoostingRegressor** com hiperparâmetros
otimizados via RandomizedSearchCV — atingiu **RMSE 0,3511 °C, MAE 0,2588 °C
e R² 0,9713** no conjunto de teste, redução de 83,7% no erro em relação ao
baseline (prever a mediana). O fluxo completo — definição do problema, EDA,
preparação com pipeline, comparação de 3 famílias de modelos, otimização e
análise crítica — está documentado no notebook.

## Como executar

**Notebook no Google Colab:**
https://colab.research.google.com/drive/1Kq29itUva76Z2a4jUkuWAjCEloXl39sI?usp=sharing

Abra o link acima e execute do início ao fim
(`Ambiente de execução → Reiniciar e executar tudo`).

Não há dependências a instalar (apenas bibliotecas pré-instaladas no Colab)
nem necessidade de upload ou autenticação: o dataset é carregado diretamente
deste repositório via URL raw. Tempo total de execução: ~10 min em CPU
(dominado pela busca de hiperparâmetros).

## Estrutura do repositório

| Arquivo | Descrição |
|---|---|
| `MVP_ML_Analytics.ipynb` | Notebook completo do MVP (cópia do Colab acima) |
| `elnino.csv` | Dataset em CSV — conversão direta do arquivo original do UCI (nomes de colunas conforme `tao-all2.col`; valores "." convertidos para nulos; nenhuma linha removida ou alterada) |
| `README.md` | Este arquivo |

## Dataset

**El Niño Data Set — TAO Project**, UCI Machine Learning Repository.
178.080 medições diárias (1980–1998) das boias do Pacífico equatorial.

> El Nino [Dataset]. (1999). UCI Machine Learning Repository.
> https://doi.org/10.24432/C5WG62

Distribuído sob licença **CC BY 4.0**, que permite redistribuição com
atribuição — condição atendida pela citação acima.
