---
title: Cadenas en Java
updated: 2022-10-04 03:12:31Z
created: 2022-10-02 00:56:48Z
tags:
  - java
---

# Cadenas en Java
[toc]
***
Las cadenas de caracteres son un [tipo de referencia](../Java/Literales,%20tipos%20de%20datos%20y%20variables%20en%20Java.md) inmutable, es decir, que no se puede cambiar un carácter en una cadena. Las cadenas pueden tener el valor `null`.

```java
String cadena = "Esta es una cadena de texto"; // Declaración literal

String str = new String("Esta es otra cadena de texto"); // Declaración con constructor
```

## Métodos para cadenas de texto
### length()
Retorna el número de caracteres en la cadena de texto. No confundir con `.length` (sin paréntesis) utilizado en arreglos.

### charAt( int index)
Retorna el carácter ubicado en el índice especificado. Recordar que las cadenas comienzan con el índice `0` y terminan con `length() - 1`.

### isEmpty()
Retorna `true` si la cadena está vacía, de lo contrario, retorna `falso`,

### toUpperCase()
Retorna una cadena en mayúsculas.

### toLowerCase()
Retorna una cadena en minúsculas.

### startsWith(prefijo)
Retorna `true` si la cadena empieza con el prefijo indicado.

### endsWith(sufijo)
Retorna `true` si la cadena termina con el sufijo indicado.

### contains(...)
Retorna `true` si la cadena contiene el argumento dado, este argumento puede ser una cadena o un solo carácter.

### substring(inicio, fin)
Retorna una subcadena a de la cadena original a partir del índice `inicio` y hasta `fin - 1`.

```java
String cadena = "Java"; // [0]J [1]a [2]v [3]a
String subcadena = cadena.substring(0,3); // Jav
```

### replace(viejo, nuevo)
Retorna una nueva cadena, reemplazando todas las ocurrencias de `viejo` con `nuevo`. Los argumentos pueden ser cadenas o caracteres.

### trim()
Retorna una copia de la cadena eliminando los espacios en blanco al principio y al final de la misma.

### concat(cadena)
Concatena la cadena a la que se le aplica el método con la cadena que se utiliza como argumento.

### equals(cadena)
Compara la cadena a la que se la aplica el método con la cadena utilizada como argumento, en caso de que sean iguales, retorna `true`.

> Recordar que si se utilizan los operadores ==, !=, se compararía la dirección de memoria y no el valor.

### equalsIgnorecase(cadena)
Mismo operación que `equals()` pero no es sensible a mayúsculas y minúsculas.

## Excepciones al procesar cadenas de texto
### NullPointerExcpetion
Ocurre al intentar ejecutar un método en una cadena con el valor de `null`.

### StringIndexOutOfBoundsExcpetion
Ocurre al intentar acceder a un carácter no existente mediante índices.

## Concatenación de cadenas de texto
Dos cadenas de texto puede unirse con el operador `+` o el método `concat()`. Cuando se concatena una cadena con un dato de otro tipo, este dato se convierte automáticamente a una cadena. 
```java
String shortString = "str";
int number = 100;

String result1 = shortString + number + 50; // the result is "str10050"
String result2 = number + 50 + shortString; // ¿Cuál es el resultado?
```
El resultado de `result2` es `150str` debido al orden de la operaciones.

> Nota: La concatenación es una operación no conmutativa, es decir, cadena1 + cadena2 no es igual a cadena2 + cadena1.

