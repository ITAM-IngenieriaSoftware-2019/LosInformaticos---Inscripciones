# Los Informáticos - Inscripciones

# Software Requirement Specification for Incripciones
Preparado por:
* Luciano Montes de Oca Villa
* Emilio Alfonso Venancio Landeros
* Andoni Wadgymar Iñiguez

## Equipo Los Informáticos
ITAM
Creado el 4 de Octubre de 2019

## Introducción

### Propósito
El propósito de este proyecto es crear un sistema que le permita a los alumnos del Instituto Tecnológico Autónomo de México (ITAM) realizar el proceso de inscripción de sus materias, con el objetivo de mejorar el sistema ya existente de inscripciones (Grace ITAM). 

### Convenciones del Documento
Las prioridades elegidas para los requerimientos funcionales se eligieron de acuerdo a cómo se encuentran relacionadas unas con otras.

Asimismo cada requisito tiene su propia prioridad y consideramos que todas las prioridades son altas por el hecho de que sin uno de esos requisitos el sistema no estaría completo y no funcionará adecuada y correctamente.

Por otro lado, para la realización del presente documento utilizamos lenguaje Markdown.

Para las estimaciones, decidimos tomar como referencia las dificultades del videojuego Halo, las cuales se definen de la siguiente forma: Fácil (Mini), Normal (Medium), Heroico (Maxi) y Legendario (Giant).

### Audiencia prevista y sugerencias de lectura
La audiencia que tenemos provista para la lectura de este documento son los desarroladores y programadores de software. Para realizar una buena lectura del proyecto, es recomendable leer en el orden en cómo se van presentando cada una de las secciones. De igual manera, si el lector tuviese dudas con respecto a la comprensión de los contenidos del documentos, puede visitar las referencias abajo citadas.

Finalmente, el documento se divide en las siguientes secciones: Introducción, Descripción General, Requisitos de Interfaz Externa, System Features, y Otros Requisitos No Funcionales.


### Alcance del producto
El beneficio de este sistema es que permitirá un fácil y sencillo proceso de inscripción para los alumnos, tomando en cuenta que muchos alumnos se inscriben en horarios iguales y checando que no falle al momento de inscribirse. La meta del sistema es que los alumnos no tengan dificultad para inscribir materias y que las ventanas del sistema sean agradables y de fácil uso para los usuarios.

### Referencias
Wiegers, K. (1999). Software Requirements Specification. Recuperado el 25 de Octubre de 2019, de https://drive.google.com/file/d/15UdWMiunZWb1OsIafbTSl1qdl2_EUgeH/view


## Descripción general

### Perspectiva del producto
Este producto pretende reemplazar al actual sistema de inscripciones con el que el ITAM cuenta. Se utilizaran las bases de datos existentes, por lo que solamente la capa de presentación y de la lógica de negocios cambiará.

### Funcionalidad del producto

- Inicio de sesión para alumnos y personal administrativo
- Listado de los grupos abiertos y listas de espera existentes
- Inscribirse a grupos y listas de espera
- Darse de baja de grupos y listas de espera
- Ver resultados de lista de espera
- Crear y modificar comentarios para la lista de espera
- Listar los grupos en los que estoy inscrito (Tira de materias)
- Mostrar el horario detallado

### Clases de usuario y características
Se deben de definir las siguientes clases:

1. Grupo
    - Clave de la materia
    - Nombre de la materia
    - Horario de clase
    - Salón asignado (Este parámetro también determina el número de lugares disponibles en el grupo)
    - Lista de alumnos inscritos
    - Docente asignado
1. Lista de espera (Hereda a grupo)
    - Lista de alumnos en la lista de espera
1. Profesor
    - Nombre
    - Clave única
1. Alumno
    - Nombre
    - Clave única
    - Plan de estudios
    - Semestre (nominal y por materias)
    - Permisos y bloqueos de dirección escolar
    - Lista de grupos en los que el alumno esta inscrito
    - Lista de listas de espera en las que el alumno esta inscrito
1. Administrativo
    - Nombre
    - Clave única
    - Departamento al que pertenece
1. Salón
    - Nombre
    - Capacidad máxima

Un grupo puede ser lista de espera si esta próximo a completarse (5 espacios restantes).

### Ambiente de operación
El sistema actual es alojado en in servidor de Windows con un Microsoft SQL server para la base de datos por lo que reutilizaremos el equipo existente

### Limitaciones de diseño e implementación
Debido a que no se tiene acceso a el servidor en el que se va a montar la fase de pruebas puede ser complicada. Tampoco se tiene acceso a la base de datos con los alumnos, salones, profesores, etc por políticas de la institución.

El ITAM será el encargado de verificar el funcionamiento de la aplicación con sus bases de datos y del mantenimiento posterior de la aplicación

### Documentación del usuario
El usuario contará con un manual para las inscripciones, los administrativos con un manual para dar de alta grupos, salones y alumnos. También algunos administrativos tienen un manual para aprobar las listas de espera

### Supuestos y dependencias
El proyecto depende enteramente del funcionamiento de las bases de datos existentes y del correcto acoplamiento del servidor de bases de datos con la nueva aplicación

## Descripción y prioridad
Pantalla de _login_ para el usuario del sistema de inscripciones.
Esta nueva funcionalidad tiene alta prioridad.

## Secuencias de respuesta
- Si el usuario inserta una combinación de nombre de usuario y contraseña correctos, se le redirigirá a los menús
- Si el usuario inserta una combinación de nombre de usuario y contraseña incorrectos, mostrar un mensaje acorde. Eg. "Usuario/Contraseña incorrectos"
- Si el usuario no recuerda su contraseña, hará clic una etiqueta que lo redirigirá a una pantalla de recuperación de usuario/contraseña

## Requerimientos funcionalidades
1. Los usuarios con que cuentan con su correo del ITAM y su contraseña deben de poder entrar al sistema.
    1. La pantalla de inicio cuenta con dos campos para ingresar texto (nombre de usuario y contraseña), un boton para validar los campos ingresados
