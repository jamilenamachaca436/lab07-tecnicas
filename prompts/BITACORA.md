# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting. Herramienta de IA usada: (escribe aqui cual usaste)
##	Ejercicio	2:	Zero-shot, one-shot y few-shot
| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) | 
|------|-----------------|-------------------------|-----------------------------------| 
| Zero-shot | 5 aciertos| con iconos de colores  | si | 
| One-shot |5 aciertos | con guiones y lista ordenada | si | 
| Few-shot | 5 aciertos | con lista  comillas y flechas| si | 

##	Ejercicio	3:	Chain of Thought


| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) | 
|--------|--------------------|---------------------------|------------------| 
| Directo | 318.60 | no | si | 
| Paso a paso | 318.60| si | si | 


##	Ejercicio	4:	Role prompting

| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas | 
|---------|-------------------------------|-----------------------|---------------------| 
| A. Sin rol |sencillo | si| estudiante | 
| B. Rol docente | sencillo | si | estudiante | 
| C. Rol senior |tecnico | si | estudiante de software | 


## Ejercicio 5: Descomposicion

### Registro de pasos

##  Pedido por pasos

### Paso 1

**Qué me entregó la IA:**
Me dio 5 requisitos principales para crear el sistema de inventario.

**Comparación:**
Al hacerlo por pasos, la respuesta fue más directa y se enfocó solo en lo que pedí. En el pedido de una sola vez, la respuesta fue más general y extensa.

### Paso 2

**Qué me entregó la IA:**
Me indicó qué clases debía crear y qué información tendría cada una.

**Comparación:**
La respuesta fue más ordenada porque se basó en los requisitos del paso anterior. En el pedido de una sola vez, todo se presentó junto.

### Paso 3

**Qué me entregó la IA:**
Me dio el código de la clase `Producto`, incluyendo sus datos, el constructor y los métodos necesarios.

**Comparación:**
El código estuvo relacionado con lo que se había definido en los pasos anteriores. Esto hizo que el resultado fuera más claro que el pedido de una sola vez.

### Paso 4

**Qué me entregó la IA:**
Revisó el código de `Producto` y me dio 3 sugerencias para mejorarlo.

**Comparación:**
La revisión fue más específica porque la IA ya conocía el código creado en los pasos anteriores. En el pedido de una sola vez, todo se habría generado al mismo tiempo.

## Ejercicio 6: Prompt estructurado y autocritica
| Qué revisar | Cumple (Sí / No) |
|---|---|
| ¿Tiene las 4 columnas pedidas? | Sí |
| ¿Incluye el bloqueo después de 3 intentos? | Sí |
| ¿Incluye casos con campos vacíos? | Sí |
| ¿Indica qué casos agregó en la autocrítica? | Campos vacíos, correo sin @, contraseña con espacios, límite exacto de 3 intentos fallidos |
| ¿Hay algún caso repetido o que no tenga sentido? | Sí, intentos de inicio de sesión |
 



# Tarea: Mi prompt avanzado

## Tarea elegida

**Documentar una función de programación de forma clara y sencilla.**

La función elegida será una función llamada `calcularPromedio`, que recibe una lista de notas y calcula el promedio.

El objetivo es crear un prompt que permita obtener una documentación clara de la función, explicando qué hace, qué datos recibe, qué devuelve y mostrando un ejemplo sencillo de uso.

---

## Version 1: prompt basico

```text
Documenta la siguiente función:

def calcularPromedio(notas):
    return sum(notas) / len(notas)

Explica qué hace, qué recibe y qué devuelve.
```

### Técnica agregada

En esta primera versión se utilizó una instrucción directa y específica sobre la tarea que se desea realizar.

### ¿Por qué?

Porque primero es necesario establecer claramente qué se quiere obtener antes de agregar técnicas más avanzadas.

### ¿Qué mejoró en la respuesta?

La respuesta permite obtener una explicación básica de la función, indicando su propósito, los datos que recibe y el resultado que devuelve.

---

## Version 2

```text
Actúa como un redactor de documentación de software para estudiantes que están aprendiendo programación.

Documenta la siguiente función:

def calcularPromedio(notas):
    return sum(notas) / len(notas)

Explica de forma clara y sencilla:

1. Qué hace la función.
2. Qué datos recibe.
3. Qué resultado devuelve.
4. Un ejemplo sencillo de uso.

Evita utilizar términos técnicos innecesarios y organiza la respuesta con títulos y listas.
```

### Técnica agregada

Se agregó **role prompting** y **prompt estructurado**.

### ¿Por qué?

Se utilizó un rol específico para indicar cómo debe realizar la tarea la IA. En lugar de decir solamente "actúa como experto", se definió el rol de **redactor de documentación de software para estudiantes**.

También se estructuraron los puntos que debe contener la respuesta para evitar que la IA omita información importante.

### ¿Qué mejoró en la respuesta?

La documentación se vuelve más ordenada y fácil de entender. Además, el rol ayuda a que la explicación utilice un lenguaje apropiado para estudiantes y no una explicación demasiado técnica.

---

## Version 3: prompt final

```text
Actúa como redactor de documentación de software para estudiantes de programación que necesitan comprender una función sin utilizar lenguaje técnico innecesario.

Tu tarea es documentar la siguiente función:

def calcularPromedio(notas):
    return sum(notas) / len(notas)

Descompón la documentación en las siguientes partes:

1. Propósito:
   Explica en una o dos frases para qué sirve la función.

2. Datos de entrada:
   Indica qué información recibe la función y explica cada dato de forma sencilla.

3. Resultado:
   Explica qué devuelve la función.

4. Funcionamiento:
   Explica paso a paso qué realiza la función, sin mostrar razonamientos internos de la IA.

5. Ejemplo:
   Muestra un ejemplo sencillo de uso de la función y explica brevemente el resultado.

6. Errores o consideraciones:
   Indica al menos una situación que podría causar un problema al utilizar la función.

Utiliza el siguiente ejemplo como referencia del nivel de claridad esperado:

Ejemplo:
Función: sumarDosNumeros(a, b)

Descripción: Esta función recibe dos números y devuelve el resultado de sumarlos.

Entrada:
- a: primer número.
- b: segundo número.

Resultado:
- Devuelve la suma de los dos números.

Mantén este mismo nivel de sencillez y claridad.

Antes de finalizar, realiza una autocrítica de la documentación y verifica que:

- La explicación sea clara para un estudiante.
- Se hayan explicado los datos de entrada y el resultado.
- Se incluya un ejemplo.
- No existan explicaciones técnicas innecesarias.
- La información corresponda realmente con el código proporcionado.

Formato de respuesta obligatorio:

# Documentación de la función

## Propósito
...

## Datos de entrada
...

## Resultado
...

## Funcionamiento
...

## Ejemplo
...

## Errores o consideraciones
...

## Revisión final
...
```

### Técnicas agregadas

En esta versión se combinaron **role prompting, descomposición, few-shot, prompt estructurado y autocrítica**.

### ¿Por qué?

Se agregaron estas técnicas para controlar mejor la respuesta y conseguir una documentación completa, ordenada y fácil de entender.

* **Role prompting:** establece un rol específico relacionado con la documentación para estudiantes.
* **Descomposición:** divide la tarea en partes pequeñas como propósito, entrada, resultado, funcionamiento y ejemplo.
* **Few-shot:** proporciona un ejemplo de cómo debe verse la documentación.
* **Prompt estructurado:** establece instrucciones y un formato obligatorio para organizar la respuesta.
* **Autocrítica:** solicita una revisión final para comprobar que la documentación cumpla los requisitos establecidos.

### ¿Qué mejoró en la respuesta?

La respuesta final es más completa y consistente. La IA tiene instrucciones claras sobre qué información debe incluir, cómo debe explicarla y cómo debe organizarla. Además, la autocrítica permite comprobar que no falten elementos importantes.

---

## Técnicas usadas en el prompt final

| Técnica             | Parte del prompt donde se utiliza                                      | Función                                                   |
| ------------------- | ---------------------------------------------------------------------- | --------------------------------------------------------- |
| Role prompting      | "Actúa como redactor de documentación de software para estudiantes..." | Define el rol que debe asumir la IA.                      |
| Descomposición      | "Descompón la documentación en las siguientes partes..."               | Divide la tarea en pasos más pequeños.                    |
| Few-shot            | Ejemplo de `sumarDosNumeros(a, b)`                                     | Muestra a la IA cómo debe ser el resultado esperado.      |
| Prompt estructurado | "Formato de respuesta obligatorio"                                     | Define la estructura que debe seguir la respuesta.        |
| Autocrítica         | "Antes de finalizar, realiza una autocrítica..."                       | Permite revisar si la respuesta cumple las instrucciones. |

---

## Evaluación del resultado

| Criterio                                    | ¿Cumple? |
| ------------------------------------------- | -------- |
| Utiliza un rol específico                   | Sí       |
| Incluye un formato de respuesta definido    | Sí       |
| Explica claramente la función               | Sí       |
| Incluye los datos de entrada y resultado    | Sí       |
| Incluye un ejemplo                          | Sí       |
| Utiliza al menos tres técnicas de prompting | Sí       |
| Realiza una revisión final                  | Sí       |
| Evita lenguaje técnico innecesario          | Sí       |

---

## Por qué elegí estas técnicas

Elegí **role prompting, descomposición, few-shot, prompt estructurado y autocrítica** porque la tarea consiste en generar una documentación clara, ordenada y fácil de entender. El role prompting ayuda a establecer el tipo de explicación que se necesita, mientras que la descomposición permite dividir la documentación en partes específicas. El few-shot sirve para mostrar un ejemplo del resultado esperado y el prompt estructurado ayuda a mantener un formato organizado. Finalmente, la autocrítica permite revisar que la documentación contenga toda la información solicitada. No utilicé otras técnicas porque estas son suficientes para controlar el contenido, el nivel de explicación y la estructura de una documentación de funciones.
