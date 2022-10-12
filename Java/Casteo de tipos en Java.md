---
title: Casteo de tipos en Java
updated: 2022-10-01 16:38:37Z
created: 2022-09-18 02:32:04Z
tags:
  - java
---

# Casteo de tipos en Java
[toc]
***
El casteo es el proceso de convertir una variable de un tipo de dato a otro compatible. En Java, existe el casteo implícito y explícito.

## Casteo implícito
El casteo implícito es realizado por el compilador de forma automática cuando el tipo destino es más amplio que el tipo de origen. La imagen uestra la dirección en la que ocurre el casteo implícito.

![implicit-casting.svg](../_resources/implicit-casting.svg)

Cuando se castean valores `int` o `long` a `float` o `double` se corre el riesgo de perder información:
```java
long bigLong =  1_200_000_002L;
float bigFloat = bigLong; // 1.2E9 (= 1_200_000_000)
```

Al convertir un valor `char` a `int` se obtiene el valor Unicode (UTF-16) del caracter que se castea:
```java
char character = 'a';
char upperCase = 'A';

int ascii1 = character; // 97
int ascii2 = upperCase; // 65
```

## Casteo explícito
El casteo explícito puede usarse cuando se converte de un tipo más amplio que el tipo destino. En este caso se puede perder información sobre la magnitud de un valor y su precisión. Para realizar casteo explícito, se escribe el tipo destino entre parantesis antes del valor del tipo de origen.
```java
(tipoDestino) origen
```

```java
double d = 2.00003;

// Se pierde la parte fraccional
long l =  (long) d; // 2

// long es más amplio que int
int i = (int) l; // 2 

// Se castea porque el resultado es de tipo long (indicado por la letra L)
int val = (int) (3 + 2L); // 5

// Casteo de long a char
char ch = (char) 55L; // '7'
```

El **desbordadmiento de tipo** ocurre cuando se convierte un valor que está por encima del límite del tipo destino.
```java
long bigNum = 100_000_000_000_000L;
int n = (int) bigNum; // 276447232
```



