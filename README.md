# Sentiment Analysis Application

Esta es una aplicación de análisis de sentimientos que utiliza un modelo de regresión logística para clasificar mensajes como positivos o negativos. La aplicación está desarrollada con Flask y puede ejecutarse en un contenedor Docker.

## Estructura del Proyecto

sentimental-analysis-app/ ├── app.py # Archivo principal para ejecutar la aplicación Flask ├── Dockerfile # Archivo para construir la imagen Docker ├── requirements.txt # Dependencias del proyecto ├── sentiment.tsv # Dataset de entrenamiento ├── train.py # Script para entrenar el modelo ├── model/ │ ├── logistic_clf.pkl # Modelo entrenado y vectorizador ├── templates/ │ ├── home.html # Página principal de la aplicación │ ├── result.html # Página de resultados


## Requisitos

- Python 3.8 o superior
- Docker (opcional, para ejecutar la aplicación en un contenedor)

## Instalación

1. Clona este repositorio:

   ```bash
   git clone <URL_DEL_REPOSITORIO>
   cd sentimental-analysis-app

2. Instala las dependencias:

    pip install -r requirements.txt

3. Entrena el modelo (opcional si ya existe model/logistic_clf.pkl):

    python train.py

## Uso

1. Ejecuta la aplicación Flask:

    python app.py

2. Abre tu navegador y ve a http://127.0.0.1:5000.

3. Ingresa un mensaje en la página principal y presiona "Predict" para ver el resultado del análisis de sentimientos.

## Uso con Docker

1. Construye la imagen Docker:

    docker build -t sentiment-analysis-app .

2. Ejecuta el contenedor:

    docker run -p 5000:5000 sentiment-analysis-app

3. Abre tu navegador y ve a http://127.0.0.1:5000.

## Archivos Clave

### app.py
Este archivo contiene la lógica principal de la aplicación Flask. Carga el modelo entrenado y define las rutas para la página principal (/) y la predicción (/predict).

### train.py
Este script entrena un modelo de regresión logística utilizando el dataset sentiment.tsv. El modelo y el vectorizador se guardan en model/logistic_clf.pkl.

### templates/home.html
Página principal donde el usuario puede ingresar un mensaje para analizar.

### templates/result.html
Página que muestra el resultado del análisis de sentimientos (positivo o negativo) junto con una imagen representativa.

### Dockerfile
Archivo para construir una imagen Docker que contiene la aplicación Flask.

### Dataset
El dataset sentiment.tsv contiene dos columnas:

    label: Etiqueta de sentimiento (pos para positivo, neg para negativo).

    body_text: Texto del mensaje.
