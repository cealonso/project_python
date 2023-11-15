# Ejercicios sobre Python (2023)

### Solicitar el ingreso de tres productos con sus respectivos precios. Mostrar una lista de los productos comprados con sus respectivos precios y mostrar el subtotal de los productos adquiridos.

```python 
product_name_1=input("¿Cual es la descripción del producto? ")
product_price_1=input("¿Cual es el precio? ")
product_name_2=input("¿Cual es la descripción del producto? ")
product_price_2=input("¿Cual es el precio? ")
product_name_3=input("¿Cual es la descripción del producto? ")
product_price_3=input("¿Cual es el precio? ")
print(product_name_1+" "+product_price_1)
print(product_name_2+" "+product_price_2)
print(product_name_3+" "+product_price_3)
subtotal=int(product_price_1)+int(product_price_2)+int(product_price_3)
print(subtotal)
```

### Modificar el ejercicio 1 usando listas.

```python
product_names=[]
product_prices=[]
product_names.append(input("¿Cual es la descripción del producto? "))
product_prices.append(input("¿Cual es el precio? "))
product_names.append(input("¿Cual es la descripción del producto? "))
product_prices.append(input("¿Cual es el precio? "))
product_names.append(input("¿Cual es la descripción del producto? "))
product_prices.append(input("¿Cual es el precio? "))
print(product_names[0]+" "+product_prices[0])
print(product_names[1]+" "+product_prices[1])
print(product_names[2]+" "+product_prices[2])
subtotal=int(product_prices[0])+int(product_prices[1])+int(product_prices[2])
print("Subtotal:"+str(subtotal))
total=subtotal
print("Total:"+str(total))
```

### Realizar un programa que permite solicitar el nombre del usuario junto con sus gustos personales. El algoritmo permitirá agregar sugerencias según el gusto seleccionado y almacenarlos en la misma lista. El programa finaliza cuando el usuario introduce la palabra bye.

```python
hobbies=[]
goodbyes='hasta luego'
username=input('¿Cúal es tu nombre? ')
hobby=""

def addSuggestion(hobby):
    if (hobby.upper()=="comer".upper()):
        hobbies.append("Salir con amigos")
    if (hobby.upper()=="beber".upper()):
        hobbies.append("Ir a Bares")
    if (hobby.upper()=="naturaleza".upper()):
        hobbies.append("Actividad Fisica")
    if (hobby.upper()=="futbol".upper()):
        hobbies.append("Ropa Deportiva")
        hobbies.append("Ir a la cancha")
    if (hobby.upper()=="cantar".upper()):
        hobbies.append("ir al karaoke")
    if (hobby.upper()=="estudiar".upper()):
        hobbies.append("Jugar")
    if (hobby.upper()=="autos".upper()):
        hobbies.append("Me gusta el Heavy Metal")


while (hobby != 'bye'): 
    hobby=input("¿Dime algún gusto tuyo, (bye es la despedida) "+ username + "? ") 
    addSuggestion(hobby)
    hobbies.append(hobby)
    print(hobbies)
print("Good Bye :"+username)

```
### Armar un módulo denominado recommendation.py que contenga el siguiente código:

```python
def addSuggestion(hobby,hobbies):
    hobbies.append(hobby)
    if (hobby.upper()=="comer".upper()):
        hobbies.append("Salir con amigos")
    if (hobby.upper()=="beber".upper()):
        hobbies.append("Ir a Bares")
    if (hobby.upper()=="Aprender idiomas".upper()):
        hobbies.append("Viajar")
    if (hobby.upper()=="naturaleza".upper()):
        hobbies.append("Actividad Fisica")
        hobbies.append("Meditación")
    if (hobby.upper()=="futbol".upper()):
        hobbies.append("Ropa Deportiva")
        hobbies.append("Ir a la cancha")
    if (hobby.upper()=="cantar".upper()):
        hobbies.append("ir al karaoke")
    if (hobby.upper()=="estudiar".upper()):
        hobbies.append("Jugar")
    if (hobby.upper()=="autos".upper()):
        hobbies.append("Me gusta el Heavy Metal")
    return hobbies

```
### Importar el modulo recommendation.py, solicitando el nombre del usuario y sus gustos. Listar sus gustos personales junto con las preferencias obtenidas en la función addSuggestion(). Luego armar una lista de distintos tipos de despedidas obtenidas de ChatGPT mostrándolas en forma aleatoria cuando el usuario decide despedirse de la aplicación.

```python

import recommendation as rec
import random 

hobbies=[]
# Obtenidos de ChatGPT
goodbyes=["Adiós", "Hasta luego", "Hasta la vista", "Nos vemos", "Chau", "Hasta pronto", "Hasta mañana", "Que tengas un buen día", "Cuidate"]
username=input('¿Cúal es tu nombre? ')
hobby=""

while (hobby != 'bye'): 
    hobby=input("¿Dime algún gusto tuyo, (bye es la despedida) "+ username + "? ") 
    if (hobby=='bye'):
        break
    hobbies=rec.addSuggestion(hobby,hobbies)
    print(hobbies)
print(random.choice(goodbyes)+" "+username)

```

### Realizar una función denominada evenNumber() que permita a través de una lista de números devolver una lista con solo los números pares. Realizar una comprobación mediante assert para verificar si la función devuelve lo que se espera que devuelva.

```python

def evenNumbers(lst_numbers,lst_evens):
    for aux in lst_numbers:
        if (aux%2)==0:
            lst_evens.append(aux)
    return lst_evens

assert evenNumbers([8,5,3,21,4],[])==[8,4]

```
### Escribir un programa que dado una lista de números reemplace en una nueva lista los múltiplos de 3 por la palabra “Fizz”, los múltiplos de 5 por “Buzz” y los múltiplos de ambos, es decir, los múltiplos de 3 y 5 por la palabra “FizzBuzz”.

```python

def fizzBuzz(lst_numbers,lst_fizzbuzz):
    for aux in lst_numbers:
        if ((aux%3==0) and (aux%5==0)):
            lst_fizzbuzz.append("FizzBuzz")
        elif (aux%5)==0:
            lst_fizzbuzz.append("Buzz")
        elif (aux%3==0):
            lst_fizzbuzz.append("Fizz")
        else:
            lst_fizzbuzz.append(aux)
    return lst_fizzbuzz

assert fizzBuzz([8,5,3,21,15,4],[])==[8,"Buzz","Fizz","Fizz","FizzBuzz",4]

```

### Escribir un programa que dado los primeros cien números imprima por pantalla la palabra “Fizz” si es múltiplos de 3, imprima “Buzz” si es múltiplo de 5 y en el caso de que sea múltiplo de 3 y de 5 la palabra “FizzBuzz”.

```python

def fizzBuzz2():
    for i in range(1, 100):
        if ((i % 3 == 0) and (i % 5 == 0)):
            print ('FizzBuzz')
        elif (i % 3) == 0:
            print ('Fizz')
        elif (i % 5) == 0:
            print ('Buzz')
        else:
            print (i)

fizzBuzz2()

```

### Escribir una función que dada una lista de cosas (Por ejemplo, una lista de frutas) busque un elemento en dicha  lista y cuente las cantidades de apariciones de dicho elemento en la lista.

```python

def findThings(lst_fruits,fruit):
    count=0
    for aux in lst_fruits:
        if aux==fruit:
            count=count+1
    return count   

assert findThings(["Banana","Anana","Pera","Manzana","Banana"],"Banana")==2

```

### Crear una aplicación que permita almacenar en un archivo denominado tareas.txt distintas tareas ingresadas por teclado. La cantidad de tareas debe ser solicitado tambien en la entrada. Cada tarea tiene una prioridad definido por un color: Rojo (Prioridad Alta), Amarillo (Prioridad Intermedia) y Verde (Prioridad Baja) que debe también ser solicitado por la aplicación. Según el Color ingresado la aplicación deberá convertir el color en una texto que indique tipo de prioridad es y almacenarlo también el archivo tareas.txt.

```python
from datetime import date

def get_priority(colour):
    if (colour=="Rojo"):
        priority="Importante"
    elif (colour=="Amarillo"):
        priority="Prioridad Intermedia"
    else:
        priority="Baja Prioridad"
    return priority

count=int(input("La cantidad de Eventos que quiero agendar : "))
file=open("tareas.txt","w",encoding="utf8")
today = str(date.today())
file.write(today+'\n')
for i in range(count):
    new_element=input("Que querés agendar? : ") #Se repite las count veces
    new_priority=input("Prioridad (Rojo, Amarillo, Verde) : ") 
    add_priority=get_priority(new_priority)
    file.write(new_element+'\t')
    file.write(add_priority+'\n')
file.close()

```
