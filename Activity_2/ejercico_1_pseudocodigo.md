# Actividad de lapices
Realice un algoritmo para determinar cuánto se debe pagar por equis cantidad de lápices considerando que si son 1000 o más el costo es de $85 cada uno; de lo contrario, el precio es de $90. Represéntelo con el pseudocódigo y el diagrama de flujo. 

## Datos de entrada
| Nombre | Descripción |
| ------ | ----------- |
|Cantidad | Cuantos lápices se van a comprar |


## Datos de salida
| Nombre | Descripción |
| ---- | ---- |
| Unidad | Cuanto vale cada lápiz |
| Total | Cuanto es el total |

## PSEUDOCÓDIGO  
Inicio   
Mostrar “Cuantos lápices vas a comprar”   
Leer Cantidad   
Si Cantidad >= 1000   
    Unidad = 85   
Sino    
    Unidad = 90   
Fin si    
Total = Cantidad*Unidad   
Mostrar Total   
Fin   