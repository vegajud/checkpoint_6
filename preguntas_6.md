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

También es clave entender que no siempre es necesario utilizar clases. Es el caso de muchos programas pequeños que funcionan sin Programación Orientada a Objetos.
Los casos más habituales serían al escribir scripts pequeños que hacen una tarea simple (usar funciones suele ser suficiente) o programas muy lineales que requieren un
flujo simple (como leer datos, procesar y mostrar su resultado).

Sí son útiles cuando en el código existen muchas entidades similares (usuarios, productos), son programas grandes, se necesita reutilizar el código o son sistemas con muchas partes interactuando.

En resumen, por lo general usamos clases en Python para crear objetos a partir de una plantilla, organizar código, reutilizar la lógica empleada en él y modelar entidades complejas.

## ¿Qué método se ejecuta automáticamente cuando se crea una instancia de una clase?

El método que se ejecuta automáticamente al crear una instancia de una clase es el constructor. Su función principal es inicializar los atributos y establecer el estado inicial del objeto.

Como puede verse en el ejemplo anterior, el método ```__init__``` de Python se declara dentro de una clase y se utiliza para inicializar los atributos de un objeto en cuanto este se forma. Al definir un método ```__init__(self)```, siempre se pasa un parámetro predeterminado, llamado *"self"*, en su argumento. Este *"self"* representa el *objeto* de la clase.

En resumen, el atributo ```__init__```  se utiliza para asignar valores iniciales a los atributos, preparar el objeto para usarse y ejecutar código al crear el objeto.

## ¿Cuáles son los tres verbos de API?

Los tres verbos de __API__ son __GET__, __POST__ y __DELETE__. Estos verbos son instrucciones enviadas por el navegador para indicarle al servidor qué acción realizar en un recurso, ya sea una página web, una imagen o datos.

__1- GET:__ Se utiliza para recuperar o leer información de un recurso.

**Ejemplo**
```
GET /usuarios
```
Pide la lista de usuarios sin modificar nada, sólo consulta información.

__2- POST:__ Se utiliza para crear un nuevo recurso.


**Ejemplo**
```
POST /usuarios
```
Crea un nuevo usuario y se envían datos en el cuerpo de la petición, dando como resultado algo así:

```
{
  "nombre": "Ander",
  "edad": 39
}
```

__3- DELETE:__ Se utiliza para eliminar un recurso.

**Ejemplo**
```
DELETE /usuarios/5
```
Eliminará el usuario con ID = 5.



## ¿Es MongoDB una base de datos SQL o NoSQL?

Una base de datos SQL es un sistema de gestión de bases de datos relacionales que almacena datos estructurados en tablas con filas y columnas, similar a una hoja de cálculo.
<br> 
Por otra parte, una base de datos NoSQL ("no solo SQL") es un sistema de almacenamiento no relacional diseñado para manejar grandes volúmenes de datos no estructurados o semiestructurados, que a diferencia de SQL, utilizan esquemas flexibles, permitiendo guardar información en tipos de documentos como JSON en lugar de tablas rígidas.

Teniendo esto en cuenta, __MongoDB__ es una base de datos NoSQL, un sistema orientado a documentos que almacena datos en formatos tipo JSON (específicamente BSON), lo que permite esquemas flexibles, alta escalabilidad horizontal y un manejo eficiente de datos no estructurados.

[Fuente: MongoDB](https://www.mongodb.com/es/resources/basics/databases/nosql-explained/nosql-vs-sql#:~:text=Casos%20de%20uso%20de%20bases,datos%20NoSQL%2C%20compatible%20con%20ACID.)

## ¿Qué es una API?

Una __API__ o __Interfaz de Programación de Aplicaciones__ es un conjunto de reglas, protocolos y herramientas que permite que dos componentes de software se comuniquen e intercambien datos entre sí de forma segura. Actúa como un intermediario o "puente" que facilita a los desarrolladores integrar funcionalidades de otras aplicaciones sin necesidad de crearlas desde cero

__Funcionamiento de una API__

Funcionan compartiendo datos entre aplicaciones, sistemas y dispositivos. Esto se produce mediante un ciclo de solicitud y respuesta. La solicitud se envía a la API, que recupera los datos y los devuelve al usuario.

![API](/Users/juditvega/Desktop/Cursos/programacion_2/checkpoints/checkpoint_6/images/API_que.png)
[Fuente imagen: outvio](https://outvio.com/es/blog/que-es-una-api/)

El funcionamiento básico es siempre petición - procesamiento - respuesta:

__1- Petición (Request):__
<br>
Tu aplicación envía un mensaje a la API con instrucciones, como por ejemplo “Dame el clima de Bilbao” o “Encuentra todos los post que contengan la palabra {palabra}”.

Lo hace usando HTTP (el mismo protocolo de las webs) y con los verbos API (mencionados anteriormente): GET (pedir datos), POST (enviar datos), PUT (actualizar datos) y DELETE (borrar datos).

__2- Procesamiento:__
<br>
La API recibe la petición y la traduce al lenguaje del sistema que maneja los datos.
Por ejemplo, consulta la base de datos o llama a otra función interna.

__3- Respuesta (Response):__
<br>
La API devuelve los datos en un formato estándar, normalmente JSON o XML, que tu aplicación puede leer y usar.

Ejemplo de petición:
```
GET https://api.weather.com/current?city=Bilbao
```

*Respuesta de la API:*
```
{
  "city": "Bilbao",
  "temperature": 18,
  "condition": "Cloudy"
}
```

__Posibles ventajas del uso de las APIs__

Las ventajas más habituales de las APIs incluyen:

__1- Automatización:__ se pueden usar para automatizar tareas repetitivas y que consumen mucho tiempo, de modo que las personas puedan concentrarse en tareas más complejas mejorando la productividad.

__2- Innovación:__ Las API públicas pueden ser utilizadas por equipos de ingeniería externos, permitiendo que los desarrolladores reutilicen la funcionalidad existente para crear nuevas experiencias digitales.

__3- Seguridad:__ pueden proporcionar una capa extra de protección contra accesos no autorizados, ya que requieren autenticación y autorización para cualquier solicitud de acceso a datos confidenciales.

__4- Rentabilidad:__ brindan acceso a herramientas e infraestructura útiles de terceros, por lo que las pueden evitar el gasto de desarrollar sistemas internos complejos.

__Tipos de API__

Dependiendo del tipo de acceso, existen *APIs públicas o abiertas* (disponibles para cualquier desarrollador, como Google Maps API), *APIs privadas* (se usan dentro de la empresa que las desarrolla, como podría ser la app interna un banco que consulta datos de clientes) y *APIs de socios* (se comparten entre empresas o desarrolladores autorizados, pero no son abiertas, siendo el caso de un proveedor de pagos como Paypal, que permite a ciertos comercios conectarse a su API).

También pueden clasificarse, según su función, en *APIs de datos* (proporcionan información), *APIs de servicios* (permiten realizar acciones como procesar pagos o enviar mensajes) y *APIs de hardware* (conectan software con hardware como impresoras o cámaras).

Por último, existen diferentes tipos dependiendo de su arquitectura, siendo los siguientes los más comunes:

__1- REST__
Es la arquitectura API más popular para la transferencia de datos a través de internet. Usa HTTP (GET, POST, PUT, DELETE) y responde normalmente en JSON.

__2- SOAP__
Acrónimo de *Simple Object Access Protocol* (Protocolo Simple de Acceso a Objetos), utiliza XML para transferir mensajes altamente estructurados entre un cliente y un servidor. Se usa frecuentemente en sistemas empresariales antiguos o que requieren alta seguridad, pero puede ser más lento que otras arquitecturas de API.

__3- GraphQL__
Lenguaje de consulta de código abierto que permite a los clientes interactuar con un único punto final de API para obtener los datos exactos que necesitan, sin encadenar múltiples solicitudes, reduciendo así el número de intercambios de datos entre el cliente y el servidor.

__4- Webhooks__
Se utilizan para implementar arquitecturas basadas en eventos. Por ejemplo, cuando ocurre un evento específico en una aplicación, como un pago, esta puede enviar una solicitud HTTP a una URL de webhook preconfigurada con los datos relevantes del evento en la carga útil de la solicitud. El sistema que recibe el webhook puede procesar el evento y tomar la acción correspondiente.

__5- gRPC__
*Remote Procedure Call* o Llamada a Procedimiento Remoto, son APIs creadas por Google. Con ellas un cliente puede llamar a un servidor como si fuera un objeto local, lo que facilita la comunicación entre aplicaciones y sistemas distribuidos.

__Buenas prácticas__

- Usar correctamente los métodos HTTP. Cada verbo debe tener su propósito claro. Aquí se encuentran los verbos más comunes (los mencionados anteriormente y alguno más):

  - GET: Obtiene datos.
  <br>
  - POST: Crea recursos.
  <br>
  - PUT: Actualiza completamente.
  <br>
  - PATCH: Actualiza parcialmente.
  <br>
  - DELETE:	Elimina.

- Usar nombres de recursos en plural es una convención muy usada en APIs REST.

  Recomendado:
```
/usuarios
/productos
/pedidos
```

- Mantener respuestas consistentes. Relacionado también con el punto anterior, todas las respuestas deberían seguir una estructura similar, como por ejemplo:
```
{
  "data": {...},
  "message": "ok",
  "status": 200
}
```
- Usar rutas claras y consistentes. Deben ser predecibles y fáciles de entender.

```
GET /usuarios
GET /usuarios/5
GET /usuarios/5/pedidos
```

- Usar códigos de estado HTTP correctos. Estos códigos son respuestas numéricas del servidor a las solicitudes del navegador, esenciales para la comunicación en la web, la experiencia de usuario y el SEO. Utilizar los códigos correctos sigue las mejores prácticas de API REST y garantiza una buena depuración. Ejemplos de códigos HTTP son:

  - 400:	Error en la petición.
  <br>
  - 401:	No autorizado.
  <br>
  - 404:	Recurso no encontrado.
  <br>
  - 500:	Error del servidor.

- Versionar la API. Las APIs cambian con el tiempo. Por eso es buena práctica incluir versión, por ejemplo:

```
/api/v1/usuarios
/api/v2/usuarios
```
- Usar paginación para listas grandes. Si una API devuelve miles de registros, se debe usar paginación, mejorando el rendimiento, la velocidad y el uso de la memoria.

- Manejo claro de errores. Es mejor explicar el motivo del error (por ejemplo ```"error":	"Recurso no encontrado."``` ).

- Autenticación y seguridad. Las APIs deben protegerse con mecanismos como Tokens, API Keys o HTTPS.

- Documentación clara. Una API sin documentación es difícil de usar. Una herramienta popular para mantener la documentación clara y accesible sería Postman.
La documentación debería explicar endpoints, parámetros,respuestas y tener ejemplos claros.


## ¿Qué es Postman?

Postman es una plataforma de desarrollo y pruebas de APIs que funciona desde su aplicación de escritorio o web, enviando peticiones HTTP y mostrando las respuestas de servidores sin necesidad de programar código.
<br>
Simplifica las solicitudes HTTP, permitiendo a los usuarios enviar, inspeccionar y automatizar llamadas a la API. Sus principales características incluyen espacios de trabajo compartidos, pruebas automatizadas y generación de documentación.

Para usar Postman primero se debe elegir el *método HTTP* (GET, POST, PUT, DELETE) según la acción que se quiera realizar, luego se escribe la *URL del endpoint de la API* y, en caso de ser necesario, se *agregan datos* en el cuerpo de la petición. Después, se *pulsa Send* para enviar la solicitud al servidor y se *revisa la respuesta* que incluye el contenido, el código de estado y el tiempo de respuesta. Finalmente, puede guardarse la petición en una *colección* para reutilizarla más adelante, lo que hace que probar y documentar APIs sea rápido, visual y organizado.

## ¿Qué es el polimorfismo?

Polimorfismo significa "muchas formas". Se refiere a la capacidad de una entidad (como una función u objeto) para realizar diferentes acciones según el contexto.

En Python, el polimorfismo es un concepto de Programación Orientada a Objetos que permite que un mismo método, función u operador se comporte de manera diferente según el objeto con el que trabaje. Esto hace que el código sea más flexible y reutilizable. Este principio fundamental de la programación orientada a objetos hace que el código sea más modular, extensible y fácil de mantener.

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

El uso del polimorfismo tiene beneficios como una mayor
flexibilidad (pueden usarse distintas clases de manera uniforme), un código más limpio (evitando condicionales largos)y su reutilización (funciones y métodos pueden trabajar con distintos tipos de objetos).

## ¿Qué es un método dunder?

Un método dunder es un método especial de una clase cuyo nombre empieza y termina con doble guion bajo (__dunder__ viene de *“double underscore”* o __ ).
Se pueden usar para personalizar el comportamiento de operaciones como ```+, -, *, **, ==``` y en estructuras de datos personalizadas, inicializar y eliminar objetos, obtener su representación en cadena, habilitar la indexación de objetos y mucho más. Estos métodos son invocados automáticamente por Python en ciertas situaciones y permiten personalizar el comportamiento de los objetos sin tener que llamar al método explícitamente.
<br>
Entre los motivos más comunes para usar los métodos dunder se encuentran el de automatizar acciones al crear, comparar o eliminar objetos y hacer que las clases se integren mejor con Python y sean más “naturales” de usar.

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
