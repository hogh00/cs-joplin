---
title: Formatear la salida en Java
updated: 2022-10-06 00:27:34Z
created: 2022-10-05 23:42:25Z
tags:
  - java
---

# Formatear la salida en Java
[toc]
***
## El método printf()
Este método  se compone de dos campos. El primero es la cadena a la que se le va a dar formato. Esta cadena contiene las reglas para dar formato por medio de los **especificadores de formato**. El segundo campo debe llevar la lista de argumentos que se usaran para el formato de la cadena.
```java
System.out.printf("My Name is %s. I was born in %d", "Mike", 1998);
```

## El método String.format()
Esté método tiene una función similar a `printf()`. La diferencia es que este método devuelve una cadena en vez de imprimirla en pantalla.
```java
public static void main(String[] args){
    int age = 22;
    char initial = 'M';
    String surname = "Anderson";
    double height = 1.72;

    String details = String.format(
            "My name is %c. %s.%nMy age is %d.%nMy height is %.2f.",
            initial, surname, age, height);
    System.out.println(details);
}
```

La clase `String` ahora tiene un método `formatted(Object... args)` que puede usarse en vez de `String.format()`.
```java
public static void main(String[] args) {
    int age = 22;
    char initial = 'M';
    String surname = "Anderson";
    double height = 1.72;

    String details = "My name is %c. %s.%nMy age is %d.%nMy height is %.2f."
            .formatted(initial, surname, age, height);

    System.out.println(details);
}
```
Es importante mencionar que `formatted()` es un método de instancia, mientras que `String.format()` es un método de clase o estático.

## Especificadores de formato
|Especificador|Tipo de dato|Salida|
|---|---|---|
|%d|int, short, byte, long|Entero decimal|
|%c|char|Carácter Unicode|
|%f|double, float|Decimal de punto flotante|
|%e|double, float|Decimal en notación científica|
|%h|cualquiera|Cadena hexadecimal del método hashCode()|
|%s|cualquiera|Cadena de texto|
|%t|Fecha/Hora|%t es un prefijo para conversiones de fecha/hora, ver notas|

> Nota 1: En datos de punto flotante, se puede especificar la precisión con `%.nf`, donde `n` es el número de decimales deseados. 

> Nota 2: Se necesitan más banderas para darle el formato deseado a una fecha