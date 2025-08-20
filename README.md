# 📡 Proyecto: Telecom X – Parte 2  

Este proyecto corresponde al **segundo desafío** de la serie **Telecom X**, una empresa ficticia de telecomunicaciones que enfrenta un problema crítico: la **evasión de clientes (churn)**.  

En la **Parte 1** se trabajó en la **extracción, limpieza, transformación y análisis exploratorio de datos (EDA)**.  
En esta **Parte 2**, avanzamos hacia la **construcción, validación e interpretación de modelos predictivos**, con el objetivo de anticipar qué clientes tienen mayor probabilidad de abandonar el servicio.  

---

## 🎯 Objetivo

Construir un **modelo de predicción de evasión de clientes** que identifique patrones clave y anticipe la decisión de los usuarios.  
Esto permitirá a la empresa diseñar **estrategias de retención efectivas**, reduciendo pérdidas económicas y fortaleciendo la sostenibilidad del negocio.  

---

## ⚙️ Ejecución del Proyecto

El proyecto puede ejecutarse en **Google Colab** (recomendado) o localmente con **Jupyter Notebook**.  

1. **Abrir el Notebook en Colab**  
   - Accede al archivo principal.  
   - Usa el botón `Open in Colab` o copia el código en un nuevo notebook.  

2. **Cargar datos tratados**  
   - El archivo `datos_tratados.csv` está disponible en el repositorio.  
   - Se carga automáticamente al ejecutar las celdas iniciales.  

3. **Ejecutar el análisis paso a paso**  
   - Cada celda incluye explicaciones, gráficos y resultados.  
   - No se requieren conocimientos avanzados de programación: basta con ejecutarlas en orden.  

4. **Explorar el modelo entrenado**  
   - El modelo final (`modelo_champion.pkl`) puede cargarse en el notebook.  
   - Se muestran ejemplos de predicciones y análisis de resultados.  

---

## 🧩 Estructura del Proyecto

El análisis está organizado en módulos progresivos:  

### 1. Preparación de datos  
- Importación de librerías y configuración.  
- Extracción del dataset `datos_tratados.csv`.  
- Eliminación de columnas irrelevantes y tratamiento de binarias.  
- Codificación de categóricas con `OneHotEncoder`.  

### 2. Análisis Exploratorio (EDA)  
- Distribución de la variable respuesta (**Evasión**).  
- Gráficos comparativos para variables categóricas y numéricas.  
- Mapas de calor de correlación y análisis de multicolinealidad.  
- Estudio de clientes con **≤12 meses de antigüedad**.  

### 3. Entrenamiento de Modelos  
- Split en entrenamiento, validación y prueba.  
- Normalización de variables.  
- Pruebas con distintos algoritmos de clasificación.  
- Evaluación mediante matriz de confusión, métricas (precision, recall, accuracy, F1) y curvas ROC/PRC.  

### 4. Validación y Confianza  
- Validación cruzada con **K-Fold** y **StratifiedKFold**.  
- Intervalos de confianza para recall en distintos **umbrales (0.3, 0.4, 0.5)**.  

### 5. Selección del Modelo Champion  
- Optimización de hiperparámetros con **GridSearchCV**.  
- Comparación de rendimiento bajo diferentes umbrales.  
- Selección final: **Random Forest (umbral = 0.3)**, priorizando recall.  

### 6. Pruebas con Nuevos Registros  
- Predicciones sobre registros reales y simulados.  
- Evaluación de robustez frente a escenarios de evasión/permanencia.  

### 7. Interpretabilidad del Modelo  
- Importancia de características (**Feature Importance**).  
- Variables más influyentes:  
  - Tipo de contrato (mensual vs largo plazo).  
  - Antigüedad.  
  - Servicio de internet (fibra óptica).  
  - Cargos mensuales y totales.  

---

## 🗂️ Estructura de los Datos

El dataset `datos_tratados.csv` es el resultado del **Desafío 1** y contiene las variables listas para modelado:  

- **Demográficas y contractuales**: Género, AdultoMayor, Pareja, Dependientes, TipoContrato, MetodoPago.  
- **Servicios contratados**: Telefonía, Internet (DSL, Fibra óptica, Ninguno), Soporte, Streaming, Seguridad, etc.  
- **Numéricas**: MesesAntiguedad, CargoMensual, CargoTotal, CuentasDiarias.  
- **Respuesta**: `Evasion` (Sí/No).  

---

## ✅ Conclusiones

Este **Desafío 2** marca la transición de un **EDA descriptivo** hacia un **modelo predictivo funcional**:  

- La empresa cuenta ahora con una herramienta capaz de **anticipar clientes en riesgo de evasión**.  
- El modelo Champion (Random Forest, umbral = 0.3) equilibra **recall y precisión**, priorizando la detección de clientes en riesgo.  
- Las pruebas con registros reales y simulados validan su aplicabilidad práctica.  
- El análisis de variables críticas brinda información estratégica para campañas de retención.  

En resumen, este proyecto no solo es un ejercicio académico, sino un **caso práctico aplicable en empresas reales**, demostrando cómo los datos y la IA pueden impulsar decisiones estratégicas.  

---
