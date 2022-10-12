---
title: Archivo Java (JAR)
updated: 2022-10-09 04:47:21Z
created: 2022-10-08 04:51:09Z
---

# Archivo Java (JAR)
Un Archivo Java (JAR) es un formato de archivo de plataforma independiente el cual empaqueta múltiples recursos y los distribuye como un solo archivo. Está comprimido con un algoritmo ZIP para reducir su tamaño y facilitar su distribución en red.

## Estructura de un archivo JAR
Un archivo JAR agrega los archivos compilados `.class`, archivos de configuración como `.json` y `.xml` , imágenes y otros recursos en un solo archivo comprimido.

Se recomienda que también se incluya un archivo `MANIFEST.MF` en una carpeta `META-INF`. Este archivo contiene los metadatos del JAR.

Este archivo se conforma de encabezados en donde el nombre y el valor se separan con dos puntos (:).
```
Manifest-Version: 1.0
Created-By: 9.0.1 (Oracle Corporation)
Main-Class: second.Main

```
El encabezado opcional `Main-Class` define la ruta relativa de la clase que contiene en método `main` sin agregar la extensión `.class`. También es importante mencionar que la última línea del archivo `MANIFEST.MF` **debe terminar con un línea nueva o retorno de carro.**

```
archivo.jar
├── META-INF
│   └── MANIFEST.MF
├── second
│   ├── Main.class
│   └── MyIcon.png
└── third
    └── another
        └── OneMore.class
```
Los archivos `.class` están agrupados en **paquetes**, que no son más que directorios que en vez de separarse con diagonales `third/another`, lo hacen con puntos `third.another`.

## Ejecutar un archivo JAR
Hay dos formas de ejecutar un archivo JAR dependiendo de si se incluye el encabezado `Main-Class` en el archivo manifiesto o no.
- Si el encabezado no está presente:
```
java -cp app-without-main-class-header.jar path.to.Main
```
- Si el encabezado está presente:
```
java -jar app-with-main-class-header.jar
```