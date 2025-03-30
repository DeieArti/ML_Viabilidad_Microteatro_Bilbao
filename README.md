# ML_Viabilidad_Microteatro_Bilbao
# Versión en español:
# Proyecto ML: ¿Tendría éxito un microteato en Bilbao?

## Objetivo del proyecto

Este proyecto de machine learning buscar estimar la asistencia a eventos de artes escénicas en Bilbao con el fin de evaluar la viabilidad de abrir un microteatro en la ciudad.Se han analizado variables como el tipo de evento, precio medio, capacidad, localización o gratuidad. 

## Dataset

- **Fuente principal**: Observatorio Vasco de la Cultur
- **Muestra final**: 130 eventos celebrados en Bilbao entre 2023 y 2024
- **Formato**: '.csv' (también disponible una muestra en `data_sample/`)
- **Variables destacables**:
  - 'tipo_evento': teatro, música, poesía, etc.
  - 'capacidad': aforo del evento
  - 'precio_medio': entrada promedio
  - 'evento_gratuito': binaria
  - 'asistentes': target numérico
  - 'distrito', 'lugar', 'ratio_ocupacion', etc.

## Proceso del trabajo

1. Recolección y limpieza de datos
2. Análisis exploratorio (EDA)
3. Ingeniería de variables seleccionadas o features (escalado, encoding, ratios)
4. Entrenamiento de modelo base
5. Optimización con 'GridSearchCV'
6. Comparación de modelos
7. Evaluación final en conjunto de test

##  EDA - Principales conclusiones

- La **capacidad** y el número de  **asistentes** están altamente correlacionados.
- Eventos **gratuitos** suelen atraer a más público. Pero es cierto que es una variable que discrimine demasiado.
- Los eventos celebrados en **Abando** y **Casco Viejo** tienen mayor afluencia.
- El **tipo de evento** influye mucho en la asistencia: teatro y musicales superan en media a monólogos o poesía. 

## Modelos empleados

| Modelo         | MAE final (de mejor a peor) |
|----------------|---------------------|
| Random Forest  | 137.30            |
| LightGBM       | 137.57              |
| XGBoost        | 298.17            |

> 🔎 **Moldeo final**: 'RandomForestRegressor' optimizado con 'GridSearchCV'

## Resultados

- **MAE(test set)**: ~ 137 asistentes
- **R^2 (test set)**: > 0.78

## Estructura del repositorio

1. ``src/data_sample``: archivo de datos de muestra utilizados en el proyecto que permitan ejecutar el código.
2. ``src/results_notebook``: notebook final resultante del proyecto.
3. ``src/models``: modelos guardados al ejecutar el código del proyecto.

#Versión en inglés:
# ML Project: Would a Microtheater Be Successful in Bilbao?

## Project Objective

This machine learning project aims to estimate attendance at performing arts events in Bilbao to assess the feasibility of opening a microtheater in the city. Various factors such as event type, average ticket price, venue capacity, location, and whether the event is free have been analyzed.

## Dataset

- **Main Source**: Basque Culture Observatory
- **Final Sample**: 130 events held in Bilbao between 2023 and 2024
- **Format**: `.csv` (a sample is also available in `data_sample/`)
- **Key Variables**:
  - `event_type`: theater, music, poetry, etc.
  - `capacity`: venue capacity
  - `average_price`: average ticket price
  - `free_event`: binary indicator
  - `attendees`: numeric target variable
  - `district`, `venue`, `occupancy_rate`, etc.

## Workflow

1. Data collection and cleaning
2. Exploratory Data Analysis (EDA)
3. Feature engineering (scaling, encoding, ratios)
4. Baseline model training
5. Optimization using 'GridSearchCV'
6. Model comparison
7. Final evaluation on the test set

## EDA - Key Findings

- **Capacity** and **attendees** are highly correlated.
- **Free events** tend to attract larger audiences, although this variable may not be highly discriminatory.
- Events held in **Abando** and **Casco Viejo** have the highest attendance.
- **Event type** strongly influences attendance: theater and musicals have a higher average attendance than stand-up comedy or poetry events.

## Models Used

| Model          | Final MAE (best to worst) |
|---------------|--------------------------|
| Random Forest | 137.30                    |
| LightGBM      | 137.57                    |
| XGBoost       | 298.17                    |

> 🔎 **Final Model**: 'RandomForestRegressor' optimized with 'GridSearchCV'

## Results

- **MAE (test set)**: ~ 137 attendees
- **R^2 (test set)**: > 0.78

## Repository Structure

1. `src/data_sample`: sample dataset files used in the project to ensure code execution.
2. `src/results_notebook`: final notebook summarizing the project.
3. `src/models`: saved models generated during project execution.
