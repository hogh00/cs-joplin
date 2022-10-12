---
title: Herramientas de construcción para Java
updated: 2022-10-10 00:41:33Z
created: 2022-10-07 03:14:33Z
---

# Herramientas de construcción para Java
[toc]
***
## [Apache Maven](../Java/Maven.md)
Es una herramienta lanzada en 2004 basada en el lenguaje extensible de marcado XML. Actualmente es la herramienta de construcción de proyectos Java más popular en la industria.

Maven sigue le concepto de **convención sobre configuración**, el cual significa que un desarrollador solo debe especificar aspectos no convencionales de la aplicaciones, y todos los aspectos comunes funcionan por defecto.

## [Gradle](../Java/Gradle.md)
Gradle fue lanzado en 2007 y es la herramienta estándar para aplicaciones Android. Gradle utiliza un lenguaje de dominio específico (DSL) basado en Kotlin y Groovy.

## Similitudes entre Maven y Gradle
- Ambos proyectos son de código libre bajo la licencia apache 2.0.
- Son soportados por los IDEs Java más populares.
- Cuentan con extensiones para añadir funcionalidad adicional.
- Tiene la misma estructura de directorio (Gradle adoptó la de Maven).
- Pueden configurarse sus repositorios de dependencias.

## Diferencias entre Maven y Gradle
- Lenguaje utilizado: Maven utiliza un lenguaje de marcado, XML, Gradle usa un lenguaje de programación basado en Groovy. Por esta razón, Gradle es más versátil y poderoso aunque también lo hace susceptible a bugs.
- Rendimiento: Gradle implementan estrategias como caches de construcción y compilación incremental, lo que lo hace más rápido que Maven en proyecto grandes.
- Extensiones: Maven cuenta con más extensiones que Gradle al ser más antiguo y popular.
- Manejo de dependencias. Maven sigue el orden de declaración de dependencias, mientras que Gradle hace referencia a un árbol de dependencias.

## Maven o Gradle, ¿Cuál utilizar?
Aquí algunas consideraciones para tomar la decisión:
- Tamaño del proyecto: Gradle es preferible en proyecto grandes, aunque este diferenciador se ha vuelto menos relevante con el aumento de popularidad de los microservicios.
- Personalización La configuración de Gradle es más sencilla que la de Maven
- Curva de aprendizaje: Gradle es más complicado que Maven.
- Soporte: Maven tiene una comunidad más grande y madura la de Gradle.