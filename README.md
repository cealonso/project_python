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
### Usar la librería Requests de Python para realizar solicitudes HTTP para obtener el dólar oficial del servidor https://dolarapi.com

```python

import requests
response = requests.get("https://dolarapi.com/v1/dolares/oficial")
dolar=response.json()
print("Compra USD Oficial : ", dolar['compra'])
print("Venta USD Oficial : ",dolar['venta'])

```
### Realizar una función con la sucesión de Fibonacci. La sucesión de Fibonacci es una sucesión infinita de números naturales que comienza con los números 0 y 1, y a partir de estos cada uno de los nuevos términos se calcula como la suma de los dos anteriores. Ejemplo: 0,1,1,2,3,5,8,13,21,34,55, ... 

```python

def fibonacci(x):
    # first two terms
    n1=0
    n2=1
    sum = n1 + n2
    print(n1)
    print(n2)
    print(sum)
    count=3
    while (count<x):
        n1 = n2
        n2 = sum
        sum = n1 + n2
        print(sum)
        count=count+1
val=15
fibonacci(val)

```
### Crear una aplicación que obtenga la suma de los datos usados en un dataframe (los datos son obtenidos del sitio https://pypl.github.io/PYPL.html que contiene el uso de los lenguajes de programación más usados en el 2023) Obtener una visualización grafica de dichos datos usando la librería matplotlib.

```python

import pandas as pd
import matplotlib.pyplot as plt

data = {
  "Language": ['Python', 'Java', 'JavaScript','C/C++','C#','PHP','R','TypeScript','Swift','Objective-C','Rust'],
  "Share": [27.99, 15.91, 9.18,6.76,6.67,4.86,4.45,2.95,2.7,2.32,1.98],
  "1-year trend":[0,-0.8,-0.3,0.2,-0.3,-0.3,0.4,0.1,0.6,0.2,0.3]
}
df = pd.DataFrame(data)
print(df) 
print("Popularity of Programming Language: ",df.Share.sum())
x = df.Language
y = df.Share
plt.scatter(x, y, color = 'hotpink')
plt.title('Popularity of Programming Language (2023)') 
plt.xlabel('Lenguaje', size=12)
plt.ylabel('Uso', size=12)
plt.legend(['Porcentaje de Uso'], loc='upper right')
plt.show()


```
###Desarrollar una calculadora sencilla que permita realizar las cuatro operaciones básicas: Suma, Resta, Multiplicación y División mediante el uso de una interfaz gráfica (GUI) para ello debe usar la librería grafica tkinter de Python.


```python

from tkinter import *
import tkinter.messagebox

def sum():
   num1=float(box1.get())
   num2=float(box2.get())
   total=num1+num2
   tkinter.messagebox.showinfo("Mensaje","El resultado es: %.2f"%total)
   box1.delete(0,20)
   box2.delete(0,20)

def subtraction():
   num1=float(box1.get())
   num2=float(box2.get())
   total=num1-num2
   tkinter.messagebox.showinfo("Mensaje","El resultado es: %.2f"%total)
   box1.delete(0,20)
   box2.delete(0,20)

def multiplication():
   num1=float(box1.get())
   num2=float(box2.get())
   total=num1*num2
   tkinter.messagebox.showinfo("Mensaje","El resultado es: %.2f"%total)
   box1.delete(0,20)
   box2.delete(0,20)

def division():
   num1=float(box1.get())
   num2=float(box2.get())
   total=num1/num2
   tkinter.messagebox.showinfo("Mensaje","El resultado es: %.2f"%total)
   box1.delete(0,20)
   box2.delete(0,20)

#Creacion de la GUI
gui = Tk()
#Titulo del GUI
gui.title("Calculadora")
gui.geometry("400x250+500+300")
var1 = StringVar()
var1.set("Escribe el primer numero:")
lblnum1 = Label(gui,textvariable=var1,height = 2)
lblnum1.pack()
num1=StringVar()
box1=Entry(gui,bd=4,textvariable=num1)
box1.pack()
var2 = StringVar()
var2.set("Escribe el segundo numero:")
lblnum2 = Label(gui,textvariable=var2,height = 2)
lblnum2.pack()
num2=StringVar()
box2=Entry(gui,bd=4,textvariable=num2)
box2.pack()
btnSum = Button(gui, text = "Suma", command = sum,width=15)
btnSum.pack()
btnSub = Button(gui, text = "Resta", command = subtraction,width=15)
btnSub.pack()
btnMul = Button(gui, text = "Multiplicacion", command = multiplication,width=15)
btnMul.pack()
btnDiv = Button(gui, text = "Division", command = division,width=15)
btnDiv.pack()

#Cargar la GUI
gui.mainloop()


```

