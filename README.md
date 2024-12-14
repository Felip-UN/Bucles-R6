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
    n4["n&lt;=100 ?"] -- V --> n5["imprime n y n^2"]
    n2["Definir como valor inicial de n =1"] --> n4
    n5 --> n6["Sumar +1 a n"]
    n1["Inicio"] --> n8["Imprimir un titulo de orden"]
    n8 --> n2
    n4 -- F --> n7["End"]
    n6 --> n4
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
### 3. Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
###
