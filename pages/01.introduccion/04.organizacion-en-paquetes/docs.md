---
title: 'Organización en paquetes'
taxonomy:
    category:
        - docs
visible: true
---

[TOC]
## Paquetes
La organización del código fuente en Java se hace agrupando los fuentes en carpetas, a lo que en la terminología de java se le llama **paquete**.
Al principio de cada fuente se incluirá el nombre del paquete en el que se incluye con la directiva **package**. Ej: si el fuente de una clase llamada _Marcianito_ se guarda en un paquete llamado _naves_, entonces en el código de _Marcianito.java_ se incluye como primera línea la declaración `package naves;`.  
Los códigos compilados siguen una distribución en paquetes con la misma estructura que las fuentes. Java dispone de un mecanismo para comprimir paquetes en un solo fichero (con extensión **.jar** -java archive-), para distribuir compilados de una manera más compacta.

Si un fuente se mete dentro de una carpeta y ésta dentro de otra en el proyecto, el nombre del paquete pasa a ser el nombre de todas las carpetas separadas por puntos. <mark>Los nombres de los paquetes completamente en minúscula</mark>

Por ejemplo, si en un proyecto creamos una carpeta llamada _naves_ y dentro de esa otra llamada _intestelares_ y dentro de esa creamos la clase HalconMilenario.java, entonces habrá que especificar como primera línea de _HalconMilenario.java_ su paquete de ésta manera: `package naves.interestelares;`.

## importando clases
Cuando un fichero fuente indica el nombre de otra clase, Java asume que está en su mismo paquete. Si no fuera así, hay que decirle al compilador en qué paquetes están las clases que vamos a usar con una o más directivas **import**, que se escriben debajo de package.
> `import naves.interestelares.HalconMilenario;` indica al compilador que vamos a usar la clase HalconMilenario 
> del paquete naves.interestelares.        
> `import naves.interestelares.*;` indica al compilador que vamos a usar _cualquier_ clase del paquete naves.interestelares.  

Las clases del API de java están agrupadas en paquetes que habitualmente empiezan por **java** o **javax**.
Por ejemplo, la clase Scanner está en el paquete java.util, y para usarla hay que poner la directiva `import java.util.Scanner;` o `import java.util.*`.

El paquete **java.lang** contiene clases fundamentales para cualquier aplicación de java (Como **String** o **System**) y no hace falta importarlo.
