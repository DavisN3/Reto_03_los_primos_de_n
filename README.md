# Reto_03_los_primos_de_n.
El presente repositorio es una guía paso a paso sobre como obtener los primos hasta un número "n" dado, usando pseudocódigo y diagramas de flujo.

## Contenido:
- Proceso en pseudocódigo para tener los primos hasta "n".
- Proceso en diagrama de flujo para tener los primos hasta "n".

## Proceso en pseudocódigo de tener los primos hasta "n".
Los primos, números caracterizados por no tener divisores más que ellos mismos y el uno pero, ¿hay alguna manera de determinar los primos hasta un número "n"?
La respuesta es sí, a lo largo de la historia se han desarrollado diferentes métodos para poder hacer esta ardua labor, algunos de los métodos son:
- "Fuerza bruta": Evaluar la divisibilidad de cada número desde 2 hasta n, descártando pares a excepción del 2.
- Criba segmentada: Aplica la Criba de Eratóstenes para rangos mayores, consiste en segmentar los rangos de 2 a n en rangos más pequeños, y aplicar la Criba de Erastóstenes en cada segmento de rango.
- Criba de Eratóstenes: Es un algoritmo que consiste en eliminar los múltiplos de cada primo hasta un número n, para dejar así a los números primos como los que no fueron descartados.

En este caso y por cuestiones de practicidad vamos a utilizar la Criba de Erastóstenes.

### Pasos a seguir:
- Paso #1: 
