# Checkpoint 6

## ¿Para qué usamos Clases en Python?

Las clases de Python se usan para agrupar datos y funciones relacionados en una sola unidad, haciendo que los programas sean más claros, fáciles de entender y reutilizables. Las clases se utilizan en desarrollo web, ciencia de datos, automatización y muchos proyectos del mundo real.
<br>
En comparación con otros lenguajes de programación, el mecanismo de clases de Python añade clases con sintaxis y semántica más reducidas, lo que puede hacer que resulte más sencillo de utilizar y entender.
<br>
Por ejemplo, si quisieramos diseñar los personajes de un videojuego con ciertas características (vitalidad, ataque, defensa y velocidad), podríamos diseñar la clase ```Personaje``` que guarde esas características como una especie de "*blueprint*" o *plantilla*, y luego crear los personajes concretos (```paladin, ladron```) con valores diferentes en las mencionadas características.

**Ejemplo**
```
class Personaje:
    def __init__(self, vitalidad, ataque, defensa, velocidad):
        self.vitalidad = vitalidad
        self.ataque = ataque
        self.defensa = defensa
        self.velocidad = velocidad

paladin = Personaje(120, 20, 30, 5)
ladron = Personaje(80, 10, 10, 30)

print(f"Vitalidad del plaladín: {paladin.vitalidad}")
print(f"Velocidad del plaladín: {paladin.velocidad}")
print(f"Velocidad del ladrón: {ladron.vitalidad}")
```

*Resultado:*
```
Vitalidad del plaladín: 120
Velocidad del plaladín: 5
Velocidad del ladrón: 80
```


## ¿Qué método se ejecuta automáticamente cuando se crea una instancia de una clase?

El método que se ejecuta automáticamente al crear una instancia de una clase es el constructor. Su función principal es inicializar los atributos y establecer el estado inicial del objeto.

Como puede verse en el ejemplo anterior, el método ```__init__``` de Python se declara dentro de una clase y se utiliza para inicializar los atributos de un objeto en cuanto este se forma. Al definir un método ```__init__(self)```, siempre se pasa un parámetro predeterminado, llamado *"self"*, en su argumento. Este *"self"* representa el *objeto* de la clase.

## ¿Cuáles son los tres verbos de API?

Los tres verbos de __API__ son __GET__, __POST__ y __DELETE__. Estos verbos son instrucciones enviadas por el navegador para indicarle al servidor qué acción realizar en un recurso, ya sea una página web, una imagen o datos.

__1- GET:__ Se utiliza para recuperar o leer información de un recurso.
<br>
__2- POST:__ Se utiliza para crear un nuevo recurso.
<br>
__3- DELETE:__ Se utiliza para eliminar un recurso.


## ¿Es MongoDB una base de datos SQL o NoSQL?

Una base de datos SQL es un sistema de gestión de bases de datos relacionales que almacena datos estructurados en tablas con filas y columnas, similar a una hoja de cálculo.
<br> 
Por otra parte, una base de datos NoSQL ("no solo SQL") es un sistema de almacenamiento no relacional diseñado para manejar grandes volúmenes de datos no estructurados o semiestructurados, que a diferencia de SQL, utilizan esquemas flexibles, permitiendo guardar información en tipos de documentos como JSON en lugar de tablas rígidas.

Teniendo esto en cuenta, __MongoDB__ es una base de datos NoSQL, un sistema orientado a documentos que almacena datos en formatos tipo JSON (específicamente BSON), lo que permite esquemas flexibles, alta escalabilidad horizontal y un manejo eficiente de datos no estructurados.

[Fuente: MongoDB](https://www.mongodb.com/es/resources/basics/databases/nosql-explained/nosql-vs-sql#:~:text=Casos%20de%20uso%20de%20bases,datos%20NoSQL%2C%20compatible%20con%20ACID.)

## ¿Qué es una API?

Una __API__ o __Interfaz de Programación de Aplicaciones__ es un conjunto de reglas, protocolos y herramientas que permite que dos componentes de software se comuniquen e intercambien datos entre sí de forma segura. Actúa como un intermediario o "puente" que facilita a los desarrolladores integrar funcionalidades de otras aplicaciones sin necesidad de crearlas desde cero

![API](/Users/juditvega/Desktop/Cursos/programacion_2/checkpoints/checkpoint_6/images/API_que.png)
[Fuente imagen: outvio](https://outvio.com/es/blog/que-es-una-api/)

## ¿Qué es Postman?

Postman es una plataforma de desarrollo y pruebas de APIs que funciona desde su aplicación de escritorio o web, enviando peticiones HTTP y mostrando las respuestas de servidores sin necesidad de programar código.
<br>
Simplifica las solicitudes HTTP, permitiendo a los usuarios enviar, inspeccionar y automatizar llamadas a la API. Sus principales características incluyen espacios de trabajo compartidos, pruebas automatizadas y generación de documentación.

## ¿Qué es el polimorfismo?

Polimorfismo significa "muchas formas". Se refiere a la capacidad de una entidad (como una función u objeto) para realizar diferentes acciones según el contexto.

En Python, el polimorfismo permite que un mismo método, función u operador se comporte de manera diferente según el objeto con el que trabaje. Esto hace que el código sea más flexible y reutilizable. Este principio fundamental de la programación orientada a objetos hace que el código sea más modular, extensible y fácil de mantener.

Ejemplo:
```
class Titulo:
    def __init__(self, content):
      self.content = content

    def render(self):
      return f'<h1>{self.content}</h1>'

class Parrafo:
  def __init__(self, content):
    self.content = content

  def render(self):
    return f'<div>{self.content}</div>'

titulo = Titulo('Aquí probamos el primer texto')
parrafo_uno = Parrafo('Aquí el segundo')
parrafo_dos = Parrafo('Y aquí el tercero')

def html_render(tag_object):
  print(tag_object.render())

html_render(titulo)
html_render(parrafo_uno)
html_render(parrafo_dos)
```

*Resultado:*
```
<h1>Aquí probamos el primer texto</h1>
<div>Aquí el segundo</div>
<div>Y aquí el tercero</div>
```
En el ejemplo, la función *tag_object.render()*
se puede utilizar con las clases ```Titulo``` y ```Parrafo```, generando ```h1``` o ```div``` (formas distintas) al texto que se incluya en cada caso.

## ¿Qué es un método dunder?

Un método dunder es un método especial de una clase cuyo nombre empieza y termina con doble guion bajo (__dunder__ viene de *“double underscore”* o __ ).
Se pueden usar para personalizar el comportamiento de operaciones como ```+, -, *, **, ==``` y en estructuras de datos personalizadas, inicializar y eliminar objetos, obtener su representación en cadena, habilitar la indexación de objetos y mucho más.

Por ejemplo existe el método ```__Init__```, que se ejecuta automáticamente al crear un objeto:

```
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad

p1 = Persona("Suna", 29)

print(p1.nombre)
print(p1.edad)
```

*Resultado:*
```
Suna
29
```
En Python, éste método se conoce como método de inicialización. Se llama automáticamente cuando se crea una nueva instancia de una clase. Permite definir comportamientos personalizados que establecen el estado inicial de un objeto, como definir atributos o realizar acciones específicas en el momento de la creación del objeto.
Es importante saber que ```self``` representará al objeto que se está creando (en este caso, ```p1```).

## ¿Qué es un decorador de python?
Los decoradores permiten añadir comportamiento adicional a una función sin modificar su código.
<br>
Un decorador es una función que recibe otra función como entrada y devuelve una nueva función. Se escribe usando el símbolo ```@```. 
<br>
Un ejemplo de operador sería ```@property```, que facilita la definición de propiedades sin necesidad de llamar manualmente a la función integrada ```property()```. Se utiliza para devolver los atributos de propiedad de una clase a partir de los métodos ```getter```, ```setter``` y ```deleter``` especificados como parámetros.

Ejemplo:
```
class Persona:
    def __init__(self, nombre, apellido):
        self.nombre = nombre
        self.apellido = apellido

    @property
    def nombre_completo(self):
        return f"{self.nombre} {self.apellido}"

p = Persona("Suna", "Ruiz")

print(p.nombre_completo)
```

*Resultado:*
```
Suna Ruiz
```