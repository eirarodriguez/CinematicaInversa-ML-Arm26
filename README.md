# Aprendizaje Automático para la Resolución de la Cinemática Inversa en el Análisis del Movimiento Humano

Este repositorio contiene el código, los conjuntos de datos sintéticos y los modelos utilizados en el artículo presentado en el **XXI Simposio CEA de Control Inteligente (2026)**.

## 📝 Descripción del Proyecto
El análisis biomecánico tradicional requiere resolver la cinemática inversa mediante algoritmos de optimización iterativa, lo que supone una alta carga computacional y limita su uso en tiempo real. 

Este proyecto propone y evalúa una metodología unificada para sustituir los optimizadores clásicos de **OpenSim** por modelos de **Aprendizaje Automático** (Regresión Lineal, MLP, SVR y XGBoost). El enfoque transforma la simulación biomecánica en un motor de inferencia directa, reduciendo la latencia a niveles compatibles con el control de exoesqueletos y prótesis (aprox. 13.77 ms).

## 📂 Estructura del Repositorio
* `main.ipynb`: Notebook principal con el preprocesamiento de datos, entrenamiento de modelos y evaluación de resultados.
* `requirements.txt`: Archivo con las dependencias exactas necesarias para reproducir el entorno.
* `arm26.osim`: Archivo del modelo biomecánico simplificado del miembro superior utilizado en OpenSim.
* `movimiento_1/` a `movimiento_9/`: Carpetas que contienen las trayectorias cinemáticas generadas en las simulaciones. Cada carpeta incluye:
  * `angulos.mot`: Archivos con las variables articulares (hombro y codo).
  * `posiciones.sto`: Archivos con las coordenadas espaciales tridimensionales de la mano.

## ⚙️ Requisitos y Dependencias
Para ejecutar el código, primero clona este repositorio en tu equipo, accede a la carpeta del proyecto y luego instala las librerías necesarias utilizando el archivo de requisitos:

```bash
# 1. Clonar el repositorio
git clone [https://github.com/eirarodriguez/CinematicaInversa-ML-Arm26.git](https://github.com/eirarodriguez/CinematicaInversa-ML-Arm26.git)

# 2. Entrar en la carpeta del proyecto
cd CinematicaInversa-ML-Arm26

# 3. Instalar las dependencias
pip install -r requirements.txt
```

## 📊 Resultados Principales
El modelo **XGBoost** demostró ser la alternativa de compromiso óptima, alcanzando:
* **MAE Medio:** 0.14°
* **R²:** ~1.000
* **Tiempo de inferencia:** 13.77 ms (ejecutado en CPU AMD Ryzen 3)

## 📌 Citar este trabajo
Si utilizas este código o estos datos en tu investigación, por favor cita nuestro artículo:

> Rodríguez Martín, E., Sierra-García, J. E., Penacoba-Yagüe, M. (2026). Machine Learning for Solving Inverse Kinematics in the Analysis of Human Movement. *XXI Simposio CEA de Control Inteligente*, Salamanca (Spain), 2026.
