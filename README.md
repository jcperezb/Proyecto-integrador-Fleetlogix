# FleetLogix - Proyecto Integrador

## Contexto

Este proyecto simula el proceso completo de modernización de datos de una empresa de logística.
La empresa opera con múltiples vehículos, conductores, rutas y entregas, y necesita pasar de sistemas básicos a una infraestructura de datos robusta.

El objetivo fue construir una solución completa: desde la generación de datos hasta un Data Warehouse en la nube con Snowflake.

## Enfoque del proyecto

El proyecto se desarrolló en tres etapas:

- Avance 1: Construcción del modelo relacional y generación de datos  
- Avance 2: Análisis mediante consultas SQL y optimización  
- Avance 3: Implementación en Snowflake y desarrollo de un pipeline ETL  

Cada avance construye sobre el anterior, manteniendo coherencia entre los datos y las decisiones técnicas.

## Tecnologías utilizadas

- PostgreSQL  
- Python (Pandas, Faker, SQLAlchemy)  
- Snowflake  
- SQL  

## Reflexión

A lo largo del proyecto, el mayor reto no fue solo escribir código, sino entender cómo se conectan todas las partes: base de datos, lógica de negocio, análisis y arquitectura.
También hubo obstáculos técnicos importantes (tipos de datos, carga en Snowflake, estructura del ETL), pero resolverlos permitió entender mejor cómo funciona un flujo real de datos.

## Estructura

El proyecto está organizado por avances para facilitar su evaluación y comprensión.
