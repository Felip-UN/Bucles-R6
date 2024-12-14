# Bucles-R6
Retos con bucles tipo while
## Retos propuestos
### 1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado
#### Diagrama de flujo
```mermaid
---
config:
  layout: fixed
---
flowchart TD
    n2["Definir como valor inicial de n =1"] --> n4["n&lt;=100 ?"]
    n5["imprime n y n^2"] --> n6["Sumar +1 a n"]
    n1["Inicio"] --> n8["Imprimir un titulo de orden"]
    n8 --> n2
    n4 -- V --> n5
    n6 --> n4
    n4 --> n7["End"]
    n4@{ shape: diam}
    n1@{ shape: rounded}
    n8@{ shape: rect}
    n7@{ shape: rounded}
```
#### Programa
```python
n=1
print("Orden:\nNumero -> Numero**2\n")
while n<=100:
  print(n,n**2)
  n+=1
```
### 2. Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000
#### Diagrama de flujo
```mermaid
---
config:
  layout: fixed
---
flowchart TD
    n1["Inicio"] --> n2["defirnir n = 1"]
    n2 --> n3["Imprimir titulo: Impares"]
    n3 --> n4["n&lt;1000 ?"]
    n4 -- F --> n6["definir n = 1"]
    n4 -- V --> n7["n es impar?"]
    n7 -- F --> n8["Sumar 1 a n"]
    n7 -- V --> n9["Imprimir n"]
    n9 --> n8
    n8 --> n4
    n10["n es par?"] -- V --> n12["Imprimir n"]
    n12 --> n11["Sumar 1 a n"]
    n6 --> n13["Imprimir titulo: Pares"]
    n10 -- F --> n11
    n13 --> n15["n&lt;=1000 ?"]
    n15 -- V --> n10
    n15 -- F --> n14["End"]
    n11 --> n15
    n1@{ shape: rounded}
    n4@{ shape: diam}
    n7@{ shape: diam}
    n10@{ shape: diam}
    n12@{ shape: rect}
    n11@{ shape: rect}
    n13@{ shape: rect}
    n15@{ shape: diam}
    n14@{ shape: rounded}
```
#### Programa
```python
n=1
print("Impares\n")
while n<1000:
  if n%2 != 0:
    print(n)
  n+=1
n=1
print("\nPares\n")
while n<=1000:
  if n%2 == 0:
    print(n)
  n+=1
```
### 3. Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
###
