# Bash

## Basics

```bash
variable="Hello World"               # asignar valor a una variable
variable=$1                          # capturar argumento de la línea de comandos
array=(1 2 3 4 5)                    # declarar un array
diccionario=(["clave"]="valor")      # declarar un diccionario
diccionario["otraclave"]="otrovalor" # agregar un elemento al diccionario
file="file.txt"                      # nombre del archivo
echo $variable                       # imprimir variable
echo ${array[0]}                     # imprimir primer elemento del array
echo ${diccionario["clave"]}         # imprimir valor de la clave
```

## Bucles

```bash
for i in {1..10}; do 
    echo $i
done

for i in {1..10..2}; do 
    echo $i 
done

for i in $(seq 1 10); do 
    echo $i 
done

for i in $(seq 1 2 10); do 
    echo $i 
done
```

## Condicionales

```bash
variable=True 

if [ $variable = True ]; then 
    echo "Verdadero" 
else # si no
    echo "Falso"
fi

if [ $variable = True ]; then 
    echo "Verdadero"
elif [ $variable = False ]; then
    echo "Falso"
else
    echo "Desconocido"
fi
```

## Funciones

```bash
function saludar(nombre) {
    echo "Hola $nombre"
}

saludar "Mundo"
```
