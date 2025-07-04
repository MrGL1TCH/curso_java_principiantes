# Módulo 03 – Operadores en Java

## Objetivo del módulo

Comprender cómo utilizar operadores para realizar cálculos, comparar valores, asignar datos y trabajar con condiciones.\
Aprenderás qué operadores existen en Java y cómo su comportamiento puede variar dependiendo del tipo de dato.

---

## ¿Qué es un operador?

Un **operador** es un símbolo que indica una operación entre valores.\
Por ejemplo: `+`, `-`, `*`, `=`, `==`, `!=`, `&&`, etc.

En Java los operadores nos ayudan a:

- Hacer cálculos matemáticos
- Comparar datos
- Asignar valores
- Evaluar condiciones

---

## Tipos de operadores en Java

### 1. Operadores Aritméticos

Los **operadores aritméticos** se utilizan para realizar operaciones matemáticas básicas como suma, resta, multiplicación, división y módulo (residuo).

| Operador | Descripción      | Ejemplo |
| -------- | ---------------- | ------- |
| `+`      | Suma             | `a + b` |
| `-`      | Resta            | `a - b` |
| `*`      | Multiplicación   | `a * b` |
| `/`      | División         | `a / b` |
| `%`      | Módulo (residuo) | `a % b` |

#### Ejemplos:

```java
int a = 10;
int b = 3;
System.out.println("Suma: " + (a + b));       // 13
System.out.println("Resta: " + (a - b));      // 7
System.out.println("Multiplicación: " + (a * b)); // 30
System.out.println("División: " + (a / b));   // 3 (división entera)
System.out.println("Módulo: " + (a % b));      // 1 (residuo)
```

Ponemos énfasis en "División entera" ya que estamos diviendo valores enteros `int` para obtener decimales debemos utilizar datos de tipo `double`.

---

### 2. Operadores de Asignación

Se usan para asignar valores a variables. También existen versiones combinadas con operaciones matemáticas.

| Operador | Significado         | Ejemplo            |
| -------- | ------------------- | ------------------ |
| `=`      | Asignación directa  | `a = 5`            |
| `+=`     | Suma y asigna       | `a += 2` (a = a+2) |
| `-=`     | Resta y asigna      | `a -= 1`           |
| `*=`     | Multiplica y asigna | `a *= 3`           |
| `/=`     | Divide y asigna     | `a /= 4`           |
| `%=`     | Módulo y asigna     | `a %= 2`           |

#### Ejemplos:

```java
int a = 10;
a += 5; // al aplicar += le sumamos 5 al valor actual de "a", es decir, 10 + 5 = 15
a *= 2; // al usar *= multiplicamos 2 al valor actual de "a", es decir, 15 * 2 = 30
System.out.println("Resultado final: " + a); // 30
```

---

### 3. Operadores de Comparación

Estos operadores comparan dos valores y devuelven un resultado booleano (`true` o `false`).

| Operador | Significado       | Ejemplo  |
| -------- | ----------------- | -------- |
| `==`     | Igual a           | `a == b` |
| `!=`     | Diferente de      | `a != b` |
| `>`      | Mayor que         | `a > b`  |
| `<`      | Menor que         | `a < b`  |
| `>=`     | Mayor o igual que | `a >= b` |
| `<=`     | Menor o igual que | `a <= b` |

#### Ejemplos:

```java
int x = 5;
int y = 10;
System.out.println(x == y); // false
System.out.println(x != y); // true
System.out.println(x < y);  // true
System.out.println(x >= 5); // true
```

---

### 4. Operadores Lógicos

Se utilizan principalmente para evaluar múltiples condiciones lógicas.

#### `&&` (AND)
Devuelve `true` si **ambas condiciones** son verdaderas.

```java
true && true    // true

true && false   // false

false && false // false
```

#### `||` (OR)

Devuelve `true` si al menos una condición es verdadera.

```java
true || true // true

true || false   // true

false || false  // false
```

#### `!` (NOT)
Invierte el valor booleano

```java
!true  // false

!false // true
```

#### Ejemplos:

```java
int edad = 20;
boolean estudiante = true;
System.out.println("Es mayor de 18 años Y es estudiante? " + (edad > 18 && estudiante)); // true
System.out.println("Es menor de edad O es estudiante? " + (edad < 18 || estudiante)); // true
System.out.println("NO es estudiante " + (!estudiante));             // false
```

Así como en matematicas, usamos "()" para realizar primero la operación dentro del parentesis, después `concatenamos` el resultado al `String` usando el operador `+`.
También nótese que se pueden realizar operaciones dentro de un `print` o `println`, pero puede llegar a ser algo confuso de leer entre más codigo exista, procura explicarlo comentando el código y/o realizando las operaciones antes.

---

## El operador `+` según el tipo de dato

Java interpreta el operador `+` de forma distinta según los **tipos de datos** involucrados:

- **Si ambos operandos son números** (`int`, `double`): realiza una **suma matemática**.
- **Si al menos uno es una** `String`: realiza una **concatenación de texto**.

### Ejemplos:

```java
int a = 3 + 2;               // Resultado: 5 (suma)
double b = 1.5 + 2.0;        // Resultado: 3.5 (suma)
String c = "Hola" + " Mundo"; // Resultado: "Hola Mundo" (concatenación)
String d = "Edad: " + 25;     // Resultado: "Edad: 25" (concatena número con texto)
```

> ⚠️ Es importante tener cuidado al usar `+` con distintos tipos, ya que puede cambiar el comportamiento esperado.

---

## Ejemplo completo

```java
public class CompraEjemplo {
    public static void main(String[] args) {
        double dineroDisponible = 500.0;
        double precioProducto = 450.0;
        boolean enOferta = true;

        // Evaluamos si puede comprar el producto
        boolean puedeComprar = dineroDisponible >= precioProducto && enOferta; // Guardará un valor true o false en "puede comprar" dependiendo
                                                                               // de si se cumplen o no las condiciones: 
                                                                               // El dinero disponbible es mayor o igual al precio del producto 
                                                                               // Y el producto debe estar en oferta.
        System.out.println("¿Puede comprar el producto?: " + puedeComprar);    // En este caso dará true ya que se cumplen las condiciones.
    }
}
```

---

## Ejercicios

### Ejercicio1Modulo03.java – Suma y resta básica

Crea dos variables enteras, realiza una suma y una resta entre ellas.  
Imprime los resultados.

**Salida esperada:**
```
Suma: 5
Resta: -1
```

<details>
  <summary>Ver solución</summary>

  <pre><code>public class Ejercicio1Modulo03 {
    public static void main(String[] args) {
        int a = 2;
        int b = 3;
        int suma = a + b;               // Sumamos las variables y el resultado lo asignamos a la variable "suma".
        int resta = a - b;              // Restamos las variables y el resultado lo asignamos a la variable "resta".
        System.out.println("Suma: " + suma);       // Imprimimos la variable "suma".
        System.out.println("Resta: " + resta);      // Imprimimos la variable "resta".

    //  System.out.println(a + b); // Ejemplo realizando la operación dentro el print
    }
}
</code></pre>

</details>

### Ejercicio2Modulo03.java – Comparar edades

Crea dos variables `int` con edades distintas.  
Imprime si una edad es mayor que la otra usando operadores de comparación.

**Salida esperada:**
```
¿La edad 1 es mayor a la edad 2? false
```

<details>
  <summary>Ver solución</summary>

  <pre><code>public class Ejercicio2Modulo03 {
    public static void main(String[] args) {
        int edad1 = 25;
        int edad2 = 30;
        boolean esMayorEdad1 = edad1 > edad2;       // Comparamos si la variable "edad1" es mayor que "edad2", dado que no es mayor, el resultado es false
        System.out.println("¿La edad 1 es mayor a la edad 2? " + esMayorEdad1);  // La edad 1 es mayor a la edad 2? false
    }
} 
</code></pre>

</details>

### Ejercicio3Modulo03.java – Promedio y aprobado o reprobado

Obtén el promedio de 5 calificaciones diferentes.  
Después crea un booleano que verifique si el promedio es mayor o igual a 6 para verificar si aprobo o no.  
Imprimé el valor del booleano y el promedio.

**Salida esperada:**
```
Aprobado: true
Promedio: 7.0
```

<details>
  <summary>Ver solución</summary>

  <pre><code>public class Ejercicio3Modulo03 {
    public static void main(String[] args) {
        int matematicas = 7;
        int español = 8;
        int ciencias = 6;
        int computacion = 10;
        int fisica = 8;

        double promedio = (matematicas + español + ciencias + computacion + fisica) / 5; // Sumamos todas las calificaciones y dividimos entre el total de materias.
        boolean siAprobado = promedio >= 6;         // Comparamos si el promedio es mayor o igual a 6.

        System.out.println("Aprobado: " + siAprobado + "\nPromedio: " + promedio); // Imprimimos las variables, en este caso dará true y promedio de 7.0
    }
}
</code></pre>

</details>

### Ejercicio4Modulo03.java – Módulo y comparación

Determinar si un número es par usando el operador % y una comparación.

**Salida esperada:**
```
¿El número 8 es par? true
```

<details>
  <summary>Ver solución</summary>

  <pre><code>public class Ejercicio4Modulo03 {
    public static void main(String[] args) {
        int numero = 8;

        boolean esPar = (numero % 2) == 0;    // Usando el modulo "%" aplicamos una división, pero el resultado será el residuo.
                                              // El residuo de una división entre 2 de un número par siempre va ser 0
                                              // Entonces si el residuo es 0, es par "true" o es impar

        System.out.println("¿El número " + numero + " es par? " + esPar); // La salida en este caso será "true" ya que 8 es par.
    }
}
</code></pre>

</details>

---

> Intenta resolver los ejercicios antes de ver las soluciones. Si lo necesitas, puedes dar click en "Ver solución".

## Gracias por continuar

- Gracias por seguir con el curso. Ya comenzamos a desarrollar más la lógica, así que tómate tu tiempo para resolver los ejercicios.  
- Siempre puedes volver a revisar la teoría, así como investigar más en otras fuentes. Lo importante es aprender y mejorar.  
- El siguiente módulo trata sobre condicionales. ¡Muchísimo éxito!

### Autor

[![GitHub](https://img.shields.io/badge/GitHub-MrGL1TCH-181717?logo=github&style=flat-square)](https://github.com/MrGL1TCH)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-angel--rm--dev-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/angel-rm-dev/)