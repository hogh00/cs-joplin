---
title: Métodos en Java
updated: 2022-10-01 16:43:45Z
created: 2022-09-26 18:09:45Z
tags:
  - java
  - oop
---

# Métodos en Java
[toc]
***
Un método es una secuencia de instrucciones que puede ser invocada o referenciada múltiples ocasiones. A diferencia de una **función**, un método está asociado con un objeto. Java cuenta con un gran número de métodos predefinidos en su librería estándar, además de permitir la creación de métodos definidos por el usuario.

## Invocación de un método
Para invocar un método, se escribe su nombre y, en caso de ser necesario, se pasan sus parámetros como argumentos.
```java
imprimirNumero(7); // Este método imprime el número 7
```
Para llamar métodos fuera de la clase a la que pertenecen, se indica su clase como prefijo.
```java
Math.round(79.378);
Character.isLetter('a');
```

## Declaración de métodos
En general, un método en Java tiene un conjunto de [modificadores](../Java/Modificadores.md), un tipo de valor de retorno, un nombre, una lista de parámetros y un cuerpo. La combinación del nombre del método y sus parámetros se conoce como **firma del método**.
```java
// SINTAXIS DE UN MÉTODO
[modificadores][tipo de retorno] nombre(parámetros){
	// cuerpo
}

public static int sumarEnteros(int numero1, int numero2) {
	return numero1 + numero2;
}
```
Algunos métodos también cuentan con una lista de excepciones, que son elementos que definen el comportamiento del método en caso de que ocurra un error en el programa.

### Parámetros
Los parámetros son datos que se utilizan como elementos de entrada que serán utilizados en un método. Cuando los parámetros son tipos primitivos, se crea una copia del valor. En caso de que el parámetro sea un tipo de referencia, **se crea una copia a la referencia pero el valor continúa siendo el mismo**. Esta diferencia significa que si un valor que es referenciado se modifica dentro de un método, los cambios persistirán fuera de éste.

## Varargs
Los argumentos de longitud variable (***varargs***) permiten pasar un numero indefinido de argumentos del mismo tipo de dato para ser utilizados como parámetros en un método. Los varargs se procesan de manera similar a un arreglo del mismo tipo. Para declarar un parámetro como vararg, se utilizan tres puntos `...` después de especificar el tipo de dato.
```java
// SINTAXIS
public static void printNumberOfArguments(int... numbers) {
    System.out.println(numbers.length);
}

printNumberOfArguments(1); // 1
printNumberOfArguments(1, 2); // 2
printNumberOfArguments(1, 2, 3);  // 3
printNumberOfArguments(new int[] { }); // 0 (sin argumentos)
printNumberOfArguments(new int[] { 1, 2 }); // 2
```
Si un método tiene más de un parámetro, el parámetro vararg debe ser el último en la declaración.
```java
public static void method(int a, double... varargs) { /* do something */ }
```