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


