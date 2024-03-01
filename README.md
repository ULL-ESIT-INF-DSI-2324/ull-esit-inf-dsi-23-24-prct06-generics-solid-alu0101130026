[![Coverage Status](https://coveralls.io/repos/github/ULL-ESIT-INF-DSI-2324/ull-esit-inf-dsi-23-24-prct06-generics-solid-alu0101130026/badge.svg?branch=main)](https://coveralls.io/github/ULL-ESIT-INF-DSI-2324/ull-esit-inf-dsi-23-24-prct06-generics-solid-alu0101130026?branch=main)

## Informe Práctica 6

### Clases e interfaces genéricas. Principios SOLID.

#### Datos identificativos

- Diego Díaz Fernández
- alu0101130026@ull.edu.es

### Introducción y objetivos

### Ejercicio 1 - La mudanza

Para este primer ejercicio, se nos pide que desarrollemos un sistema de información para una mudanza, en el cual tendremos distintos enseres que se almacenan en cajas. Podremos añadir o quitar enseres en la caja, buscar si hay un enser en concreto o listar el contenido de una caja por consola.

Para la implementación de este ejercicio se dividió el programa en 4 archivos. El primero es donde está la interfaz enser, que solo tiene el nombre como atributo pero que lo implementarán los otros archivos. El segundo es la interfaz box, que implementa enseres, además de tener también los métodos para los operaciones de las cajas. El tercero es la clase BoxManager, en la cual se definen 5 funciones: un constructor, una para añadir elementos en la caja, otra para quitarlos, otra para listar por consola los enseres de la caja y la última para buscar algún enser.

Mencionar también que se creó un main, en el cual se ha instanciado un ejemplo de caja y se realizan algunas inserciones, exclusiones, listas y búsquedas.

En este ejercicio se han seguido dos principios SOLID. La clase Box cumple el Single responsibility principle, porque solo gestiona los enseres que se trasladan durante la mudanza. También el de Liskov substitution principle, porque la interfaz genérica Enser permite que diferentes tipos de enseres sean tratados en la clase BoxManager.

### Ejercicio 2 - Facturas en diferentes formatos

Para este segundo ejercicio, se nos pide crear un sistema de información que permita gestionar facturación básica. Se deberá poder generar facturas en formato PDF o HTML.

Para ello, se han diseñado una interfaz y 3 clases. La interfaz contiene el formato en el que tienen que estar las facturas, contiene el método para generar las facturas que después veremos cómo lo implementan las otras clases. La primera clase es la clase Bill, que tiene un constructor y los métodos para añadir y obtener un item de la factura. Después está las clases concretas de los tipos de factura: PDFBill y HTMLBill. La primera implementa a Format y define la función generarFactura de Format, especificando el formato de una factura PDF. Mientras que la segunda es igual, pero cambia la lógica para que las facturas sean en HTML.

Se cumple lo que se expone en el guión. Si quisiéramos añadir un nuevo formato, solo se tendría que crear una clase con ese formato y definir la función generarFactura de Format, sin tocar el resto de código ya hecho. Se cumple con el Open-closed principle, puesto que está abierto a la extensión pero cerrado a la modificación.

### Ejercicio 3 - Gestor de ficheros

El código que se nos da en el guión no cumple con el Single responsibility principle, porque la clase FileManager se encarga de lectura y escritura, por lo que tiene más de una "responsabilidad". Para que sí se cumpla este principio lo que se hará será dividir FileManager en dos clases: FileReader y FileWriter, cada una con una sola responsabilidad.
