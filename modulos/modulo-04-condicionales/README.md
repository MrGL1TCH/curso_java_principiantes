# Módulo 04 – Condicionales en Java

## Objetivo del módulo

Aprender a tomar decisiones en el código utilizando estructuras condicionales como `if`, `else if` y `else`. Esto permite ejecutar diferentes bloques de código dependiendo de si se cumple o no una condición.

---

## ¿Qué es una condicional?

Una condicional evalúa si una expresión es verdadera o falsa. Dependiendo del resultado, se puede ejecutar un bloque de código u otro.  
Por ejemplo:   
- Si estás leyendo esto entonces: Vas a aprender condicionales.
- Si no, entonces: Vas a hacer otra cosa.

---

## Estructura básica de `if`, `else if` y `else`

```java
if (condición) {
    // Código que se ejecuta si la condición es verdadera
} else if (otraCondición) {
    // Código si no se cumplió la anterior, pero sí esta
} else {
    // Código si ninguna de las condiciones anteriores se cumplió
}
```

### ¿Cómo funciona?

- `if` evalúa la **condición**, esta se encierra en paréntesis `(condición)`.
- `else if` permite evaluar otra condición **si la anterior no fue verdadera**.
- `else` se ejecuta **solo si ninguna condición anterior fue verdadera**.

> Presta atención a las llaves "{}" ya que indicarán qué bloque de código se va ejecutar con if, else if y else.

Las condicionales también son útiles para validar datos. Por ejemplo, si un valor introducido por el usuario no es válido, podemos mostrar un mensaje de advertencia usando `else`. Esto es común cuando pedimos información como edad, nombre, opciones, etc. Más adelante, cuando usemos `Scanner` para leer entradas del usuario, esta lógica será muy útil para aceptar únicamente información válida.

### Ejemplo:

```java
int edad = 17;

if (edad >= 18) {                               // Si edad es mayor o igual a 18 entonces:
    System.out.println("Eres mayor de edad.");      // Imprime "Eres mayor de edad".
} else if (edad >= 13) {                        // No se cumplió lo anterior, ahora si edad es mayor a 13 entonces:
    System.out.println("Eres adolescente.");        // Imprime "Eres adolescente"
} else {                                        // No se cumplió ninguna condición entonces:
    System.out.println("Eres niño o niña.");        // Eres niño o niña porque no se cumplieron las condiciones anteriores
}
```

El código se ejecuta de arriba hacia abajo. Evalúa primero el `if`; si la condición no es verdadera, pasa al siguiente `else if`, y así sucesivamente hasta que se cumpla alguna condición.
Si ninguna condición se cumple, se ejecutará el bloque de código dentro de `else`.

---

## Comparando texto (`String`).

A veces como condición necesitamos saber si un texto es igual a otro, en Java, los `String` se consideran **objetos** (más adelante aprenderás qué es un objeto). Por ahora, basta con saber que al usar `==`, Java no compara el texto, sino si las **referencias** son iguales, es decir, compara si **ambas variables apuntan al mismo lugar en la memoria**.  

Por esta razón usaremos un **método** llamado `.equals()` para comparar `Strings`, más adelante profundizaremos sobre qué es un método.

### `.equals()`: 

Para usarlo necesitamos 3 partes importantes, una `variable`, el `método` y el `argumento`. 

#### Forma general:

```java
variable.equals(argumento);
```

- `variable`: es el objeto sobre el que se llama el método `.equals()`.
- `argumento`: es el valor (u otra variable) con el que se va a comparar.

Con el siguiente ejemplo se entenderá mejor:

```java
String nombre1 = "Juan";
String nombre2 = "Juan";

System.out.println(nombre1.equals(nombre2));  // Compara si la variable "nombre1" es igual al argumento, el cual es otra variable (nombre2).
                                              // Retornará "true" ya que son iguales.
```

> Recuerda, los `String` son un tipo especial de clase en Java. Cuando usas `==`, estás comparando **referencias** (la dirección de memoria). Cuando usas `.equals()`, estás comparando el **contenido del texto**.

### Usar `.equalsIgnoreCase()` para ignorar mayúsculas

Si además quieres comparar **ignorando mayúsculas o minúsculas**, puedes usar `.equalsIgnoreCase()`:

```java
String color1 = "Azul";
String color2 = "azul";

System.out.println(color1.equalsIgnoreCase(color2)); // true
```

> Veremos más sobre objetos, métodos y estructuras como estas en los módulos dedicados a la programación orientada a objetos (POO).

---

## Ejemplos

### Ejemplo 1: Comparar Strings

```java
String respuesta = "SI";

if (respuesta.equalsIgnoreCase("si")) {
    System.out.println("Aceptaste los términos.");
} else {
    System.out.println("No aceptaste los términos.");
}
```

### Ejemplo 2: Validar acceso

```java
int edad = 20;

if (edad >= 18) {
    System.out.println("Puedes ingresar a la aplicación.");
} else {
    System.out.println("Acceso denegado. Debes ser mayor de edad.");
}
```
---

## Condicionales anidadas

También puedes colocar una condicional dentro de otra. Esto se conoce como **anidación**, y es útil cuando se deben verificar múltiples condiciones jerárquicamente.

### Ejemplo:

```java
int edad = 20;
boolean tieneIdentificacion = true;

if (edad >= 18) {                                                           // Si es mayor de edad entonces:
    if (tieneIdentificacion) {                                                  // Si tiene identificación, entonces:
        System.out.println("Acceso permitido.");                                    // Tiene acceso permitido
    } else {                                                                    // No tiene identificación, entonces:
        System.out.println("Acceso denegado. Necesitas una identificación.");       // Acceso denegado
    }
}
```

Nota la importancia de la separación del texto de forma organizada con espacios blancos, se le llama **indentación**, el cual sirve para:  
- Para leer y entender el código más fácilmente.  
- Para distinguir **bloques** de código que pertenecen a estructuras como `if`, `else`, `for`, `while`, `métodos`, etc.  
- Aunque en Java no es obligatoria (el programa compila sin ella), es una buena práctica muy importante.

---

## Usar operadores lógicos en condicionales

Puedes usar operadores como `&&`, `||` y `!` para evaluar múltiples condiciones:

```java
int edad = 22;
boolean estudiante = true;

if (edad >= 18 && estudiante) {                            // Si edad es mayor o igual a 18 "Y" es estudiante entonces:
    System.out.println("Es mayor de edad y estudiante.");
}

if (edad < 18 || estudiante) {                             // Si edad es menor a 18 "O" es estudiante entonces:
    System.out.println("Es menor de edad o estudiante.");
}

if (!estudiante) {                                         // Si estudiante es un valor false entonces:
    System.out.println("No es estudiante.");
}
```
> Nota: Si no existe un bloque "else" se interpretará que lo que se haga después del fin del bloque "if" será lo que pasa si la condición no se cumple, como en el ejemplo, es útil cuando quieres verificar una condición, pero si no se cumple no requieres que se haga una acción específica.
---

## Ejercicios

### Ejercicio1Modulo04.java – Comparar palabras

Crea dos variables `String` con palabras diferentes. Compara si son iguales con `.equals()` y muestra un mensaje.

**Entrada ejemplo:**
```
texto1 = "Esto es una String"  
texto2 = "Esto es una String"
```
**Salida esperada:**
```
El texto es igual

```

<details>
  <summary>Ver solución</summary>
    <pre><code>public class Ejercicio1Modulo04 {
    public static void main(String[] args) {
        String texto1 = "Esto es una String";
        String texto2 = "Esto es una String";

        if (texto1.equals(texto2)) {                        // Si el texto1 es diferente al texto2 entonces:
            System.out.println("El texto es igual");
        } else {                                            // Si no, entonces:
            System.out.println("El texto es diferente");
        }
    }
}
</code></pre>

</details>

### Ejercicio2Modulo04.java – Validar edades

Crea una variable edad. Usa `if` `else if` `else` para imprimir si es mayor o menor de edad.
Además validar que la edad no sea un valor imposible, por ejemplo -100 años o 999 años.

> Puedes utilizar AND (&&) para colocar rangos en condiciones.

**Entrada ejemplo:**
```
edad = 28
```
**Salida esperada:**
```
Eres mayor de edad.

```

<details>
  <summary>Ver solución</summary>
<pre><code>public class Ejercicio2Modulo04 {
    public static void main(String[] args) {
        int edad = 18;

        if (edad >= 18 && edad <= 140) {                    // Si la edad es mayor o igual a 18 y es menor o igual a 140 entonces:
            System.out.println("Eres mayor de edad.");
        } else if (edad >= 0 && edad <= 17) {               // Si la edad es mayor o igual a 0 y es menor o igual a 17 entonces:
            System.out.println("Eres menor de edad.");
        } else {                                            // Si no entra en los casos anteriores entonces:
            System.out.println("Error. Edad imposible");
        }
    }
}
</code></pre>

</details>

### Ejercicio3Modulo04.java – If anidado y rangos

Declara una variable int llamada calificacion.
Usa condicionales para imprimir el resultado según el valor de la calificación:

- Si la calificación es igual a 100, imprime: "Excelente".

- Si es mayor o igual a 60 pero menor o igual a 99, imprime: "Aprobado".

- Si es menor o igual a 59, imprime: "Reprobado".

- Si la calificación no está en el rango 0 a 100, imprime: "Calificación inválida".

**Entrada ejemplo:**
```
calificación = 77
```
**Salida esperada:**
```
Aprobado

```

<details>
  <summary>Ver solución</summary>
    <pre><code>public class Ejercicio3Modulo04 {
    public static void main(String[] args) {
        int calificacion = 77;

        if (calificacion == 100) {                              // Si calificación es igual a 100 entonces:
            System.out.println("Excelente");
        } else if (calificacion >= 55 && calificacion <= 99){   // Si calificación es mayor o igual a 55 y menor o igual a 99 entonces:
            System.out.println("Aprobado");
        } else if (calificacion >= 0 && calificacion <= 54) {   // Si calificación es mayor o igual a 0 y menor o igual a 54 entonces:
            System.out.println("Reprobado");
        } else {                                                // Si no cumple las condiciones anteriores entonces:
            System.out.println("Calificación inválida");
        }
    }
}
</code></pre>

</details>

### Ejercicio4Modulo04.java – If, rangos y condición doble.

Declara una variable que represente una hora del día en formato de 24 horas (por ejemplo, `int hora = 20`). Usa condicionales para imprimir:

- "Buenos días" si la hora está entre 4 y 11.
- "Buenas tardes" si está entre 12 y 18.
- "Buenas noches" si está entre 19 y 3.
- "Hora no válida" en otro caso.

**Entrada ejemplo:**  
```
hora = 2  
```
**Salida esperada:**  
```
Buenas noches

```

> Pista: Para verificar el caso de "Buenas noches" necesitarás usar AND (&&) y OR (||) en la misma condición.

<details>
  <summary>Ver solución</summary>
    <pre><code>public class Ejercicio4Modulo04 {
    public static void main(String[] args) {
        int hora = 23;

        if (hora >= 4 && hora <= 11) {                                          // Si la hora está entre 4 y 11.
            System.out.println("Buenos días.");
        } else if (hora >= 12 && hora <= 18){                                   // Si está entre 12 y 18.
            System.out.println("Buenas tardes");   
        } else if ((hora >= 19 && hora <= 23) || (hora >= 0 && hora <= 3)){     // Si está entre 19 y 3.
            System.out.println("Buenas noches");
        } else {                                                                // Otros casos
            System.out.println("Hora no válida");
        }
    }
}
</code></pre>

</details>

### Ejercicio5Modulo04 - Acceso a cine con if anidado

Un cine muestra una película clasificada como B15 (mayores de 15 años).   
Además, hay un descuento si el espectador es estudiante.  
Necesitarás una variable para la edad y otra para indicar si el usuario es estudiante.
Evalúa con condicionales anidadas lo siguiente:

- Si la edad es mayor o igual a 15 pasa a la siguiente fase:

    - Si es estudiante → imprimir "Puedes ver la película y tienes descuento por estudiante."

    - Si no lo es → imprimir "Puedes ver la película. Pero no tienes descuento."

- Si es menor de 15 → imprimir "No puedes ver esta película. Clasificación B15."

**Entrada ejemplo:**
```
edad = 20  
estudiante = false
```
**Salida esperada:**
```
Puedes ver la película. Pero no tienes descuento de estudiante.

```

<details>
  <summary>Ver solución</summary>
    <pre><code>public class Ejercicio5Modulo04 {
    public static void main(String[] args) {
        int edad = 20;
        boolean esEstudiante = false;

        if (edad >= 15){                                // Si edad es mayor o igual a 15 pasa al siguiente bloque
            if (esEstudiante) {                             // Si es estudiante entonces:
                System.out.println("Puedes ver la película y tienes descuento por estudiante.");
            } else {                                        // Si no, entonces:
                System.out.println("Puedes ver la película. Pero no tienes descuento de estudiante.");
            }
        } else {                                        // Si no, entonces:
            System.out.println("No puedes ver esta película. Clasificación B15");
        }
    }
}
</code></pre>

</details>

---

> Intenta resolver los ejercicios antes de ver las soluciones. Si lo necesitas, puedes dar click en "Ver solución".

## Gracias por continuar

- Cada vez se vuelve más complejo, pero eso significa que cada vez tenemos mejor capacidad de pensar soluciones a diferentes problemas.
- Lo estás haciendo muy bien, gracias por seguir con el curso, mucho éxito.

### Autor

[![GitHub](https://img.shields.io/badge/GitHub-MrGL1TCH-181717?logo=github&style=flat-square)](https://github.com/MrGL1TCH)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-angel--rm--dev-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/angel-rm-dev/)