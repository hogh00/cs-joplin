---
title: Pruebas unitarias en JavaScript
updated: 2022-08-15 18:31:54Z
created: 2022-08-15 14:48:30Z
---

# Pruebas unitarias en JavaScript

[toc]
* * *
Los test unitarios son una herramienta para prevenir bugs en ejecución. Sirven para asegurarnos de que un bloque de nuestro código, función o clase, funcionan correctamente y abarca la mayoría de casos de uso que se puedan dar. Además, proporciona robustez y calidad a nuestro código y confirma que funciona correctamente.

Las pruebas unitarias comprueban casos estándares (suposición explícita) es decir, no son perfectas.

Las pruebas unitarias son el proceso de dividir tu código en pequeñas funciones y probar cada una de esas funciones por separado. Las pruebas unitarias no se preocupan por el contenido interno del código, solo se preocupan por la **salida** con una **entrada** determinada.

Las características de las pruebas unitarias son:
- Automatizables: Deben funcionar sin ningún proceso manual.
- Cobertura total: Debemos de pasar por cada bloque escrito.
- Reutilizables: Podemos usarlas para probar otros bloques.
- Independientes: No pueden depender de otra prueba para funcionar.
- Rápidas de crear: Deben de ser algo conciso y que prueben algo muy particular.

## Jester
Investigar acerca de palabras clave `expect` y `toBe`
Para ejecutar un pruba se utiliza `npm test archivoprueba.js`	

Para monitorear más de una prueba a la vez, se agrega la opción `--watchAll` a la línea `"test": "jest"`  en el archivo `package.json`

## Operador ternario