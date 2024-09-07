# Reto_12

1. Consulte que hacen los siguientes métodos de strings en python: endswith, startswith, isalpha, isalnum, isdigit, isspace, istitle, islower, isupper.
## endswith
Determina si una cadena de texto termina con los caracteres de una cadena indicada, devolviendo true o false según corresponda.
## startswith
Indica si una cadena de texto comienza con los caracteres de una cadena de texto concreta, devolviendo true o false según corresponda.
## isalpha
Devuelve True si todos los caracteres son alfabéticos, False de lo contrario.
## isalnum
Recibe el código ASCII de una carácter y devuelve el valor 1 si el carácter que corresponde a ese código ASCII es una letra o un dígito numérico; en caso contrario devuelve un 0.
## isdigit
Indica si el carácter que ocupa la posición especificada en una cadena especificada se clasifica por categorías como un dígito decimal.
## isspace
Se utiliza para comprobar el espacio en la cadena . Devuelve verdadero si solo hay caracteres de espacio en blanco en la cadena. De lo contrario, devuelve falso.
## istitle
Devuelve True si todas las palabras de un texto comienzan con una letra mayúscula Y el resto de la palabra son letras minúsculas; de lo contrario, devuelve False . Los símbolos y números se ignoran.
## islower
Devuelve True si todos los caracteres están en minúsculas, de lo contrario False . No se comprueban los números, símbolos ni espacios, solo los caracteres del alfabeto.
## isupper
Toma una cadena y devuelve True si todas las letras de la cadena están en mayúsculas; de lo contrario, devuelve False . Este método ignora espacios, nuevas líneas, caracteres numéricos y especiales en la cadena.


2. Procesar el archivo y extraer:

* Cantidad de vocales
* Cantidad de consonantes
* Listado de las 50 palabras que más se repiten

```python
file = open('archivo.txt') 
texto = file.read() 
#Lista de vocales y lista de consonantes.
vocales=["a","e","i","o","u","A","E","I","O","U"]
consonantes=["b","c","d","f","g","h","j","k","l","m","n","p","q","r","s","t","v","w","x","y","z","B","C","D","F","G","H","J","K","L","M","N","P","Q","R","S","T","V","W","X","Y","Z"]
#Contador de vocales (V) y consonantes (C).
V=0
C=0
for letra in texto: #Itera sobre cada carácter del texto.
    if letra in vocales: #Si el carácter está en la lista de 'vocales' incrememta 1 al valor de V.
        V+=1
    elif letra in consonantes: #Si el carácter está en la lista de 'consonantes' incrememta 1 al valor de C.
        C+=1

print(f"El número de vocales es: {V}")
print(f"El número de consonantes es: {C}")

#Simbolos inecesarios.
simbolos = "|!\"#$%&/()=?'+*~[]^,;.:-_@\n\t<>" 

#Reemplaza cada símbolo de la lista en el texto por un espacio (" ").
for caracter in simbolos:
    texto = texto.replace(caracter," ")

texto = texto.lower() #Convierte todas las letras del texto a minúsculas.
palabras = texto.split(" ")
palabras = [palabra for palabra in palabras if (palabra!='') ]  

frecuencia_palabras = {} #Diccionario

for palabra in palabras: #Itera sobre cada palabra en la lista 'palabras'.
    if palabra in frecuencia_palabras: #Verifica si la palabra ya existe en el diccionario.
        frecuencia_palabras[palabra]+=1 #Si la palabra ya existe, se incrementa el valor de su frecuencia en 1.
    else:
#Si no existe en el diccionario.
        frecuencia_palabras[palabra] = 1 #Agrega la palabra al diccionario como clave y como valor se establece una frecuencia inicial de 1.

palabras_ordenadas = sorted(frecuencia_palabras.items(), key=lambda item: item[1], reverse=True)

# Imprime las 50 palabras que más se repiten junto con su frecuencia.
print("Las 50 palabras que más se repiten en el texto son:")
for palabra, frecuencia in palabras_ordenadas[:50]: # Itera sobre las primeras 50 tuplas de 'palabras_ordenadas'.
    print(f"{palabra} -> {frecuencia}")
```

<h2>Bibliografía</h2>
    <div class="bibliografia">
        <table>
            <tr>
                <th>Referencia</th>
            </tr>
          <tr>
                <td>https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith"></a></td>
            </tr> 
          <tr>

