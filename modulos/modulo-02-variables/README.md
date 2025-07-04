# Módulo 02 – Variables y Tipos de Datos

## Objetivo del módulo

Aprender qué son las variables en Java, cómo declararlas, asignarles valores, usarlas en la consola, y conocer los principales tipos de datos primitivos.

---

## ¿Qué es una variable?

Una **variable** es un espacio en memoria donde se guarda un dato temporalmente.  
En Java, necesitas decirle al programa qué tipo de dato va a guardar antes de usarla.

---

## ¿Cómo se declara una variable?

El primer parametro será su **tipo**, `int` `double` `String`, pronto explicaremos más sobre ello.  
Seguido de este colocaremos el **nombre** que le daremos a la variable.  
Por ultimo su **valor**, este debe coincidir con el **tipo** de variable declarado.

```java
tipo nombre_de_variable = valor;
```

Ejemplo:

```java
int edad = 25;
```

En este ejemplo usamos `int` que permite guardar números enteros.   
Colocamos un **nombre** descriptivo para la *variable* que será **edad**.  
Y por último le damos el **valor** del número entero que será guardado, en este caso 25.

---

## ¿Cómo usar una variable?

Una vez que declaras una variable, puedes **utilizarla escribiendo su nombre directamente**.

```java
String nombre = "tu_nombre";
System.out.println(nombre); // Esto mostrará: tu_nombre
```

También puedes cambiar su valor utilizando **"="**:

```java
int edad = 20;
edad = 21;
System.out.println(edad); // Muestra: 21
```

Existen más formas de cambiar los valores de las variables con **operadores**, pero esto lo veremos a más profundidad en el módulo 03.

---

### ¿Qué es una constante?

Una **constante** es una variable cuyo valor no puede cambiar después de haber sido asignado.  
En Java, se declara usando la palabra clave `final`.

---

### Sintaxis de una constante:

```java
final tipo NOMBRE_CONSTANTE = valor;
```

```java
final int AÑO_ACTUAL = 2025;
```

Por convención, el nombre de una constante se escribe en MAYÚSCULAS y si tiene varias palabras, se separan con guiones bajos (_).  

Cuando tienes valores fijos que no deben cambiar nunca, como PI, el número de días de la semana, un límite máximo, etc.  

Ayuda a que el código sea más legible, fácil de mantener, y menos propenso a errores.

---

## Tipos de datos primitivos y casos de uso

Cada tipo de variable tiene distintos usos, cómo se explica en la siguiente tabla:

| Tipo      | Descripción                         | Ejemplo             | Caso de uso                   |
|-----------|-------------------------------------|---------------------|-------------------------------|
| `int`     | Número entero                       | `int edad = 21;`     | Contar, edades, cantidades    |
| `double`  | Número con decimales                | `double peso = 60.5;`| Altura, peso, precios         |
| `char`    | Un solo carácter                    | `char letra = 'A';`  | Iniciales, letras sueltas     |
| `boolean` | Verdadero o falso                   | `boolean activo = true;` | Estados: Encendido / Apagado      |
| `String`  | Texto completo                      | `String nombre = "tu_nombre";` | Nombres, mensajes |

### Cómo se escriben los valores correctamente

Al declarar una variable en Java, debes escribir el **valor de manera adecuada** según su tipo. Aquí tienes algunos ejemplos con las reglas más comunes:

| Tipo      | Ejemplo correcto         | ¿Por qué?                                               |
|-----------|--------------------------|----------------------------------------------------------|
| `String`  | `"tu_nombre"`            | Los textos siempre deben ir entre **comillas dobles** (`" "`) |
| `int`     | `25`                     | Solo se escriben los números, **sin comillas**               |
| `double`  | `1.82`                   | Usa punto (`.`) para decimales, **no comas**, y sin comillas |
| `char`    | `'A'`                    | Escribes un solo carácter entre **comillas simples** (`' '`) |
| `boolean` | `true` o `false`         | Se escribe en **minúsculas**, sin comillas                  |

---

## ¿Qué pasa si usas un dato no válido?

Si asignas un tipo de dato incorrecto, Java marca un error:

```java
int edad = "tu_edad"; // ❌ Error: no se puede asignar un texto a un int
```

Es importante respetar el tipo de dato al momento de declarar y asignar valores.

---

### Ejemplos correctos:

```java
String ciudad = "tu_ciudad";   // Correcto: comillas dobles
int edad = 20;                 // Correcto: número sin comillas
double peso = 60.5;            // Correcto: decimal con punto
char inicial = 'J';           // Correcto: comillas simples
boolean activo = true;        // Correcto: sin comillas
```

### Ejemplos incorrectos:

```java
String nombre = tu_nombre;     // Falta comillas dobles
int edad = "20";               // No uses comillas en números
double altura = 1,75;          // Usa punto, no coma
char letra = "A";              // Usa comillas simples, no dobles
boolean esEstudiante = "true"; // No uses comillas en booleanos
```

---

## Cómo imprimir variables con `System.out.print`

Puedes mostrar variables en consola combinándolas con texto usando el operador `+`.

```java
String nombre = "tu_nombre";
int edad = tu_edad;
System.out.println("Nombre: " + nombre + ", Edad: " + edad);
```

Si usas `+` con dos números: los suma.  
Si mezclas texto y número: convierte todo a texto.

---

## Ejemplo completo (ImpresionVariables.java)

```java
public class ImpresionVariables {
    public static void main(String[] args) {
        String nombre = "tu_nombre";                       // Variable tipo texto
        int edad = tu_edad;                                // Variable tipo entero
        String ciudad = "tu_ciudad";                       // Variable tipo texto

        // Concatenamos todo en una línea utilizando el operador "+"
        System.out.println("Hola, me llamo " + nombre + ", tengo " + edad + " años y vivo en " + ciudad + "."); 
    }
}
```

---

## Ejercicios para practicar

### Ejercicio1Modulo02.java – Imprimir variable

Crea una variable de tipo `String` llamada **saludo** que contenga alguna forma de saludar, puedes guiarte por el ejemplo.
Después imprimela.

**Salida esperada:**
```
Hola

```

<details>
  <summary>Ver solución</summary>
    <pre><code>public class Ejercicio1Modulo02 {
    public static void main(String[] args) {
        String saludo = "Hola";             // Declaramos la variable
            System.out.println(saludo);     // Imprimimos la variable
    }
}
</code></pre>

</details>

---

### Ejercicio2Modulo02.java – Actualizar datos

Crea una variable con un número n e imprimelo, después actualiza su valor a un número diferente usando el operador "=" e imprime el nuevo valor.

**Salida esperada:**
```
El número es: 5
El nuevo valor del número es: 7

```

<details>
  <summary>Ver solución</summary>

  <pre><code>public class Ejercicio2Modulo02 {
    public static void main(String[] args) {
        int numero = 5;                                                 // Declarar variable "numero" y asignarle un valor

        System.out.println("El número es: " + numero);                  // Imprimir la variable

        numero = 7;                                                     // Actualizar el valor de "numero"

        System.out.println("El nuevo valor del número es: " + numero);  // Imprimir la variable
    }
}
</code></pre>

</details>

---

### Ejercicio3Modulo02.java – Concatenar datos

Crea una variable `nombre`, `edad`, `estatura` y `estudiante`, asigna un tipo de dato adecuado para su uso. Puedes guiarte por el ejemplo de salida.  
Imprime las varibales en lineas separadas de manera que el formato de salida sea el siguiente:

**Salida esperada:**
```
Nombre: tu_nombre
Edad: 27
Altura: 1.82m
¿Estudiante?: true

```

<details>
  <summary>Ver solución</summary>

  <pre><code>public class Ejercicio3Modulo02 {
    public static void main(String[] args) {
        String nombre = "tu_nombre";        // Variable tipo texto
        int edad = 27;                 // Variable tipo entero
        double altura = 1.82;               // Variable decimal
        boolean estudiante = true;          // Variable tipo booleano

        // Imprimimos cada valor
        System.out.println("Nombre: " + nombre);
        System.out.println("Edad: " + edad);
        System.out.println("Altura: " + altura + "m");
        System.out.println("¿Estudiante?: " + estudiante);
    }
}
</code></pre>

</details>

## Gracias por continuar

- Gracias por seguir con el curso, el siguiente módulo comenzamos con ejercicios más complejos, pero de nivel principiante para desarrollar la lógica.  
- Mucho exito en tu camino.

### Autor

[![GitHub](https://img.shields.io/badge/GitHub-MrGL1TCH-181717?logo=github&style=flat-square)](https://github.com/MrGL1TCH)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-angel--rm--dev-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/angel-rm-dev/)
