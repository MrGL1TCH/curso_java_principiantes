# Módulo 01 – print en Java

## Objetivo del módulo

Aprender cómo imprimir texto en la consola usando `System.out.print` y `System.out.println`,  
y entender la estructura básica de un programa Java desde cero.

---

## Cosas importantes antes de comenzar

### Practica durante la marcha

- Practica los ejemplos mientras estudias.
- Escribe o copia y pega en tu IDE favorito el codigo(como IntelliJ, Eclipse o VS Code)
- Si descargaste todo el curso deberías tener archivos llamados cómo: "EjercicioNModulo01", puedes usarlos de base para practicar.
- También puedes ejecutar en línea aquí: [https://replit.com/languages/java10](https://replit.com/languages/java10)

### ¿Qué es el método `main`?

Todo programa Java **debe tener un método llamado `main`**.  
Es como el punto de entrada o inicio. Sin él, el programa no sabrá por dónde empezar.

```java
public static void main(String[] args) {
    // Código que se ejecuta al iniciar el programa
}
```

Explicación rápida:

- `public`: visible desde cualquier parte del programa.  
- `static`: no necesita crear un objeto para usarse.  
- `void`: no regresa ningún valor.  
- `main`: nombre obligatorio del método principal.  
- `String[] args`: sirve para pasar datos desde la terminal.

No te preocupes si no terminas de entender estos conceptos, en la práctica los iremos comprendiendo mejor.

## Nombre del archivo y nombre de la clase

En Java, **el nombre del archivo `.java` debe coincidir exactamente con el nombre de la clase pública** que contiene.  
Es decir:

```java
public class Hola {
    public static void main(String[] args) {
        System.out.println("¡Hola!");
    }
}
```

Este código debe estar guardado en un archivo llamado **`Hola.java`**, no `hola.java`, `Main.java` ni `Programa.java`.

> ⚠️ Si el nombre del archivo y el de la clase pública no coinciden, el código no compilará.

Todo programa en Java necesita:

- Una **clase pública** cuyo nombre coincida con el archivo `.java`
- Un **método `main`** que será el punto de inicio
- Cada línea de código termina con `;` (punto y coma)

---

## Estructura básica de un programa Java

```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("¡Hola, mundo!");
    }
}
```

### Explicación línea por línea:

| Línea                               | ¿Qué hace? |
|-------------------------------------|------------|
| `public class HolaMundo`           | Define la clase con el mismo nombre que el archivo (HolaMundo.java) |
| `public static void main(String[] args)` | Método principal, punto de entrada del programa |
| `System.out.println("Texto");`     | Imprime texto en consola y salta a la siguiente línea |

Puede sentirse complicado tanta información, no tienes que aprender de memoria todo lo mencionado, está es una base que puedes consultar después conforme vayas aprendiendo más sobre Java, pero sentí que era necesario mencionarlo por si en algún momento te preguntas "¿Por qué usamos public class al inicio de todo?", aquí puedes responder esas preguntas, si no entiendes algo puedes contactarme o investigarlo, el punto de esté curso es aprender todos.

---

# `print` en Java

## ¿Qué es y que puede hacer con `System.out.print/println`?

- Es un comando que permite mostrar/imprimir texto en consola.
- Imprimir variables y resultados
- Controlar el formato del texto (líneas, tabulaciones, etc.)

## ¿Qué **no** se puede hacer?

- No se puede leer datos del usuario (para eso usamos `Scanner`, lo veremos en otro módulo)
- No se puede ejecutar lógica condicional avanzada (como `if`, `for`, `switch`, etc.)
- No imprime gráficos, solo texto plano

---

### Sintaxis de `println` y `print`:

Cuando imprimimos texto o datos en la consola en Java, usamos expresiones como:

```java
System.out.print("Hola mundo");
```
A simple vista puede parecer algo largo, pero cada parte tiene un propósito. Vamos a desglosarlo:
| Parte     | Significado                                                                                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------ |
| `System`  | Es una clase predefinida en Java que forma parte de la biblioteca estándar.                                        |
| `out`     | Es un **objeto** público dentro de la clase `System`. Representa la **salida estándar** (normalmente, la consola). |
| `print()` | Es un **método** que imprime lo que le pases entre paréntesis. No agrega salto de línea.                           |

> Está es una explicación sobre que hace cada parte del código, pero con que aprendas a escribirlo es más que suficiente.

## `println` vs `print`

| Método             | ¿Qué hace?                              |
|--------------------|------------------------------------------|
| `System.out.println(...)` | Imprime y **agrega salto de línea** al final |
| `System.out.print(...)`   | Imprime **sin salto de línea**              |

> Salto de línea, es cómo cuando escribimos en un editor de texto y apretamos la tecla "Enter" da un salto de línea hacía abajo.

Con un ejemplo podrás entenderlo mejor:

```java
System.out.print("Hola ");
System.out.print("Mundo");
System.out.println("!");
System.out.print("Esto se imprimirá en otra línea ya que antes se uso println");
```

**Salida:**
```
Hola Mundo!
Esto se imprimira en otra línea ya que antes se uso println

```

Asegúrate de cerrar siempre el paréntesis () y las comillas " " si estás imprimiendo texto.  
Dentro de "()" escribiras todo lo que vayas a imprimir, también llamado argumento.  
> Un argumento es el valor o expresión que se pasa a un método cuando lo llamas. Es lo que el método necesita para funcionar correctamente.

---

### Secuencias especiales con `\` en Java

En Java, cuando escribes `\` dentro de un texto (`String`), **no se imprime tal cual**.  
La barra invertida (`\`) se usa para indicar **una secuencia especial**, que tiene un **significado oculto** para el lenguaje.

Estas secuencias comienzan con `\` y una letra, por ejemplo `\n`, `\t`, `\"`, etc.

---

#### ¿Para qué sirven?

Sirven para **dar formato** al texto que se imprime en consola.  
Por ejemplo: saltar de línea, tabular, escribir comillas o una barra invertida.

---

### Lista de secuencias especiales comunes

| Secuencia | ¿Qué hace?                        | Ejemplo de código                              | Salida en consola               |
|-----------|------------------------------------|------------------------------------------------|----------------------------------|
| `\n`      | Salto de línea                     | `System.out.print("Hola\nMundo");`             | Hola<br>Mundo                    |
| `\t`      | Tabulación (espacio grande)        | `System.out.print("Nombre:\ttu_nombre");`      | Nombre: tu_nombre                  |
| `\"`      | Comillas dobles                    | `System.out.print("Dijo: \"Hola\"");`          | Dijo: "Hola"                     |
| `\\`      | Imprime una barra invertida (`\`)  | `System.out.print("Ruta: C:\\Java");`          | Ruta: C:\Java                    |

> No es obligatorio memorizarlas todas de inmediato. En cuántos las necesites puedes consultarlas aquí.

---

### ¿Por qué `\\`?

Si escribes solo `\`, Java intentará encontrar una secuencia especial.  
Y si **no encuentra una válida**, lanza un error.

#### Esto da error:
```java
System.out.println("Carpeta: C:\Java"); // Error
```

#### Esto funciona:
```java
System.out.println("Carpeta: C:\\Java"); // Bien
```

---

## Buenas prácticas desde el inicio

- El nombre del archivo `.java` debe coincidir con el nombre de la clase pública.
- Siempre debes tener el método `main` para que Java sepa dónde iniciar.
- Usa nombres descriptivos para clases y archivos.
- Escribe comentarios usando "//" y también "/* */" para documentar o dar explicaciones, ejemplo:

```java
// Esto es un comentario de una línea

/*
    Este es un comentario de varias líneas.
    Se puede utilizar para explicar secciones más grandes de código.
*/
```
   

```java
// Esto imprime un saludo
System.out.println("¡Hola!");
```

---

## Ejemplo completo

```java
public class Hola {
    public static void main(String[] args) {
        System.out.print("Hola ");
        System.out.print("mundo\n");
        System.out.println("¡Bienvenido a Java!");
    }
}
```

**Salida:**
```
Hola mundo
¡Bienvenido a Java!
```

---

## Ejercicios

### Ejercicio1Modulo01.java - Imprimir texto
   Imprime tu nombre, edad y ciudad en 3 líneas diferentes. Intenta hacerlo usando "print" y "\n".

   ```
   Nombre: tu_nombre
   Edad: tu_edad
   Ciudad: tu_ciudad
   ```

<details>
    <summary>Ver solución</summary>

  <pre><code>public class Ejercicio1Modulo01 {
    public static void main(String[] args) {
        System.out.print("Nombre: tu_nombre\n");     // Usamos "\n" para realizar un salto de linea.
        System.out.print("Edad: tu_edad");           // Imprimimos una linea, podríamos usar "\n" para hacer el salto de línea.
        System.out.print("\nCiudad: tu_ciudad");     // Pero también podemos usarlo al inicio de aquí y dará el mismo resultado.
/*
        System.out.println("Nombre: tu_nombre");       Te doy el ejemplo con "println", por defecto va imprimir un salto de línea al final del texto;
        System.out.println("Edad: tu_edad");           Esto nos ahorra el uso de "\n" pero es importante poder manejarlo cómo lo necesites.
        System.out.println("Ciudad: tu_ciudad");       Para probarlo quita el comentario o simplemente copialo y pegalo, después ejecutalo.
        */ 
    }
}
</code></pre>

</details>

### Ejercicio2Modulo01.java Imprimir ASCII y espacios blancos.  
   Usa `println` para imprimir la siguiente forma:
   ```
     *
    ***
   *****
   ```

<details>
    <summary>Ver solución</summary>

  <pre><code>
public class Ejercicio2Modulo01 {
    public static void main(String[] args) {
        System.out.println("  *");      // Al imprimir también toma en cuenta lo espacios dentro de "" 
        System.out.println(" ***");     // Es por eso que al imprimirlo aparecen espacios al inicio de la línea
        System.out.println("*****");
    }
}
</code></pre>

</details>

### Ejercicio3Modulo01.java - Uso de los formatos "\".
   Usa `print` y `\n`, `\t`, `\\` `\*` para imprimir este resultado:

   ```
   Línea 1
   Línea 2
   Línea 3
   Nombre:    tu_nombre                          // Usa la sangría
   Edad:      tu_edad                            // Usa la sangría
   Ruta de archivo: C:\Usuarios\MrGL1TCH\Java    // Es un ejemplo de ruta, no tiene que ser real, necesitaras "\\"
   Me dijo: "Bienvenido a Java"                  // Utiliza \" para imprimir las comillas
   ```


<details>
    <summary>Ver solución</summary>

  <pre><code>public class Ejercicio3Modulo01 {
    public static void main(String[] args) {
        System.out.print("Línea 1\n");              // Aquí se utiliza "print" y además "\n" para darle al final un salto de línea
        System.out.print("Línea 2\nLínea 3\n");     // En este otro caso usamos el salto de línea en medio del texto
        System.out.print("Nombre:\ttu_nombre\n");       // Damos una sangría para denotar más el espacio
        System.out.print("Edad:\ttu_edad\n");            
        System.out.print("Ruta de archivo: C:\\Usuarios\\MrGL1TCH\\Java\n");   // Usamos "\\" para poder imprimir un "\"
        System.out.print("Me dijo: \"Bienvenido a Java\"");      // Con \" colocamos una comilla sin cerrar las comillas principales 
    }
}
</code></pre>

</details>  
  

> Intenta solucionarlos con lo aprendido, si te atoras en alguna parte puedes ver la solución dando click en "Ver solución". Tienes archivos llamados "EjercicioNModulo01" en dónde puedes solucionarlos, también puedes crear tu propio archivo desde 0 para practicar.

---

## Gracias por comenzar

- Gracias por comenzar este curso, espero te pueda servir para prácticar las bases de Java, te deseo mucho éxito.
- Practica mucho, intenta resolver los ejercicios de diferentes formas, descubre, analiza y diviertete aprendiendo.

### Autor

[![GitHub](https://img.shields.io/badge/GitHub-MrGL1TCH-181717?logo=github&style=flat-square)](https://github.com/MrGL1TCH)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-angel--rm--dev-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/angel-rm-dev/)
