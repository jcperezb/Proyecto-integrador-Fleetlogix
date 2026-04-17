# Avance 2 - Queries y optimización

## Objetivo

En esta etapa se buscó analizar la operación logística mediante consultas SQL y mejorar su rendimiento.

## Desarrollo de queries

Se trabajó con tres niveles:

### Básicas
Consultas simples para:
- conteos  
- listados  
- agregaciones  

### Intermedias
Consultas con:
- múltiples joins  
- subconsultas  
- filtros por tiempo  

### Complejas
Consultas con:
- CTEs  
- funciones de ventana (RANK, LAG)  
- métricas avanzadas  

## Qué aprendí

Aquí fue donde realmente entendí qué es una query.

Al inicio no era claro, pero luego se entendió que una query es simplemente una pregunta a la base de datos.

Ejemplo:
- ¿Cuántos vehículos hay?  
- ¿Cuál es el promedio de entregas por conductor?  

## Optimización

Se utilizó:

```sql
EXPLAIN ANALYZE
