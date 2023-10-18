# Ejercicios sobre Python (2023)

### Solicitar el ingreso de tres productos con sus respectivos precios. Mostrar una lista de los productos comprados y mostrar el subtotal de los productos adquiridos.

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
