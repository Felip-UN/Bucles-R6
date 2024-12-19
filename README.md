# Bucles-R6
Retos con bucles tipo while

Los codigos fueron comprobados y son funcionales pero se invita al usario a probar los codigos en un interprete como colab si desea echar un vistaso las salidas de los programas o desea probar distintos valores (en caso que se pueda), se avisa que algunas salidas son bien largas
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
print("Orden:\nNumero -> Numero**2\n") #Unicamente para guiar al usuario a saber cual es cual
while n<=100:
  print(n,n**2) #imprime numero y numero al cuadrado
  n+=1
```
**Salida generada:** **muy extensa (ejecutar en interprete si desea ver resultados)*
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
print("Impares\n") #Titulo que se imprimira
while n<1000: #el bucle se rompe hasta cuando n tiene valor 1000
  if n%2 != 0: #Verifica si el numero es impar
    print(n)
  n+=1
n=1
print("\nPares\n") #Titulo que se imprimira una vez finalizado el primer bucle
while n<=1000: el bucle se rompe hasta cuando n tiene valor 1001
  if n%2 == 0: #Verifica si el numero es par
    print(n)
  n+=1
```
**Salida generada:** **muy extensa (ejecutar en interprete si desea ver resultados)*

### 3. Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
#### Diagrama de flujo
```mermaid
---
config:
  layout: fixed
---
flowchart TD
    n1["Inicio"] --> n2["Asiganr un valor a n mediante el teclado"]
    n4["imprimir n"] --> n5["Restar 1 a n"]
    n5 --> n3["n &gt;= 2 ?"]
    n3 -- F --> n6["end"]
    n7["n&gt;=2?"] -- V --> n3
    n7 -- F --> n8["print(Tu numero no entra en los limites establecidos)"]
    n2 --> n7
    n9["es par?"] -- V --> n4
    n9 -- F --> n5
    n3 -- V --> n9
    n1@{ shape: rounded}
    n3@{ shape: diam}
    n7@{ shape: diam}
    n9@{ shape: diam}
```
#### Programa
```python
n=int(input("ingresa un numero >=2 : "))
if n>=2:
  while n>=2:
    if n%2 == 0:
      print(n, end=" ")
    n-=1 #esto asegura que sea descendiente
else:
  print("Tu numero no entra en los limites establecidos")
```
Ingresa 6 salida generada: 6 4 2


Ingresa 5 salida generada: 4 2


Ingresa -2 salida generada: Tu numero no entra en los limites establecidos
### 4. Imprimir el factorial de un número natural n dado
#### Programa
```python
if __name__=="__main__":
  num=int(input("Ingresa un numero: "))
  v2=1 #a este se le sumara +1 por ciclo
  acumulado=1 #este sera el factorial que se imprimira al final
  while True: #es la manera mas sencilla de hacer un bucle indefinido :P
    if num >= v2: #este es el limite indirectamente
      acumulado=v2*acumulado #Lo explico en el pseudocodigo de abajo
      v2+=1
    else:
      break
  print(str(num)+"! es:", acumulado) #esto es unicamente para una salida "elegante" y visualmente entendible
```
Ingresa 4 salida generada: 4! es: 24


Ingresa 5 salida generada: 5! es: 120


Ingresa 8 salida generada: 8! es: 40320
#### Pseudocodigo
Con este reto me confundi un poco asi que plantee en un bloc de notas de como actuaria el programa y la salida que daria (en este caso fue con el 4 pero el programa de arriba sirve con cualquier numero)
```python
a*b=valor a guardar en acumulado
1*1=1
b==4? no
se guarda acumulado=1
1*2=2
b==4? no
se guarda acumulado=2
2*3=6 
b==4? no
se guarda acumulado=6
6*4=24
b==4? si
se guarda acumulado=24 y se rompe el bucle
Fatorial = acumulado 24
```
### 5. Implementar un programa que ingrese un número de 2 a 50 y muestre sus divisores.
#### Programa
```python
numero_e=int(input("Tngresa un numero de entre 2 y 50 "))
posible_div=1
if numero_e>2 and numero_e<50: #verifica si la condicion es cumplida
  print("los divisores de",numero_e,"son:")
  while posible_div <= numero_e: #EL bucle se rompe cuando el numero que dividira sea >numero_e
    if numero_e % posible_div==0: #verifica si "posible_div" es divisor del numero
      print(posible_div, end=" ") #de serlo imprimira el numero y ademas lo imprimira seguido
    posible_div+=1
else:
  print("Tu numero no entra en los limites establecidos") #no se cumplio la condicion
```
Ingresa 12 salida generada: 1 2 3 4 6 12


Ingresa 1 salida generada: Tu numero no entra en los limites establecidos
### 6. Implementar el algoritmo que muestre los números primos del 1 al 100.
#### Funcion definida y su explicacion
```python
def sera_primo(numero):
  #Las condiciones a comprobar:
  if numero<0: #Un numero primo es mayor que cero
    return False #salida que se dara si se cumple esta condicion
  v2=2 #se le sumara +1 por ciclo
  while v2 <= numero**0.5: #Es una mausquerramienta que nos ayudara mas tarde, explicacion abajo
    if numero % v2 ==0: #Revisara si el numero resulta tener algun divisor distinto de 1 y el mismo 
      return False # salida que se dara si se cumple esta condicion con algun numero
    v2 += 1
  return True #Si ninguna condicion resulta ser cierta esta sera la salida
```
**Mausquerramienta:** Pense en utilizar todos los valores menores que el numero ingresado, pero al solo comprobar si su raiz cuadrada es divisible por algun numero menor o igual a esta significara que ese numero por el que se dividio tambien es divisor del numero original lo que significara que no es un numero primo
#### Programa
```python
def sera_primo(numero):
  if numero<0: 
    return False 
  v2=2
  while v2 <= numero**0.5: 
    if numero % v2 ==0: 
      return False
    v2 += 1
  return True
if __name__=="__main__":
  #iniciaremos desde el 2 ya que el 1 no cuenta como primo
  contador=2 #a este se le sumara +1 por ciclo
  while contador<=100: #el bucle se rompe cuando contador sea >100
    respuesta=sera_primo(contador) #Esta operacion revisara si el numero actual es primo
    if respuesta==True: #Salida True, el numero es primo
      print(contador, end=" ") #de serlo lo imprime
    contador += 1
```
Salida generada: 2 3 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97 
