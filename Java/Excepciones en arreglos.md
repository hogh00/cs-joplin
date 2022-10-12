---
title: Excepciones en arreglos
updated: 2022-10-06 00:57:52Z
created: 2022-10-06 00:40:30Z
tags:
  - excepciones
  - java
---

# Excepciones en arreglos
[toc]
***
## [NullPointerException](../Java/Excepciones.md)

## NegativeArraySizeException
Si se intenta crear una arreglo con tamaño negativo, el código compilará, pero existirá una excepción de esta clase durante la ejecución.
```java
int negSize = -1;
int[] numbers = new int[negSize]; // excepción
```
> Un arreglo puede tener un tamaño mayor o igual que cero.

## ArrayIndexOutOfBoundsException
Esta excepción ocurre cuando se intenta acceder a un elemento inexistente en un arreglo.
```java
int[] array = { 1, 2, 3 }; // arreglo de enteros

int n1 = array[2]; // n1 es 3
int n2 = array[3]; // Excepción
```
Existe una excepción similar en las cadenas de texto cuando se intenta acceder a un elemento no existente en la cadena: `StringIndexOutOfBoundsException` .

Para evitar estas excepciones, se debe verificar que un índice dado se encuentre en el intervalo $[0, length -1]$.
```java
if (index < 0 || index > hardCodedArray.length - 1) {
            System.out.println("The index is out of bounds.");
        } else {
            System.out.println(hardCodedArray[index]);
        }
```