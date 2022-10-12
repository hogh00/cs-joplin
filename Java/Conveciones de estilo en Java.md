---
title: Conveciones de estilo en Java
updated: 2022-10-04 03:42:12Z
created: 2022-09-08 01:52:10Z
tags:
  - java
---

# Conveciones de estilo en Java

[toc]

Las convenciones o guías de estilo son una serie de recomendaciones sobre cómo escribir código legible para un lenguaje en particular. Las principales convenciones en el lenguaje Java son:

- [Convención de código de Oracle](https://www.oracle.com/technetwork/java/codeconventions-150003.pdf)
- [Guía de estilo de Google](https://google.github.io/styleguide/javaguide.html)

## Número de espacios
De acuierdo con la conveción de Oracle, se deben usar cuatro espacios como indentación en el código

```java
public class NumberOfSpacesExample {

    public static void main(String[] args) {
        System.out.println("Hi!");
        System.out.println("I'm a Java program.");
    }
}
```

## Ubicación de llaves
La llave de apertura `{` debe ir al dinal de la línea donde comienza el bloque. La llave de cierre `}` va al inicio de una nueva línea.

```java
public class NumberOfSpacesExample {

    public static void main(String[] args) {
        System.out.println("Hi!");
        System.out.println("I'm a Java program.");
    }
}
```

## Evitar espacios adicionales
Se debe evitar utilizar espacios dentro de paréntesis:

```java
System.out.println("Hello!"); // Correcto
System.out.println( "Hello!" ); // Incorrecto
```

Se deben evitar espacios antes de un punto y coma:

```java
System.out.println("No extra spaces"); // Correcto
System.out.println("It has an extra space") ; // Incorrecto
```

## Longitud de la línea
Evitar líneas de más de 80 caracteres

## Nombres de variables
Las reglas para nombrar variables en Java son las siguientes:

- Sensibles a mayúsculas y minúsculas
- Un nombre debe iniciar con una letra o los caracteres especiales `$` y `_`.
- Un nombre puede incluir caracteres alfanuméricos o caracteres especiales.
- Un nombre no puede ser una **palabra clave**.
- Los nombres de variables deben se claros y descriptivos. Los métodos debe utilizar verbos en modo infinitivo o imperativo.
- Los nombres de variables y métodos siguen la convención **camelCase**.
- Los nombres de clases e interfaces siguen la convención **PascalCase**.
- Las constantes de instancia y las constantes de clase siguen la convención **UPPER_CASE**

>Nota: En las **constantes locales** se suelen nombrar usando camelCase como si fueran variables convencionales. 