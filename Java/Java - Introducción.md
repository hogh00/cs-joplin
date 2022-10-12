---
title: Java - Introducción
updated: 2022-10-07 17:58:27Z
created: 2022-08-31 03:55:14Z
tags:
  - fundamentos
  - java
---

# Introducción a Java

[toc]
* * *

## Características de Java

### Portabilidad y neutralidad
“Escríbelo una vez, ejecútalo en cualquier lugar”, es decir, que Java puede ser ejecutado en cualquier máquina independientemente de su arquitectura o sistema operativo. Esto se logra mediante el proceso en el que el código fuente de Java es compilado y transformado en *bytecode*, que posteriormente es ejecutado en la Máquina Virtual Java o JVM.

### Orientado a Objetos
Permite declarar nuevos tipos de datos, además de las operaciones que se pueden hacer con ellos.

### Simple
Java fue diseñado para ser utilizado tanto por programadores novatos, como programadores con experiencia en otros lenguajes como C++.

### Ejecución Multihilo (Multithreading)
Distintas partes del código pueden ser ejecutadas de manera concurrente.

### Distribuido
Java puede acceder a objetos a través de internet como si se encontraran en el sistema de archivos local. Esta característica ahora se encuentra presente en casi todo lenguaje.

### Robusto
Java pone especial énfasis en la verificación temprana de posibles problemas. También posee un modelo de punteros que elimina la posibilidad de sobrescribir memoria y corromper datos.

### Interpretado y de alto rendimiento
La JVM ejecuta el bytecode generado en cualquier máquina y posee la capacidad de realizar compilación Just-in-Time para optimizar el código durante la ejecución.

### Dinámico
Java está diseñado para adaptarse a un entorno en evolución. Pueden crearse y añadirse nuevos métodos y variables a alguna librería sin algún efecto adverso.

## JVM, JRE y JDK
### JVM
La ***Java Virtual Machine*** es una simulación de una computadora que ejecuta el *bytecode* producido como resultado de la compilación de un lenguaje compatible con Java. En un lenguaje menos técnico, es un mediador entre el código y la máquina en donde se ejecuta.

### JRE
El ***Java Runtime Environment*** es un entorno de ejecución que contiene lo necesario para ejecutar programas compilados: la JVM y la librería de clases de Java (JCL).

JCL (*Java Core Libraries*) es el conjunto de librerías que proveen de la funcionalidad más común: clases esenciales, entrada/salida, operaciones matemáticas, entre otras.
[Repositorio de JCL](https://openjdk.org/groups/core-libs/).
> A partir de Java 11, JRE no se puede adquirir de manera separada. Se requiere de instalar el JDK completo si se desean ejecutar aplicaciones Java 11 o superior.

### JDK
Es la paquetería para el desarrollo de programas en Java. Incluye el JRE además de herramientas para desarrolladores: compilador, depurador, generador de documentación, archivero (junta los archivos `.class` en un sólo archivo `.jar`), etc.

![jvm-jre-jdk.svg](../_resources/jvm-jre-jdk.svg)

## Estructura básica de un programa en Java

Un programa de “Hola Mundo” escrito en Java luce de la siguiente manera:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
} 
```

Los elementos que conforman la estructura de un programa en java son:

1.  La clase pública: Es la unidad básica del programa. Toda aplicación Java debe tener al menos una clase. Para definir una clase se utiliza la palabra clave `class` seguida de su nombre, utilizando la convención de *PascalCase*.
2.  El método main: Para que el programa sea ejecutable, necesita de este método el cual funge como punto de entrada. Es importante mencionar que el nombre `main` es predefinido.
3.  Las sentencias del programa: dentro del bloque del método main, se colocan la secuencia de instrucciones para ejecutar en el programa. En el caso del programa de “Hola Mundo”, la declaración `System.out.println("Hello, World!")` imprime el mensaje en la pantalla.

##  [Literales, tipos de datos y variables en Java](../Java/Literales,%20tipos%20de%20datos%20y%20variables%20en%20Java.md) 

## La clase Scanner para obtener entrada de usuario

La clase `Scanner` permite obtener valores de diferentes tipos (String, numéricos, etc.) de la entrada estándar (*standard input*). Para utilizar esta clase, es necesario realizar una declaración de importación:

```java
import java.util.Scanner; // Declaración de importación
```

Y posteriormente se instancia un objeto de tipo
`Scanner`:

```java
Scanner scanner = new Scanner(System.in);
```

El parámetro de constructor `System.in` indica al programa que se leerá la entrada estándar.

### Métodos para la clase Scanner
- **next()**: Lee un *token* o una palabra sin espacios en blanco
- **nextLine()**: Lee desde la posición del cursor hasta el final de la línea, incluyendo espacios en blanco. Al finalizar, da un salto de línea.
- **nextInt()**: Lee el siguiente token como número entero.
- **nextLong()**: Lee un token como número tipo long.
- **nextBoolean()**: Lee un token de tipo booleano.
- **hasNext()**: Entrega un valor booleano. Verifica si el escaner tiene un token por leer en la entrada especificada.

## Operadores
Los operadores son símbolos que permiten manipular o evaluar datos.

### Incremento y decremento
Los operadores de incremento y decremento modifican el valor de la variable indicada por una unidad. Esto operadores tiene dos formas, preijo y posfijo.

- **Prefijo (++n,  --n)**: Incrementa/decrementa el valor de la variable antes de ser utilizada.
```java
int a = 4;
int b = ++a;

System.out.println(a); // 5
System.out.println(b); // 5
```
- **Posfijo (n++, n--)**: Incrementa el valor de la variable despues de ser utilizada.
```java
int a = 4;
int b = a++;

System.out.println(a); // 5
System.out.println(b); // 4
```
### Operadores aritméticos
- Adición `+`
- Resta `-`
- Multiplicación `*`
- División `/`
- Módulo (cociente) `%`
- Operador unario más `+`
- Operador unario menos `-`

Los operadores aritméticos tienes las mismas reglas de prioridad que en la aritmética convencional y puede utilizarse paréntesis para cambiar el orden de ejecución o agregar claridad.

- Paréntesis
- Operadores unarios
- Multiplicación y división
- Adición y resta

### Operadores relacionales
Java ofrece seis operadores relacionales para comparar números:

- Igualdad (==)
- Desigualdad (!=)
- Mayor que (>)
- Menor que (<)
- Mayor o igual que (>=)
- Menor o igual que (<=)

El resultado de estas operaciones es un booleano.

> Ejemplo:
> Hay tres niños en la clase de deportes. Quieres asegurarte se formen de acuerdo con su estatura en orden descendiente. El siguiente programa lee tres enteros `h1`, `h2` y `h3` y después verifica si `h1 >= h2` y `h2 >= h3`.

```java
import java.util.Scanner;

public class CheckDescOrder {
   public static void main(String[] args) {
       Scanner scanner = new Scanner(System.in);

       int h1 = scanner.nextInt();
       int h2 = scanner.nextInt();
       int h3 = scanner.nextInt();

       boolean descOrdered = (h1 >= h2) && (h2 >= h3);

       System.out.println(descOrdered);
   }
}
```

### Operadores lógicos
Los operadores lógicos permiten evaluar sentencias y obtener un valor booleano como resultado. Java cuenta con los siguientes operadores lógicos:

- NOT (!): Operador unario que niega o invierte el valor booleano de la expresión original
- AND (&): Operador unario que retorna `true` si las dos expresiones evaluadas son verdaderas.
- AND de circuito corto (&&): Evalúa la primera expresión y si esta es falsa, omite la evaluación de la segunda expresión y retorna el valor de toda la evaluación como `false`.
- OR (|): Operador binario que retorna `true` si alguna de sus expresiones es verdadera.
- OR de corto circuito (||): Devuelve `true` tan pronto la primera expresión resulta verdadera.
- XOR (^): Operador binario que retorna `true` cuando la expresiones evaluadas tienen valores distintos.

El orden de precedencia de operaciones lógicas es el siguiente: NOT, XOR, AND, OR. Al igual que las operaciones aritméticas, se pueden emplear paréntesis para alterar la prioridad de las operaciones.

```java
boolean b = true && !false; // verdadero, porque !false se evalúa primero
```

## Ejecución condicional
La ejecución condicional es una construcción que permite a un programa realizar una acción dependiendo del valor de la condición a la que está ligada.

### Declaración if
Una declaración `if` ejecuta una instrucción si su condición es evaluada como verdadera. Si la condición se evalúa como falsa, otra instrucción puede ser ejecutada con las declaraciones `else if` y `else`.
```java
if (expression0) {
    // do something
} else if (expression1) {
    // do something else 1
// ...
} else if (expressionN) {
    // do something else N
}
```

### Operador ternario
Este operador, también conocido como **operador condicional**, evalúa una condición y elige uno de los dos casos a ejecutar. Se considera una forma más concisa del enunaciado `if ... else`.
```java
// Sintaxis
resultado = condicion ? casoVerdadero : casoFalso;
```
Es importante que las expresiones `casoVerdadero` y `casoFalso` sean expresiones que puedan reducirse a un tipo de dato en común. Esto define el ripo de `resultado`.

Java permite anidar un operador ternario dentro de otro una vez, aunque esto no es aconsejable.
```java
int a = 5;
int b = 3; 
String result = a == b ? "equal" :
                a > b ? "more" : "less";
```

### Switch
La declaración `switch` es una manera de elegir entre diferentes casos con base en el **valor de una variable** (no el de una expresión). 
```java
// SINTAXIS
switch (variable) {
    case value1:
        // do something here
        break;
    case value2:
        // do something here
        break;
    
    //... other cases
    
    case valueN:
        // do something here
        break;
    default:
        // do something by default
        break; // it can be omitted
}
```

## Bucles
Un bucle es una secuencia de código que se ejecuta de manera repetida hasta que una condición deja de cumplirse. Los bucles se categorizan en controlados y no controlados.

### Bucles no controlados
En un bucle no controlado (o indefinido) no se conocen las veces en la que se repetirá el código, y puede ejecutarse un número indeterminado de veces. Para declarar un bucle indefinido, se utilizan las declaraciones `while` y `do...while`.
```java
// Sintaxis de do...while
do {
	instrucción1;
	...
	instruccionN;
} while (condición);

// Sintaxis de while
while (condición) {
	instrucción1;
	...
	instruccionN;
}
```

La diferencia entre `do...while` y `while` radica en que `do...while` primero ejecuta y después evalua, mientras que `while` primero evalúa y después ejecuta. Esto significa que un caso en el que la condición a evaluar sea falsa, en el caso de `while` no se ejecutará el código dentro del bucle,  pero en el caso de  `do...while`, siempre se ejecutará al menos una vez.

### Bucles controlados
Un bucle definido es aquel en el que se define de antemano las veces que va a repetirse. Para crear bucles definidos en Java, se utiliza una declaración  `for`.
```java
for (inicialización; condición; midificación) {
    // instrucciones;
} 
```


## Errores
### Errores durante la compilación
Estos errores evitan que el programa se compile de manera exitosa.
- Errores de sintaxis
- Nombre de archivo incorrecto
- Invocación de métodos no existentes
- Entre otros

Generalmente para evitar este tipo de errores, los desarrolladores utilizan Entornos Integrados de Desarrollo con analizadores de código estático que les ayudan a identificar este tipo de problemas antes de compilar. 

### Errores durante la ejecución
Los errores durante la ejecución también son conocidos como ***bugs***. Estos errores causa que el programa se comporte de manera inesperada o incluso se detenga su ejecución. Hay dos tipos de errores durante la ejecución:
1. **Errores lógicos:** El programa produce el resultado incorrecto debido a que el código no es el correcto.
2. **Eventos excepcionales no manejados:** Tales como la división entre 0, archivos inexistentes, y otros casos inesperados.

Algunas estrategias para eliminar esta clases de errores de un programa son:
- Depurar el código
- Escribir pruebas unitarias automatizadas
- Utilizar la práctica de revisión de código como parte del proceso de desarrollo. 

### Excepciones en Java
