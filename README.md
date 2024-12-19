# Bucles-R6
Retos con bucles tipo while

Se invita al usario a probar los codigos en un interprete como colab si desea echar un vistaso las salidas de los codigos o desea probar distintos valores, se avisa que algunas salidas son bien largas
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
#### Diagrama de flujo
```mermaid
---
config:
  layout: fixed
---
flowchart TD
    n1["Inicio"] --> n2["Asiganr un valor a n mediante el teclado"]
    n3["n &gt;= 2 ?"] -- V --> n4["imprimir n"]
    n4 --> n5["Restar 1 a n"]
    n5 --> n3
    n3 -- F --> n6["end"]
    n2 --> n3
    n1@{ shape: rounded}
    n3@{ shape: diam}
```
#### Programa
```python
n=int(input("ingresa un numero: "))
while n>=2:
  if n%2 == 0:
    print(n)
  n-=1
```
### 4. Imprimir el factorial de un número natural n dado
#### Programa
```python
if __name__=="__main__":
  num=int(input("Ingresa un numero "))
  v2=1
  acumulado=1

  while True:
    if num >= v2:
      acumulado=v2*acumulado
      v2+=1
    else:
      break
  print(str(num)+"! es:", acumulado)
```
Ingresa 5 salida deseada 120
#### Pseudocodigo
Con este me trabe un poco asi que plantee en un bloc de notas como deberia actuaria el programa (en este caso fue con el 4 pero el programa de arriba sirve con cualquier numero)
```python
a*b=acumulado
1*1=1
b==4? no
se guarda acumulado=1
1*2=2
b==4? no
se guarda acumulado=2
2*3=6 
b==4? no
se guarda acumulado=6
6* 4=24
b==4? si
se guarda acumulado=24 y se rompe el bucle
Fatorial = acumulado 24
```
### 5. Implementar un programa que ingrese un número de 2 a 50 y muestre sus divisores.
#### Programa
```python
numero_e=int(input("Tngresa un numero de entre 2 y 50 "))
posible_div=1
if numero_e>2 and numero_e<50:
  print("los divisores de",numero_e,"son:")
  while posible_div <= numero_e:
    if numero_e % posible_div==0:
      print(posible_div)
    posible_div+=1
else:
  print("Tu numero no entra en los limites establecidos")
```
Ingresa 12 salida deseada:


1

2

3

4

6

12
