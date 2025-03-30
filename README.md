# PrograIIEntrega7Clase
Entrega realizada por:
- Rafael Godoy
- Alejandro Santamaría

## Ejercicio 61

### Explique la diferencia entre tipo abstracto de datos (TAD) y estructura de datos.

Un tipo abstacto de datos es un conjunto de datos y operaciones que se pueden realizar sobre esos datos, mientras que una estructura de datos es una forma de organizar datos para ser usados de manera eficiente.
Una estructura de datos es una implementación específica de un TAD, porque en todo conjunto de datos y operaciones hay que organizar los datos para poderlos usar.

## Ejercicio 62
### Explique qué es una lista y cuáles son sus operaciones típicas.

Es una TAD que representa una colección ordenada de elementos. Es una secuencia en la que cada elemento tiene una posición específica dentro de la secuencia.
Debe estar ordenada, los elementos deben ser guardados uno después del otro, se permiten elementos duplicaddos, el tamaño es dinámico y se puede acceder a cada elemento por su posición en la lista.

En una lista se pueden realizar las siguientes operaciones: 
  acceder a un elemento mediante su índice.
  obtener el tamaño de la lista.
  comprobar si está vacía.
  comprobar si un elemento se encuentra en la lista.
  obtener el índice de un elemento si se encuentra en la lista.
  agregar al final.
  insertar en una posición.
  agregar al principio.
  eliminar al final.
  eliminar al principio.
  eliminar en una posición.
  reemplazar elemento
  copiar.
  invertir lista.
  ordenar.

## Ejercicio 63
### Explique las diferentes formas de implementar una lista.
Existen principalmente dos formas comunes de implementar el TAD Lista como estructura de datos:

- Listas basadas en Arrays (Arrays o Arreglos):
  <br> -> Se utiliza un array de tamaño fijo o dinámico para almacenar los elementos de la lista de forma contigua en memoria.
  <br> -> ArrayList en Java es un ejemplo de implementación de lista basada en array dinámico.
  <br> -> Ventajas:
  <br> Acceso aleatorio eficiente: Acceder a un elemento por índice (get(indice)) es muy rápido porque se puede calcular directamente la dirección de memoria del elemento.
  <br> Buena localidad de referencia: Los elementos están almacenados contiguamente, lo que mejora el rendimiento de la caché de la CPU al acceder a elementos cercanos.
  <br> -> Desventajas:
  <br> Inserción y eliminación ineficientes en medio de la lista: Insertar o eliminar un elemento en una posición intermedia requiere desplazar todos los elementos siguientes, lo que puede ser costoso en tiempo.
  <br> Tamaño fijo inicial (en arrays estáticos): Si se utiliza un array de tamaño fijo, puede ser necesario crear un nuevo array más grande y copiar todos los elementos si se supera la capacidad. Los arrays dinámicos como ArrayList manejan esto automáticamente, pero aún así implica una operación costosa de copia cuando se necesita redimensionar.


- Listas Enlazadas (Linked Lists):
  <br> -> Se utilizan nodos para almacenar cada elemento de la lista. Cada nodo contiene el dato del elemento y una referencia (puntero) al siguiente nodo en la lista.
  <br> -> LinkedList en Java es un ejemplo de implementación de lista enlazada (doblemente enlazada en este caso).
  <br> -> Ventajas:
  <br> Inserción y eliminación eficientes: Insertar o eliminar un elemento en cualquier posición (especialmente al principio o al final) es muy rápido porque solo se necesita modificar las referencias de los nodos adyacentes. No hay necesidad de desplazar elementos.
  <br> Tamaño dinámico: El tamaño de una lista enlazada puede crecer o decrecer dinámicamente según sea necesario, sin necesidad de redimensionamiento costoso.
  <br> -> Desventajas:
  <br> Acceso aleatorio ineficiente: Acceder a un elemento por índice (get(indice)) requiere recorrer la lista desde el principio hasta llegar al índice deseado, O(n).
  <br> Mayor overhead de memoria: Cada nodo requiere espacio adicional para almacenar la referencia al siguiente nodo, lo que puede resultar en un mayor consumo de memoria en comparación con un array para el mismo número de elementos.
  <br> Peor localidad de referencia: Los nodos pueden estar dispersos en la memoria, lo que puede afectar negativamente el rendimiento de la caché de la CPU.

## Ejercicio 64
### Explique las ventajas e inconvenientes del ArrayList frente al LinkedList.

| Característica          | ArrayList                                  | LinkedList                                  |
| ----------------------- | ------------------------------------------ | ------------------------------------------- |
| Acceso Aleatorio        | Rápido (O(1))                               | Lento (O(n))                                |
| Inserción/Eliminación   | Lento en medio (O(n)), Rápido al final (O(1) amortizado) | Rápido (O(1)) al principio/final, O(1) con referencia al nodo |
| Memoria por Elemento    | Menor                                      | Mayor                                       |
| Localidad de Referencia | Buena                                      | Peor                                        |
| Redimensionamiento      | Costoso (amortizado)                       | No necesita                                 |

## Ejercicio 65
### Examine los siguientes códigos fuente e identifique la relación entre ellos:
#### Collection.java. -->
- Define la interfaz Collection.
- Es la interfaz raíz de la jerarquía de colecciones en Java.
- Define las operaciones básicas comunes que todas las colecciones deben soportar, como add(), remove(), contains(), size(), isEmpty(), iterator(), etc.
- Representa el concepto más general de una colección de objetos.

#### List.java. -->
- Define la interfaz List.
- Extiende la interfaz Collection. Esto significa que List hereda todas las operaciones de Collection y añade operaciones específicas para listas, que son colecciones ordenadas que permiten elementos duplicados.
- Introduce operaciones relacionadas con el orden y la posición de los elementos, como get(index), set(index, element), add(index, element), remove(index), indexOf(), lastIndexOf(), etc.
- Representa un tipo más específico de colección que Collection, con características de orden y acceso por índice.

#### ArrayList.java. -->
- Define la clase ArrayList.
- Implementa la interfaz List. Esto significa que ArrayList proporciona una implementación concreta de todas las operaciones definidas en la interfaz List.
- Utiliza un array dinámico como estructura de datos subyacente para almacenar los elementos de la lista.
- Proporciona una implementación basada en array del TAD Lista.

#### LinkedList.java. -->
- Define la clase LinkedList.
- Implementa la interfaz List. Similar a ArrayList, LinkedList también proporciona una implementación concreta de la interfaz List.
- Utiliza una lista doblemente enlazada como estructura de datos subyacente para almacenar los elementos.
- Proporciona una implementación basada en lista enlazada del TAD Lista.

#### Relación Jerárquica (Herencia e Implementación):
Collection (Interfaz)
^
| Extiende
List (Interfaz)
^       ^
| Implem. | Implem.
ArrayList  LinkedList (Clases)

## Ejercicio 66
### Explique qué es una pila y cuáles son sus operaciones típicas.
Una Pila (Stack) es un TAD que representa una colección ordenada de elementos que sigue el principio LIFO (Last-In, First-Out), o Último en Entrar, Primero en Salir.

- Operaciones típicas de una Pila (TAD):
  <br> -> push(elemento) (Apilar):
  <br> Añade un elemento a la cima de la pila. Es la operación para "meter" un elemento en la pila.
  <br> -> pop() (Desapilar):
  <br> Elimina y devuelve el elemento que está en la cima de la pila. Es la operación para "sacar" el elemento superior de la pila. Si la pila está vacía, generalmente se lanza una excepción (como EmptyStackException en Java) o se devuelve un valor especial (como null, aunque esto es menos común en pilas).
  <br> -> peek() (Mirar la cima):
  <br> Devuelve el elemento que está en la cima de la pila, sin eliminarlo. Permite ver el elemento superior sin modificar la pila. Si la pila está vacía, generalmente devuelve null o lanza una excepción.
  <br> -> isEmpty() (Está vacía):
  <br> Devuelve true si la pila no contiene elementos (está vacía), y false en caso contrario.
  <br> -> size() (Tamaño):
  <br> Devuelve el número de elementos que contiene la pila.

## Ejercicio 67
### Indique dos aplicaciones en que se utilzan pilas.
Las pilas son una estructura de datos fundamental con numerosas aplicaciones en informática. Aquí tienes dos ejemplos comunes:

- Pila de Llamadas a Funciones (Call Stack):
  <br> En la ejecución de programas, especialmente en lenguajes de programación que permiten llamadas a funciones anidadas (como Java, C++, Python, etc.), se utiliza una pila llamada pila de llamadas o call stack para gestionar el flujo de ejecución de las funciones.
  <br> Cuando se llama a una función, se crea un marco de pila (stack frame) que contiene información sobre esa función, como sus variables locales, parámetros y la dirección de retorno.
  <br> Cuando una función termina su ejecución, su marco de pila se desapila de la pila de llamadas, y la ejecución del programa continúa en la función que la llamó, en la dirección de retorno almacenada en el marco de pila desapilado.
  <br> La pila de llamadas asegura que las funciones se ejecuten en el orden correcto y que el programa regrese al punto de llamada adecuado después de que cada función termine.

- Evaluación de Expresiones y Conversión de Notación:
  <br> Las pilas se utilizan en algoritmos para evaluar expresiones aritméticas, especialmente expresiones en notación infija (la notación común, como 2 + 3 * 4).
  <br> También se utilizan para convertir expresiones entre diferentes notaciones, como de notación infija a notación postfija o prefija.

## Ejercicio 68
### Explique la relación existente entre el TAD lista y el TAD pila.
La relación entre el TAD Lista y el TAD Pila es que el TAD Pila es un caso especial o una especialización del TAD Lista. En otras palabras, una pila puede ser vista como una lista con restricciones adicionales en las operaciones permitidas y en el orden de acceso a los elementos.

- Puntos clave de la relación:
  <br> -> Pila como tipo de Lista restringida:
  <br> Ambos TADs (Lista y Pila) representan colecciones ordenadas de elementos.
  <br> Sin embargo, una Pila restringe la forma en que se pueden añadir y eliminar elementos, y cómo se puede acceder a ellos.
  <br> Mientras que una Lista permite acceso, inserción y eliminación en cualquier posición (o en muchas posiciones), una Pila solo permite operaciones en la cima (el último elemento añadido).
  <br> -> Operaciones de Pila como subconjunto de operaciones de Lista:
  <br> Las operaciones típicas de una Pila (push, pop, peek) son subconjuntos de las operaciones que se pueden realizar en una Lista.
  <br> Podrías implementar un TAD Pila utilizando un TAD Lista como estructura de datos subyacente. Por ejemplo, podrías usar un ArrayList o un LinkedList para almacenar los elementos de la pila y luego implementar las operaciones push, pop, peek utilizando las operaciones de la Lista subyacente, pero restringiendo el acceso solo a la "cima" de la lista (que podrías definir como el final de la lista en una implementación basada en array o lista enlazada).
  <br> -> Abstracción vs. Especialización:
  <br> El TAD Lista es más general y abstracto. Proporciona una interfaz flexible para trabajar con colecciones ordenadas.
  <br> El TAD Pila es más especializado y concreto. Define un comportamiento específico (LIFO) y un conjunto de operaciones limitadas que son adecuadas para ciertos tipos de problemas.

## Ejercicio 69
### Examine el código fuente de las clases Stack.java y Vector.java. Identifique la relación entre ellos y con ArrayList.java.
#### Vector.java:
- Vector es una clase más antigua en Java, que existía incluso antes de la introducción del Collections Framework en Java 1.2.
- Implementa una lista dinámica basada en array, similar conceptualmente a ArrayList.
- La característica clave de Vector es que sus métodos están sincronizados. Esto significa que Vector es thread-safe (seguro para ser usado en entornos multihilo sin problemas de concurrencia) por defecto. Sin embargo, esta sincronización también añade un overhead de rendimiento.

#### Stack.java:
- Stack es una clase que extiende la clase Vector.
- Stack no implementa la interfaz List directamente, sino que hereda la implementación de lista de Vector porque Vector ya implementa List.
- Stack añade operaciones específicas para el TAD Pila: push(), pop(), peek(), empty(), search(). Estas operaciones se implementan utilizando los métodos heredados de Vector. Por ejemplo, push() se implementa usando addElement() de Vector, pop() usa removeElementAt(size() - 1) y lastElement() de Vector, etc.
- En esencia, Stack es una adaptación de Vector para proporcionar una interfaz de pila (LIFO). Está construida sobre la funcionalidad de Vector.

##### ArrayList.java:
- ArrayList es una clase más moderna que se introdujo con el Collections Framework.
- También implementa una lista dinámica basada en array, similar a Vector en funcionalidad básica.
- La diferencia clave con Vector es que ArrayList no está sincronizada. Esto significa que ArrayList es no thread-safe por defecto, pero generalmente ofrece mejor rendimiento en entornos monohilo o cuando la sincronización no es necesaria o se gestiona externamente.
- ArrayList es generalmente preferida sobre Vector en aplicaciones nuevas, a menos que se requiera explícitamente la thread-safety incorporada de Vector.

#### Relacion entre clases
Vector (Clase - Lista sincronizada basada en array)
^
| Extiende
Stack (Clase - Pila, construida sobre Vector)

ArrayList (Clase - Lista NO sincronizada basada en array)

## Ejercicio 70
```
import java.util.Stack;
public class DemoPilas
{
  public static void main(String[] args)
  {
    Stack<Integer> pila = new Stack<>();
    pila.push(1);
    pila.push(2);
    System.out.println(pila);
    System.out.println(pila.peek());
    pila.pop();
  System.out.println(pila);
  }
}
```

Primero se crea un stack llamado pila, después se le añaden los enteros 1 y 2, a continuación se imprime la pila, después, el elemento en la cima de la pila, después saca el elemento en la cima de la pila y vuelve a imprimir la pila.

## Ejercicio 71 
### Explique qué es una cola y cuáles son sus operaciones típicas.

Una cola es una TAD que representa una colección ordenada en la que los elementos se añaden al final y se extraen al principio (FIFO).
Las operaciones típicas que se hacen en una cola son:
  Añadir elemento al final de la cola
  Extraer elemento al principio de la cola
  Ver el elemento al principio de la cola sin extraer
  Indicar si la cola está vacía

  ## Ejercicio 72
  ### Indique tipos de aplicaciones en que se utilicen colas.
  Las colas se utilizan en gestión de tareas y procesos, utilizan colas para gestionarlos.
  También se utiliza en el procesamiento de eventos en GUI y sistemas basados en eventos.
  También para comunicación entre procesos o hilos, pueden actuar como buffer para la comunicación entre diferentes partes de un programa o programaas diferentes.
  Sirven para explorar los nodos de un árbol por nivel.
  Por último, en simulaciones de sistemas de colas de espera.

  ## Ejercicio 73
  ### Examine el código de la clase ArrayDequeue.java y explique cómo aplica la aritmética modular.
  Con la aritmética modular se gestiona de forma circular los índices del array.
  Esta implementación permite no desplazar los elementos en memoria cada vez que se elimina un elemento del frente o se añade al final, lo que hace es mover el índice por el que empieza y por el que termina la cola dentro del array, de forma circular.
  La aritmética modular se usa porque haciendo el módulo sobre la longitud total del array los índices pueden dar la vuelta una vez llegan al final de la cola, haciendo el array circular.

  ## Ejercicio 74
  ### Ejecute y explique el siguiente código, y compare su comportamiento con el programa del ejercicio 69:
  ```
import java.util.ArrayDeque;
public class DemoColas
{
  public static void main(String[] args)
  {
    ArrayDeque<Integer> cola = new ArrayDeque<>();
    cola.add(1);
    cola.add(2);
    System.out.println(cola);
    System.out.println(cola.peek());
    System.out.println(cola.poll());
    System.out.println(cola);
  }
}
```
Este código ejecuta algo similar que el ejercicio 69 pero en una cola en vez de en un stack.
La diferencia principal es que cuando añades elementos, se añaden al final en vez de al principio, lo que cambia el resultado de peek y poll (su equivalente es pop), siendo el primer elemento en haber sido indoducido el resultado.
A la hora de imprimir, se imprimirán en orden de entrada, en lugar de orden inverso.
