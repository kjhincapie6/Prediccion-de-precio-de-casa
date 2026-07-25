# 🏡 Simulador de Valor del Mercado Inmobiliario

**plataforma:** Streamlit &nbsp;·&nbsp; **lenguaje:** Python &nbsp;·&nbsp; **modelo:** scikit-learn (Linear Regression)

Aplicación web que estima el **valor promedio del mercado inmobiliario de una zona geográfica** (no de una vivienda individual) a partir de variables socioeconómicas y del entorno, usando un modelo de Machine Learning inspirado en el California Housing Dataset.

## ¿Qué predice exactamente?

Cada registro representa una **zona residencial** (bloque censal), no una casa puntual. El modelo toma variables como ingreso medio de la zona, ubicación (latitud/longitud), proximidad al océano, total de habitaciones/dormitorios/hogares y edad mediana de la vivienda, y devuelve el valor estimado de mercado de esa zona en USD.

## Modelo

* **Dataset:** ~20.640 registros, estilo *California Housing Dataset*
* **Pipeline:** `StandardScaler` + `LinearRegression` (scikit-learn)
* **Desempeño:** R² ≈ 0.94 · RMSE ≈ 0.16 (en unidades de $100.000 USD)

## Un detalle de ingeniería

Igual que en [Predicción de Riesgo Cardiovascular](https://github.com/kjhincapie6/Prediccion-de-riesgo-cardiovascular), la versión original consultaba DataRobot vía API; al vencerse esa cuenta de prueba, se reemplazó por un modelo entrenado localmente e incrustado directamente en el código, sin dependencias externas.

## Cómo ejecutarlo localmente

```bash
git clone https://github.com/kjhincapie6/Prediccion-de-precio-de-casa.git
cd Prediccion-de-precio-de-casa
pip install -r requirements.txt
streamlit run app.py
```

## Stack

`Python` `scikit-learn` `pandas` `Streamlit`
