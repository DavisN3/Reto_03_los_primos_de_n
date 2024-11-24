# Reto_03_los_primos_de_n.
El presente repositorio es una guía paso a paso sobre como obtener los primos hasta un número "n" dado, usando pseudocódigo y diagramas de flujo.

## Contenido:
- ¿Qué es un número primo?
- Proceso en pseudocódigo para tener los primos hasta "n".
- Proceso en diagrama de flujo para tener los primos hasta "n".

## ¿Qué es un número primo?
Los primos, números caracterizados por no tener divisores más que ellos mismos y el uno pero, ¿hay alguna manera de determinar los primos hasta un número "n"?
La respuesta es sí, a lo largo de la historia se han desarrollado diferentes métodos para poder hacer esta ardua labor, algunos de los métodos son:
- "Fuerza bruta": Evaluar la divisibilidad de cada número desde 2 hasta n, descártando pares a excepción del 2.
- Criba segmentada: Aplica la Criba de Eratóstenes para rangos mayores, consiste en segmentar los rangos de 2 a n en rangos más pequeños, y aplicar la Criba de Erastóstenes en cada segmento de rango.
- Criba de Eratóstenes: Es un algoritmo que consiste en eliminar los múltiplos de cada primo hasta un número n, para dejar así a los números primos como los que no fueron descartados.

En este caso, por cuestiones de practicidad vamos a utilizar tanto en el diagrama de flujo como en el psudocódigo la Criba de Erastóstenes.

### Pasos a seguir:
1. Paso #1: Generar lista de números.
 - Hacemos una lista de los números desde 2 hasta nuestro número n; dado que en este rango ya se encuentran los primos que buscamos.
2. Paso #2: Procesamiento de números:
 - Empezamos con el primer número primo, h=2.
 - Descartamos todos los múltiplos de h, iniciando desde h^2 hasta n.
3. Paso #3: Seguir al siguiente número:
 - Incrementamos h al siguiente número que no haya sido descartado.
 - Repetimos el procedimiento del paso #2 hasta que h^2 sea mayor que n.
4.  Paso #4: Recolectar los números no descartados:
 - Los números no descartados en la lista, son nuestros números primos.


## Proceso en pseudocódigo de tener los primos hasta "n".
Con base a los pasos para ejecutar la Criba de Erastóstenes realizaremos este paso en pseudocódigo quedando algo tal que así:

```Pseudocódigo:
[Variables]
n : entero
h : entero
primos : arreglo de booleanos
i : entero

[Inicio]
escribir ("Ingrese el valor de n:")
leer (n)

Si (n < 2) entonces
  escribir ("No hay primos menores que 2.")
  salir
fin si

# Arreglo de primos:
primos := arreglo de tamaño (n+1) con todos los valores en 1 (True)
primos[0] := 0
primos[1] := 0

# Comenzamos con el primer primo del intervalo:
h := 2

# Generamos nuestro ciclo while:
mientras (h * h <= n) hacer:
    si (primos[h] == 1) entonces
        i := h * h
        Mientras (i <= n) hacer
            primos[i] := 0  # Marcar múltiplos de h como compuestos
            i := i + h
        fin mientras
    fin si
    h := h + 1
fin mientras

# Imprimimos nuestros primos:
escribir ("Los primos hasta el número n son:")
para i := 2 hasta n hacer
    si (primos[i] == 1) entonces
        imprimir (i)
    fin si
fin para

[fin]
```
## Proceso en diagrama de flujo para tener los primos hasta "n".
Con base a los pasos para ejecutar la Criba de Erastóstenes realizaremos este paso en diaframa de flujo quedando algo tal que así:

```mermaid
flowchart TD
%% Nodes
    A["Inicio"]
    B["Imprimir: Ingrese el valor de n:"]
    C["Leer n"]
    D{"n < 2"}
    E["Imprimir: No hay primos menores que 2."]
    F["Fin"]
    G["Arreglo de primos con tamaño (n+1) con todos los valores en True"]
    H["Declaramos: primos[0] := False"]
    I["Declaramos: primos[1] := False"]
    J["Declaramos: h := 2"]
    K{"h * h <= n"}
    L["h := h + 1"]
    M{"Mientras: i <= n"}
    N{"Si primos[h] == True"}
    O["Declaramos: i := h * h"]
    P["Marcar primos[i] := False"]
    Q["Incrementar i := i + h"]
    R["Imprimir: Los primos hasta n son:"]
    S{"Si primos[i] == True"}
    T["Imprimir i"]
    U["Fin"]

%% Edge connections between nodes
    A --> B --> C --> D
    D -- Sí --> E --> F
    D -- No --> G
    G --> H --> I --> J --> K
    K -- Sí --> N
    K -- No --> L
    N -- Sí --> M
    N -- No --> L
    M --> O --> P --> Q --> M
    M -- No --> R --> S
    S -- Sí --> T
    S -- No --> R
    T --> R
    L --> K
```
