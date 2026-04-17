# Avance 1 - Modelado y generación de datos

## Objetivo

En esta etapa se construyó la base del proyecto: un modelo relacional que representa la operación logística de FleetLogix y su respectiva población con datos sintéticos.

## Modelo de datos

Se trabajó con seis tablas principales:

- vehicles  
- drivers  
- routes  
- trips  
- deliveries  
- maintenance  

Estas tablas no son independientes: están conectadas entre sí para representar cómo funciona realmente la operación.

Por ejemplo:
- un viaje depende de un vehículo, un conductor y una ruta  
- una entrega depende de un viaje  
- un mantenimiento depende de un vehículo  

## Generación de datos

Se utilizó Python con Faker para generar datos sintéticos, asegurando:

- integridad referencial  
- coherencia entre tablas  
- consistencia temporal  

Se implementó `random.seed(42)` para mantener reproducibilidad.

## Aprendizaje clave

Al inicio, la dificultad principal fue entender que no se trataba solo de generar datos, sino de mantener relaciones lógicas entre ellos.

Por ejemplo, no podía existir:
- un trip con un vehicle_id inexistente  
- entregas sin viaje  
- tiempos incoherentes  

## Obstáculos

- Confusión inicial sobre dónde ejecutar el código (VS Code vs PostgreSQL)  
- Dificultad para entender conceptos como constraints y consistencia temporal  
- Interpretación de loops y generación masiva de datos  

Estos obstáculos se resolvieron entendiendo cada parte del código “como texto” y no solo ejecutándolo.

## Resultado

Se generó un conjunto de datos coherente que simula dos años de operación logística, listo para análisis en las siguientes etapas.
