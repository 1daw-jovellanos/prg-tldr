---
title: 'Empezando con Java'
taxonomy:
    category: docs
visible: true
---

[TOC]
## Clases
Una **clase** es un componente organizativo básico de la aplicación que contiene fundamentalmente _datos_ y _algoritmos_.
Aunque el código de las clases puede utilizarse directamente, habitualmente son la base para construcción de los **objetos**

Las clases en java se escriben en [**UpperCamelCase**](https://es.wikipedia.org/wiki/CamelCase). Nuestras aplicaciones van a utilizar Clases y generar objetos que proceden básicamente de tres fuentes:
1. Las clases que los programadores escribimos directamente.
2. Las clases que ya vienen predefinidas en el JDK y que forman el API de Java. [[Ver "Qué es y para qué sirve el API de Java"]](https://www.aprenderaprogramar.com/index.php?option=com_content&view=article&id=551:que-es-y-para-que-sirve-el-api-de-java-librerias-de-biblioteca-estandar-jdbc-javafx-rmi-cu00645b&catid=68&Itemid=188)
3. Clases de terceros, que incluímos en nuestro proyecto. (Compradas o utilizadas bajo su correspondiente licencia)

* Cada clase se escribe en un fichero que debe coincidir exactamente con el nombre de la clase.
* El contenido de la clase va entre llaves, e **indentado** [[Ver: Identación. Usamos K&R variante Java]](https://en.wikipedia.org/wiki/Indentation_style)
* Para mantener orden y limpieza, las clases suelen agruparse en **paquetes**. Un paquete es una carpeta 
  que agrupa clases. Si se hace uso de paquetes, la primera línea debe ser la directiva _package_ seguida del nombre
  del paquete, que estará escrito solo con letras minúsculas. El nombre del paquete también puede contener números.
  Ej: `package nombrepaqueteejemplo;`

``` java
public class Ejemplo {
  // Aquí el contenido de la clase
}
```

## el método principal
El punto de entrada a una aplicación de java es un método con la siguiente signatura `public static void main(String[] args)`

Ejemplo
```java
public class Ejemplo {
   public static void main(String[] args) {
       // contenido del método
   }
}
```

## Salida básica.
* **System.out.print(_expresión_);** emite el resultado de evaluar la expresión por la salida estándar. Ej: `System.out.print(3.14);`, `System.out.print("Hola Mundo");`. 
* **System.out.print(_expresión_);** emite el resultado de evaluar la expresión por la salida estándar seguida 
  de un cambio de línea. Ej: `System.out.println(3.14);`, `System.out.println("Hola Mundo");`. Si no se indica nada entre
  paréntesis se imprime solo un cambio de línea. `System.out.println();`
* **System.out.format(_cadena_de_formato_, _...dato_);** emite la cadena de formato, que puede tener en su interior    
  modificadores. Para cada modificador que requiera un dato hay que proporcionar el dato tras la cadena de formato,
  cuidando de que el tipo de dato coincida con el indicado en el modificador.
  > `%d` número entero  
  > `%f` número con decimales  
  > `%s` cadena  
  > `%n` cambio de línea (no requiere dato)  
  > `%%` el símbolo del tanto por ciento (no requiere dato)  

## Literales.
Un valor literal es aquel que se indica de manera explícita en el código. Vamos a empezar a indicar como se escriben los valores literales numéricos y las cadenas de texto.
* Numéros enteros: tal cual   `1232` `10000000` `999999993393`
* Números con decimales: Se utiliza el punto como separador decimal `3.1416`. Si la parte entera es 0 puede omitise. Ej: `0.23` y `.23` son equivalentes. Los ceros a la derecha en la parte entera no son significativos. Ej. `0.2` y `0.20` representan al mismo valor.
* Cadenas: Se pone el texto entre comillas dobles. Ej: `"Esto es una cadena"`, `"En java, las cadenas pueden contener cualquier carácter Unicode, como emojis 😉, pictogramas 🍵 o caracteres de los pricipales idiomas 이 언어는 훌륭합니다."`

## variables
Son un espacio de memoria con nombre en el que poder guardar datos. Vamos a empezar utilizando sólo números y cadenas.
### declaración
Se declaran escribiendo el tipo de la variable seguido de un identificador en **lowerCamelCase**.
> **int** entero sin decimales. Ej: `int numeroDeVehiculos;`  
> **double** numero con decimales de doble precisión. Ej: `double alturaDelUsuario;`    
> **String** cadena de texto. Ej: `String localidad;`   

### asignación 
Para asignar valor a una variable se utiliza el operador `=`. A la izquierda del operador debe haber una variable, y a la derecha una expresión del mismo tipo que la variable.
Ej: `numeroDeVehiculos = 28;`, `alturaDelUsuario = 1.50 + 0.3;`, `localidad = "Fuenlabrada";`

### declaración y asignación en usa sola línea.
Se puede declarar y asignar el valor inicial de una variable en una sola línea: `double numeroAsignaturas = 22;`. <mark>Sólo se recomienda para valores iniciales evidentes, o para variables temporales.</mark>

## Operadores
En java, algunas operaciones frecuentes se representan con un **operador**
> `+` Entre numeros suma `System.out.print(3.6 + 12);` `4 + altura`. Si uno de los operandos es cadena, entonces concatena `System.out.print("Hola " + "Mundo");`   
> `-` Entre numeros resta `System.out.print(3.6 - 12);` `4 - altura`. Delante de un número o una variable la cambia de signo `-8.4`, `-a`  
> `*` Multiplicación `edad * 2`.  
> `/` Cociente. `altura / 2` <mark>Si ambos operandos son enteros, la división es entera</mark>. Si cualquiera de los operandos tiene decimales, entoces la división es con decimales.  
> `%` Resto de la división, también llamado _módulo_. `altura % 10` se lee _altura módulo 10_.  


## Invocación de métodos
Los métodos representan a algoritmos, a los que se les pone un identificador, en **lowerCamelCase** seguido de unos paréntesis en los que van los parámetros. Los métodos pertenecen a una clase u objeto. La ejecución de un método es una **invocación** del método: los métodos se **invocan**.

Por ejemplo, **Math.sqrt(...)** es un método que viene con el lenguaje Java para calcular la raíz cuadrada de un número. Este metodo se llama sqrt(...) y está dentro de la clase Math. Cuando necesitamos calcular una raíz cuadrada invocamos al método por su nombre, pasándole como parámetro el valor del que queremos calcular la raíz cuadrada. `System.out.format("La raíz de 25 es %f%n", Math.sqrt(25));`.


