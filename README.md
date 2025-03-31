# Previsão de Séries Temporais para Potato White

## Aluno: Yago Phellipe Matos Lopes  
**Curso:** Ciência da Computação

## 1. Introdução
Este projeto tem como objetivo realizar previsões de preço da commodity **Potato White** utilizando modelos de séries temporais. Para isso, foram aplicadas duas abordagens distintas:

- **Prophet**: Modelo desenvolvido pelo Facebook para previsão de séries temporais.
- **LSTM (Long Short-Term Memory)**: Uma rede neural recorrente especializada em padrões sequenciais.

## 2. Dataset
O conjunto de dados utilizado foi retirado do Kaggle:
[Agriculture, Vegetables & Fruits - Time Series Prices](https://www.kaggle.com/datasets/ramkrijal/agriculture-vegetables-fruits-time-series-prices).

A base de dados contém informações históricas de preços de diversos produtos agrícolas. Neste projeto, filtramos apenas os registros referentes à **Potato White**, utilizando os seguintes campos:

- **ds**: Data do registro (originalmente "Date").
- **y**: Preço médio da commodity (originalmente "Average").


## 3. Comparação das Métricas

| Métrica  | Prophet | LSTM | Melhor Modelo |
|----------|--------|------|---------------|
| **MAE** (Erro Médio Absoluto) | 11.4068 | **1.5653** | LSTM |
| **RMSE** (Raiz do Erro Quadrático Médio) | 15.7252 | **3.3898** | LSTM |
| **MAPE** (Erro Percentual Absoluto Médio) | 34.8617% | **4.2231%** | LSTM |
| **R²** (Coeficiente de Determinação) | **-0.1793** | **0.9452** | LSTM |

### **Análise dos Resultados**
- O **LSTM teve um desempenho significativamente melhor** do que o Prophet em todas as métricas.
- O **MAE** e o **RMSE** do LSTM são muito menores, indicando previsões mais próximas dos valores reais.
- O **MAPE** do Prophet é alto (34,86%), enquanto o LSTM teve um **MAPE de apenas 4,22%**, indicando maior precisão.
- O **R²** do Prophet é negativo (-0.1793), o que significa que ele não conseguiu capturar bem a variação dos dados. Já o LSTM tem um **R² de 0.9452**, explicando bem a variabilidade dos dados.


## 4. Justificativa das Métricas
Para avaliar os modelos, escolhemos métricas amplamente utilizadas em previsão de séries temporais:

1. **MAE (Mean Absolute Error)**: Mede o erro absoluto médio entre previsão e valores reais.
   - Referência: Hyndman, R. J., & Athanasopoulos, G. (2018). *Forecasting: principles and practice*. OTexts.

2. **RMSE (Root Mean Square Error)**: Penaliza erros maiores mais severamente.
   - Referência: Chai, T., & Draxler, R. R. (2014). *Root mean square error (RMSE) or mean absolute error (MAE)?* Geoscientific Model Development.

3. **MAPE (Mean Absolute Percentage Error)**: Indica o erro relativo em porcentagem.
   - Referência: De Myttenaere, A., Golden, B., Le Grand, B., & Rossi, F. (2016). *Mean absolute percentage error for regression models*. Neurocomputing.

4. **R² (Coeficiente de Determinação)**: Mede a qualidade da explicação dos dados pelo modelo.
   - Referência: Draper, N. R., & Smith, H. (1998). *Applied regression analysis*. John Wiley & Sons.

## 5. Conclusão
O modelo **LSTM foi claramente superior** ao Prophet para prever os preços da commodity "Potato White". 

