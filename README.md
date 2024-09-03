# Reto-11
1. Desarrolle un programa que permita realizar la suma/resta de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
# Creamos 2 matrices
matriz1 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
matriz2 = [[9, 8, 7], [6, 5, 4], [3, 2, 1]]

# Creamos una función para sumar matrices
def sumaMatrices(a, b):
    # Condición para verificar que ambas matrices tengan las mismas dimensiones
    if len(a) == len(b) and len(a[0]) == len(b[0]):
        d = []  # Inicializa la matriz resultante

        # Itera sobre las filas de la primera matriz
        for i in range(len(a[0])):
            d.append([])  # Añade una nueva fila vacía a la matriz resultante
            # Itera sobre las columnas de la segunda matriz
            for j in range(len(b[0])):
                # Suma los elementos correspondientes de ambas matrices
                d[i].append(a[i][j] + b[i][j])
        return d  # Devuelve la matriz resultante

    else:
        # Si las dimensiones de las matrices no coinciden, retorna None
        return None

if __name__ == "__main__":
    c = sumaMatrices(matriz1, matriz2)  # Llama a la función de suma de matrices
    if c == None:
        print("No se puede sumar")  # Mensaje en caso de que las matrices no sean compatibles
    else:
        # Imprime la matriz resultante
        for fila in c:
            print("[", end=" ")
            for elemento in fila:
                print(elemento, end=" ")
            print("]")
```

2.Desarrolle un programa que permita realizar el producto de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.

```python
'''Producto de matrices'''

# Reciclamos las 2 matrices iniciales
matriz1 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
matriz2 = [[9, 8, 7], [6, 5, 4], [3, 2, 1]]

# Creamos una función para el producto de matrices
def productoMatriz(a, b):
    # Condición para verificar que ambas matrices tengan la misma dimensión
    if len(a) == len(b) and len(a[0]) == len(b[0]):
        d = []  # Inicializa la matriz resultante

        # Itera sobre las filas de la primera matriz
        for i in range(len(a[0])):
            d.append([])  # Añade una nueva fila vacía a la matriz resultante
            # Itera sobre las columnas de la segunda matriz
            for j in range(len(b[0])):
                # Multiplica los elementos correspondientes de ambas matrices
                d[i].append(a[i][j] * b[i][j])
        return d  # Devuelve la matriz resultante

    else:
        # Si las dimensiones de las matrices no coinciden, retorna None
        return None

if __name__ == "__main__":
    c = productoMatriz(matriz1, matriz2)  # Llama a la función de producto de matrices
    if c == None:
        print("No se puede multiplicar")  # Mensaje en caso de que las matrices no sean compatibles
    else:
        # Imprime la matriz resultante
        for fila in c:
            print("[", end=" ")
            for elemento in fila:
                print(elemento, end=" ")
            print("]")
```

3.Desarrolle un programa que permita obtener la matriz transpuesta de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.

```python
def matriz_transpuesta(P=list, x=int, y=int) -> list:
    # Inicializa una lista vacía para almacenar la matriz transpuesta
    Pa = []

    # Bucle para recorrer cada columna de la matriz original (que será una fila en la transpuesta)
    for fcf in range(y):
        Pa1 = []  # Inicializa una lista para la fila actual de la transpuesta
        # Bucle para recorrer cada fila de la matriz original (que será una columna en la transpuesta)
        for ff in range(x):
            # Asigna el valor de la matriz original a la posición transpuesta
            pa = (P[ff][fcf])
            Pa1.append(pa)  # Añade el valor a la fila de la transpuesta
        Pa.append(Pa1)  # Añade la fila completa a la matriz transpuesta

    # Devuelve la matriz transpuesta
    return Pa

if __name__ == "__main__":
    # Solicita al usuario que ingrese el número de filas de la matriz original
    x = int(input("Digite el número de filas que tendrá la Matriz P: "))
    # Solicita al usuario que ingrese el número de columnas de la matriz original
    y = int(input("Digite el número de columnas que tendrá la Matriz P: "))

    # Inicializa una lista vacía para representar la matriz original
    P = []

    # Bucle para llenar la matriz original con valores ingresados por el usuario
    for fcf in range(x):
        P1 = []  # Inicializa una lista para la fila actual
        for ff in range(y):
            # Solicita al usuario que ingrese el valor para cada posición de la matriz
            p = float(input(f"¿Qué valor irá en ({fcf+1}, {ff+1})?: "))
            P1.append(p)  # Añade el valor a la fila
        P.append(P1)  # Añade la fila completa a la matriz

    # Muestra la matriz original
    print("Matriz original: ")
    for fila in P:
        print(fila)

    # Muestra la matriz transpuesta
    print("Matriz transpuesta: ")
    for fila in matriz_transpuesta(P, x, y):
        print(fila)
```

4. Desarrollar un programa que sume los elementos de una columna dada de una matriz.

```python
def sumar_columnas_de_una_matriz(P=list, x=int, y=int) -> float:
    # Inicializa una variable para almacenar la suma de la columna
    suma_columna = 0
    # Itera a través de cada fila hasta el número de filas especificado por 'x'
    for fcf in range(x):
        # Suma el valor de la columna 'y-1' (ya que las listas en Python son indexadas desde 0)
        suma_columna += (P[fcf][y-1])
    # Devuelve la suma de los elementos de la columna especificada
    return suma_columna

if __name__ == "__main__":
    # Solicita al usuario que ingrese el número de filas de la matriz
    x = int(input("Digite el número de filas que tendrá la Matriz P: "))
    # Solicita al usuario que ingrese el número de columnas de la matriz
    e = int(input("Digite el número de columnas que tendrá la Matriz P: "))

    # Inicializa una lista vacía para representar la matriz
    P = []

    # Bucle para llenar la matriz con valores ingresados por el usuario
    for fcf in range(x):
        P1 = []  # Inicializa una lista para la fila actual
        for ff in range(e):
            # Solicita al usuario que ingrese el valor para cada posición de la matriz
            p = float(input(f"¿Qué valor irá en ({fcf+1}, {ff+1})?: "))
            P1.append(p)  # Añade el valor a la fila
        P.append(P1)  # Añade la fila completa a la matriz

    # Solicita al usuario que ingrese la columna que desea sumar
    y = int(input("¿Qué columna desea sumar?: "))

    # Llama a la función para sumar los elementos de la columna especificada
    sumar_columna = sumar_columnas_de_una_matriz(P, x, y)

    # Imprime el resultado de la suma de los elementos de la columna especificada
    print(f"La suma de los elementos de la {y} columna de la matriz {P} es igual a {sumar_columna}")
```

5. Desarrollar un programa que sume los elementos de una fila dada de una matriz.
```phyton
def sumar_filas_de_una_matriz(P=list, x=int, y=int) -> float:
    # Inicializa una variable para almacenar la suma de la fila
    suma_fila = 0
    # Itera a través de cada fila hasta el número de filas especificado por 'x'
    for fcf in range(x):
        # Suma el valor de la columna 'y-1' (ya que las listas en Python son indexadas desde 0)
        suma_fila += (P[fcf][y-1])
    # Devuelve la suma de los elementos de la fila especificada
    return suma_fila

if __name__ == "__main__":
    # Solicita al usuario que ingrese el número de filas de la matriz
    e = int(input("Digite el número de filas que tendrá la Matriz P: "))
    # Solicita al usuario que ingrese el número de columnas de la matriz
    x = int(input("Digite el número de columnas que tendrá la Matriz P: "))

    # Inicializa una lista vacía para representar la matriz
    P = []

    # Bucle para llenar la matriz con valores ingresados por el usuario
    for fcf in range(e):
        P1 = []  # Inicializa una lista para la fila actual
        for ff in range(e):
            # Solicita al usuario que ingrese el valor para cada posición de la matriz
            p = float(input(f"¿Qué valor irá en ({fcf+1}, {ff+1})?: "))
            P1.append(p)  # Añade el valor a la fila
        P.append(P1)  # Añade la fila completa a la matriz

    # Solicita al usuario que ingrese la fila que desea sumar
    y = int(input("¿Qué fila desea sumar?: "))

    # Llama a la función para sumar los elementos de la fila especificada
    sumar_fila = sumar_filas_de_una_matriz(P, x, y)

    # Imprime el resultado de la suma de los elementos de la fila especificada
    print(f"La suma de los elementos de la {y} columna de la matriz {P} es igual a {sumar_fila}")
```
