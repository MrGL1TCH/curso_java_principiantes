# Guía rápida para instalar Java en tu computadora

> Si nunca has instalado Java antes, no te preocupes. Aquí tienes una guía paso a paso para hacerlo correctamente.

---

## ¿Qué necesitas?

- El **Java Development Kit (JDK)**: Es un conjunto de herramientas que te permite compilar y ejecutar programas en Java.

---

## Instalar Java JDK (Java Development Kit)

### Opción recomendada: Instalar OpenJDK (versión 17 o superior)

1. Ve a esta página: [https://jdk.java.net/](https://jdk.java.net/)
2. Descarga la última **versión estable (LTS)** de Java para tu sistema operativo (Windows, Mac, Linux).
3. Instala siguiendo las instrucciones del instalador.

También puedes instalar Oracle JDK desde [https://www.oracle.com/java/technologies/javase-downloads.html](https://www.oracle.com/java/technologies/javase-downloads.html)

---

### Verificar que Java se instaló correctamente

Una vez instalado, abre una terminal o consola y escribe:

```bash
java -version
```

Deberías ver algo como:

```
java version "17.0.X" 202X-XX-XX
```

Si ves un error como "java no se reconoce...", reinicia tu computadora o revisa si se añadió correctamente al `PATH`.

---

## Guía de uso de Java en Visual Studio Code (VS Code)

Si vas a usar **VS Code** como tu editor para programar en Java, debes instalar algunas **extensiones** necesarias para que funcione correctamente:

1. Abre VS Code.
2. Ve al icono de **Extensiones** (símbolo de cuadrito).
3. Busca e instala estas extensiones:

- `Extension Pack for Java`\
  Contiene todas las herramientas necesarias para programar en Java con VS Code.\
  Incluye:
  - Soporte para IntelliSense (autocompletado)
  - Ejecución de código
  - Depuración
  - Formato automático

O puedes instalar individualmente:

- `Language Support for Java(TM) by Red Hat`
- `Debugger for Java`
- `Java Test Runner`
- `Maven for Java` (opcional)
- `Visual Studio IntelliCode` (opcional)

4. Reinicia VS Code si es necesario.

Nota: VS Code solo es un editor, así que necesitas tener instalado **Java JDK** previamente (como se explicó más arriba).

---

## IDEs recomendados (editores de código)

Puedes programar en Java desde muchos editores. Aquí te recomendamos los más usados:

| IDE / Editor           | Nivel          | Recomendado para                  |
| ---------------------- | -------------- | --------------------------------- |
| **Visual Studio Code** | Medio          | Flexibilidad, liviano             |
| **IntelliJ IDEA**      | Medio/Avanzado | Muy completo, excelente para Java |
| **Eclipse**            | Medio/Avanzado | Histórico y robusto para Java     |
| **NetBeans**           | Principiante   | Fácil de configurar y usar        |

Cualquiera de ellos funcionará para este curso, aunque recomendamos **VS Code** o **IntelliJ** si ya tienes algo de experiencia.

---

## Alternativa: Ejecutar Java desde el navegador

Si no deseas instalar nada al inicio, puedes usar plataformas en línea para correr tus programas Java directamente desde el navegador:

- [https://replit.com/languages/java10](https://replit.com/languages/java10)
- [https://www.jdoodle.com/](https://www.jdoodle.com/)
- [https://www.onlinegdb.com/online\_java\_compiler](https://www.onlinegdb.com/online_java_compiler)

Estas plataformas son ideales para pruebas rápidas o si estás aprendiendo desde una computadora compartida o pública.

---

¡Listo! Ahora ya puedes comenzar con tu primer archivo Java.
