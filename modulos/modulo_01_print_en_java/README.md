# 🖨️ Módulo 01 – print en Java

## 🎯 Objetivo del módulo

Aprender cómo imprimir texto en la consola usando `System.out.print` y `System.out.println`,  
y entender la estructura básica de un programa Java desde cero.

---

## 🧠 Cosas importantes antes de comenzar

### 🔗 Practica durante la marcha

- Practica los ejemplos mientras estudias.
- Escribe o copia y pega en tu IDE favorito el codigo(como IntelliJ, Eclipse o VS Code), o…
- Ejecuta en línea aquí: 👉 [https://replit.com/languages/java10](https://replit.com/languages/java10)

### 🔑 ¿Qué es el método `main`?

Todo programa Java **debe tener un método llamado `main`**.  
Es como el punto de entrada o inicio. Sin él, el programa no sabrá por dónde empezar.

```java
public static void main(String[] args) {
    // Código que se ejecuta al iniciar el programa
}
```

📖 Explicación rápida:

- `public`: visible desde cualquier parte del programa.  
- `static`: no necesita crear un objeto para usarse.  
- `void`: no regresa ningún valor.  
- `main`: nombre obligatorio del método principal.  
- `String[] args`: sirve para pasar datos desde la terminal.

No te preocupes si no terminas de entender estos conceptos, en la práctica los iremos comprendiendo mejor.


## 📂 Nombre del archivo y nombre de la clase

En Java, **el nombre del archivo `.java` debe coincidir exactamente con el nombre de la clase pública** que contiene.  
Es decir:

```java
public class Hola {
    public static void main(String[] args) {
        System.out.println("¡Hola!");
    }
}
```

➡️ Este código debe estar guardado en un archivo llamado **`Hola.java`**, no `hola.java`, `Main.java` ni `Programa.java`.

> ⚠️ Si el nombre del archivo y el de la clase pública no coinciden, el código no compilará.

Todo programa en Java necesita:

- Una **clase pública** cuyo nombre coincida con el archivo `.java`
- Un **método `main`** que será el punto de inicio
- Cada línea de código termina con `;` (punto y coma)

---

---

## 💡 ¿Qué se puede hacer con `System.out.print/println`?

- Mostrar texto en consola
- Imprimir variables y resultados
- Controlar el formato del texto (líneas, tabulaciones, etc.)

## 🚫 ¿Qué **no** se puede hacer?

- No se puede leer datos del usuario (para eso usamos `Scanner`, lo veremos en otro módulo)
- No se puede ejecutar lógica condicional avanzada (como `if`, `for`, `switch`, etc.)
- No imprime gráficos, solo texto plano

---

## 🧱 Estructura básica de un programa Java

```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("¡Hola, mundo!");
    }
}
```

### 🧠 Explicación línea por línea:

| Línea                               | ¿Qué hace? |
|-------------------------------------|------------|
| `public class HolaMundo`           | Define la clase con el mismo nombre que el archivo (HolaMundo.java) |
| `public static void main(String[] args)` | Método principal, punto de entrada del programa |
| `System.out.println("Texto");`     | Imprime texto en consola y salta a la siguiente línea |

---

## 🔄 `println` vs `print`

| Método             | ¿Qué hace?                              |
|--------------------|------------------------------------------|
| `System.out.println(...)` | Imprime y **agrega salto de línea** al final |
| `System.out.print(...)`   | Imprime **sin salto de línea**              |

### 📌 Ejemplo:

```java
System.out.print("Hola ");
System.out.print("Mundo");
System.out.println("!");
```

**Salida:**
```
Hola Mundo!
```

---

### 🧙‍♂️ Secuencias especiales con `\` en Java

En Java, cuando escribes `\` dentro de un texto (`String`), **no se imprime tal cual**.  
La barra invertida (`\`) se usa para indicar **una secuencia especial**, que tiene un **significado oculto** para el lenguaje.

Estas secuencias comienzan con `\` y una letra, por ejemplo `\n`, `\t`, `\"`, etc.

---

#### 🎯 ¿Para qué sirven?

Sirven para **dar formato** al texto que se imprime en consola.  
Por ejemplo: saltar de línea, tabular, escribir comillas o una barra invertida.

---

### 📋 Lista de secuencias especiales comunes

| Secuencia | ¿Qué hace?                        | Ejemplo de código                              | Salida en consola               |
|-----------|------------------------------------|------------------------------------------------|----------------------------------|
| `\n`      | Salto de línea                     | `System.out.print("Hola\nMundo");`             | Hola<br>Mundo                    |
| `\t`      | Tabulación (espacio grande)        | `System.out.print("Nombre:\ttu_nombre");`      | Nombre: tu_nombre                  |
| `\"`      | Comillas dobles                    | `System.out.print("Dijo: \"Hola\"");`          | Dijo: "Hola"                     |
| `\\`      | Imprime una barra invertida (`\`)  | `System.out.print("Ruta: C:\\Java");`          | Ruta: C:\Java                    |

---

### ⛔ ¿Por qué `\\`?

Si escribes solo `\`, Java intentará encontrar una secuencia especial.  
Y si **no encuentra una válida**, lanza un error.

#### ❌ Esto da error:
```java
System.out.println("Carpeta: C:\Java"); // Error
```

#### ✅ Esto funciona:
```java
System.out.println("Carpeta: C:\\Java"); // Bien
```

---

## 👨‍🏫 Buenas prácticas desde el inicio

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

## 🧪 Ejemplo completo

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

## 🏋️ Ejercicios 

1. **Ejercicio1.java**  
   Imprime tu nombre, edad y ciudad en 3 líneas diferentes. Intenta hacerlo usando "print" y "\n".

   ```
   Nombre: tu_nombre
   Edad: tu_edad
   Ciudad: tu_ciudad
   ```

2. **Ejercicio2.java**  
   Usa `println` para imprimir lo siguiente:
   ```
     *
    ***
   *****
   ```

3. **Ejercicio3.java**  
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

> ✅ Crea un archivo `.java` e ntenta resolverlos, si te atoras en alguna parte puedes ver las soluciones en los archivos adjuntos `EjercicioN.java`

---

## ♥️ Gracias por comenzar

- Gracias por comenzar esté curso, espero te pueda servir para prácticar las bases de Java, te deseó mucho éxito.
- Practica mucho, intenta resolver los ejercicios de diferentes formas, descubre, analiza y diviertete aprendiendo.

### 💻 Autor

[![GitHub](https://img.shields.io/badge/GitHub-MrGL1TCH-181717?logo=github&style=flat-square)](https://github.com/MrGL1TCH)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-angel--rm--dev-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/angel-rm-dev/)
