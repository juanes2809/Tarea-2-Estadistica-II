# Tarea 2 — Estadística II: Modelos de Regresión en Lenguaje Python

**Universidad Industrial de Santander (UIS)**  
**Escuela de Matemáticas — Bucaramanga**  
**Profesor:** Andrés Ríos-Gutiérrez  

## Integrantes del Grupo
* **Juan Jaimes**
* **Marco Galvis**
* **Maria Sarabia**
* **Juan Prada**

---

## Estructura del Repositorio

* [`Tarea_2_Estadistica_II.ipynb`](./Tarea_2_Estadistica_II.ipynb): Cuaderno de Jupyter con todo el código en lenguaje Python, resultados ejecutados, tablas estadísticas, figuras integradas y las interpretaciones **línea a línea** de todos los ítems de la tarea.
* [`Informe_Tarea_2_Estadistica_II.pdf`](./Informe_Tarea_2_Estadistica_II.pdf): Informe en formato PDF (único archivo compilado con portada institucional UIS, enlace a este repositorio, marco contextual, desarrollo estadístico, figuras de alta resolución y conclusiones). Fue generado con inteligencia artifical apartir del informe original del colab
* [`SB11_20231.TXT`](./SB11_20231.TXT): Base de datos oficial del ICFES Saber 11° (segunda cohorte 2023-1, Calendario B, $N = 12,704$ registros y $83$ variables).
* [`figuras/`](./figuras/): Directorio con los gráficos estadísticos en alta resolución ($300\text{ DPI}$).

---

## Resumen de Ítems Desarrollados

1. **Eliminación de valores faltantes (`icfes_sin_nan`)**: Filtrado vectorial de `SB11_20231.TXT` ($n = 11,853$ registros completos) y justificación metodológica desde la teoría de datos faltantes (*Missing At Random* — MAR).
2. **Selección de variables explicativas mediante diagramas de dispersión 2D**: Evaluación bivariada entre `ESTU_INSE_INDIVIDUAL` y cada una de las 5 pruebas académicas.
3. **Selección de variables explicativas mediante coeficientes de correlación de Pearson ($r$), Kendall ($\tau$) y Spearman ($\rho$)**: Contraste paramétrico y no paramétrico y análisis de multicolinealidad inter-pruebas.
4. **Selección de variables explicativas mediante el coeficiente de determinación ($R^2$) (Método "Salvo Una")**: Comparación del modelo lineal múltiple completo ($R^2 = 0.306011$) frente a los 5 modelos reducidos omitiendo una variable a la vez ($\Delta R^2_j$, estadístico $F$ parcial y VIF).
5. **Diagrama con el plano de dispersión 3D**: Ajuste y visualización tridimensional de `ESTU_INSE_INDIVIDUAL` con las dos variables más explicativas (`PUNT_INGLES` y `PUNT_MATEMATICAS`).
6. **Entrenamiento y evaluación con `train_test_split` (80% / 20%)**:
   * Modelo de Regresión Lineal Múltiple (con variables seleccionadas y modelo completo).
   * Modelo de Red Neuronal de Perceptrón Multicapa (`MLPRegressor` con `hidden_layer_sizes=(100,100,100,100,100,100), max_iter=500, activation='relu', solver='adam', learning_rate='invscaling'`).
   * Optimización de hiperparámetros (`StandardScaler` + arquitectura piramidal `64x32x16` + regularización $L_2$) y comparación con Regresión Polinomial Ridge y Gradient Boosting.
7. **Imputación de datos faltantes en `icfes_connan` ($n = 849$)** utilizando el modelo con el mejor ajuste.
8. **Predicciones de interés**: Análisis de estudiantes reales y perfiles prototípicos (incluyendo desempeño sobresaliente en Lectura Crítica y bajo puntaje en Inglés).
9. **Comparación con los puntajes de corte de admisión de la UIS**: Caracterización del perfil académico y socioeconómico de los potenciales admitidos a Medicina, Ingeniería de Sistemas, Ingeniería Civil/Industrial, Derecho y Matemáticas.
