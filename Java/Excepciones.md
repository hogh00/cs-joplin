---
title: Excepciones
updated: 2022-10-05 23:03:24Z
created: 2022-10-05 19:04:00Z
tags:
  - excepciones
  - java
---

# Excepciones
[toc]
***
Una excepción es un evento que interrumpe el flujo normal de un programa.

## Excepciones verificadas
 
## Excepciones no verificadas
Algunas excepciones de tipo no verificadas son:
- ***ArithmeticException***:  Ocurre cuando una operación aritmética no válida toma lugar, como una división entera entre 0 o una expanión decimal infinita al utilizar `BigDecimal`.
- ***NumberFormatException***: Indica que una cadena no tiene el formato adecuado para ser convertida a un tipo numérico.

### NullPointerException
El valor de `null` se usa para indicar que una variable de referencia no tiene un valor asignado. Esto puede causar una excepción del tipo `NullPointerException` (NPE) que ocurre cuando el programa intenta utilizar ese valor.
```java
String someString = null; // a reference type can be null

int size = someString.length(); // NullPointerException (NPE)
```
Para evitar la excepción en el ejemplo, se verifica si el valor de la cadena es nulo o no y después se determina el valor de la variable `size`.
```java
int size = someString != null ? someString.length() : 0; // if the string is null, the size is 0
```
En el  caso de que se necesite comparar el valor de dos cadenas de texto y existe la posibilidad de que cualquiera de ellas sea nula, se puede utilizar la clase `java.util.Object`.
```java
String s1 = null;
String s2 = null;
        
if (Objects.equals(s1, s2)) { // no NPE here
    System.out.println("Strings are the same");
}
```