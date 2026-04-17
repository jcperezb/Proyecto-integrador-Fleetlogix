# Avance 3 - Data Warehouse y ETL

## Objetivo

En esta etapa se buscó llevar el proyecto a un nivel más completo: no solo tener datos y consultas, sino construir un sistema analítico en la nube que permita trabajar con la información de forma estructurada.

Para esto, se implementó un Data Warehouse en Snowflake y se desarrolló un pipeline ETL que conecta la base de datos operativa con el entorno analítico.

## Modelo estrella

Se diseñó un modelo en estrella partiendo del modelo relacional construido anteriormente.

En el centro se encuentra la tabla de hechos:

- fact_deliveries

Esta tabla contiene la información principal de cada entrega, incluyendo métricas como:

- tiempo de entrega  
- distancia  
- estado de la entrega  

Alrededor se definieron dimensiones que permiten analizar la información desde distintos puntos de vista:

- dim_vehicle  
- dim_driver  
- dim_route  
- dim_date  
- dim_customer  

Este modelo facilita el análisis histórico y permite responder preguntas de negocio de manera más eficiente.

## Implementación en Snowflake

Se creó el entorno analítico en Snowflake con:

- Base de datos: `fleetlogix_dw`  
- Schema: `analytics`  
- Warehouse configurado con:
  - AUTO_SUSPEND  
  - AUTO_RESUME  

Se crearon las tablas correspondientes al modelo estrella y se cargaron datos utilizando archivos CSV y el comando `COPY INTO`.

También se configuró:

- **Time Travel**, para poder consultar datos históricos  
- **Secure Views**, para controlar el acceso según el tipo de usuario  

## Pipeline ETL

Se desarrolló un proceso ETL en Python que conecta PostgreSQL con Snowflake.

### Extract

Se extrajeron datos desde PostgreSQL de las tablas:

- vehicles  
- drivers  
- routes  
- trips  
- deliveries  

### Transform

En esta etapa se realizaron varias transformaciones clave:

- cálculo del tiempo de entrega  
- unión de tablas para construir la tabla de hechos  
- validación de calidad de datos (por ejemplo, evitar tiempos negativos)  
- selección de columnas relevantes para el modelo analítico  

### Load

Los datos transformados se cargaron en Snowflake en las siguientes tablas:

- dim_vehicle  
- dim_driver  
- fact_deliveries  

## Automatización

Se planteó la automatización del pipeline mediante Python, utilizando herramientas como `schedule` o ejecución programada, permitiendo que el proceso se ejecute diariamente sin intervención manual.

## Obstáculos y aprendizajes

Esta fue la etapa más compleja del proyecto.

Los principales problemas fueron:

- Confusión entre qué debía hacerse en SQL y qué en Python  
- Errores al cargar datos en Snowflake  
- Problemas con nombres de columnas (Snowflake usa mayúsculas)  
- Errores de tipos de datos, especialmente con timestamps  
- Dificultad para descargar datos directamente desde Snowflake  

Para resolver estos problemas se hicieron varios ajustes:

- Conversión de nombres de columnas a mayúsculas  
- Ajuste del ETL para asegurar compatibilidad con Snowflake  
- Simplificación de la tabla de hechos eliminando columnas problemáticas  
- Exportación de datos a CSV desde Python como alternativa  


## Aprendizaje clave

En esta etapa se entendió cómo funciona un flujo de datos completo en un entorno real:

- datos operativos  
- transformación  
- carga a un sistema analítico  

Más allá del código, el aprendizaje principal fue entender cómo se conectan todas las piezas.

## Resultado

Se logró construir un Data Warehouse funcional en Snowflake, acompañado de un pipeline ETL en Python que permite cargar y transformar los datos.

El sistema está preparado para análisis y puede escalarse fácilmente a escenarios más complejos.
