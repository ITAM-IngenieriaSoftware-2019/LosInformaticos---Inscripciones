# Los Informáticos - Inscripciones ITAM

# Software Requirement Specification for Inscripciones ITAM
Preparado por:
* Luciano Montes de Oca Villa
* Emilio Alfonso Venancio Landeros
* Andoni Wadgymar Iñiguez

# Tabla de Contenidos

## 1. Introducción
i. Propósito
ii. Convenciones del Documento
iii. Audiencia prevista y sugerencias de lectura
iv. Alcance del producto
v. Referencias

## 2. Descripción General
i. Perspectiva del producto
ii. Funcionalidad del producto
iii. Clases de usuario y características
iv. Ambiente de operación
v. Limitaciones de diseño e implementación
vi. Documentación del usuario
vii. Supuestos y dependencias

## 3. 
i. Interfaz de Usuario
ii. Interfaz de Hardware
iii. Interfaz de Software
iv. Interfaz de Comunicaciones

## 4. Requerimientos Funcionales
i. Entrar al sistema con correo y contraseña del usuario 
ii. Inscribir Materia
iii. Baja de Materias

## 5. Requerimientos No Funcionales
i. Requerimientos de rendimiento
ii. Requerimientos de seguridad
iii. Requerimientos de fiabilidad
iv. Atributos de Calidad de Software
v. Reglas del Negocio

## Equipo Los Informáticos
Creado el 4 de Octubre de 2019

## 1. Introducción

### 1.1 Propósito
El propósito de este proyecto es crear un sistema que le permita a los alumnos del Instituto Tecnológico Autónomo de México (ITAM) realizar el proceso de inscripción de sus materias, con el objetivo de mejorar el sistema ya existente de inscripciones (Grace ITAM). 

### 1.2 Convenciones del Documento
Las prioridades elegidas para los requerimientos funcionales se eligieron de acuerdo a cómo se encuentran relacionadas unas con otras.

Asimismo cada requisito tiene su propia prioridad y consideramos que todas las prioridades son altas por el hecho de que sin uno de esos requisitos el sistema no estaría completo y no funcionará adecuada y correctamente.

Por otro lado, para la realización del presente documento utilizamos lenguaje Markdown.

Para las estimaciones, decidimos tomar como referencia las dificultades del videojuego Halo, las cuales se definen de la siguiente forma: Fácil (Mini), Normal (Medium), Heroico (Maxi) y Legendario (Giant).

### 1.3 Audiencia prevista y sugerencias de lectura
La audiencia que tenemos provista para la lectura de este documento son los desarroladores y programadores de software. Para realizar una buena lectura del proyecto, es recomendable leer en el orden en cómo se van presentando cada una de las secciones. De igual manera, si el lector tuviese dudas con respecto a la comprensión de los contenidos del documentos, puede visitar las referencias abajo citadas.

Finalmente, el documento se divide en las siguientes secciones: Introducción, Descripción General, Requisitos de Interfaz Externa, System Features, y Otros Requisitos No Funcionales.


### 1.4 Alcance del producto
El beneficio de este sistema es que permitirá un fácil y sencillo proceso de inscripción para los alumnos, tomando en cuenta que muchos alumnos se inscriben en horarios iguales y checando que no falle al momento de inscribirse. La meta del sistema es que los alumnos no tengan dificultad para inscribir materias y que las ventanas del sistema sean agradables y de fácil uso para los usuarios.

### 1.5 Referencias
Wiegers, K. (1999). Software Requirements Specification. Recuperado el 25 de Octubre de 2019, de https://drive.google.com/file/d/15UdWMiunZWb1OsIafbTSl1qdl2_EUgeH/view


## 2. Descripción general

### 2.1 Perspectiva del producto
Este producto pretende reemplazar al actual sistema de inscripciones con el que el ITAM cuenta. Se utilizaran las bases de datos existentes, por lo que solamente la capa de presentación y de la lógica de negocios cambiará.

### 2.2 Funcionalidad del producto

- Inicio de sesión para alumnos y personal administrativo
- Listado de los grupos abiertos y listas de espera existentes
- Inscribirse a grupos y listas de espera
- Darse de baja de grupos y listas de espera
- Ver resultados de lista de espera
- Crear y modificar comentarios para la lista de espera
- Listar los grupos en los que estoy inscrito (Tira de materias)
- Mostrar el horario detallado

### 2.3 Clases de usuario y características
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

### 2.4 Ambiente de operación
El sistema actual es alojado en in servidor de Windows con un Microsoft SQL server para la base de datos por lo que reutilizaremos el equipo existente

### 2.5 Limitaciones de diseño e implementación
Debido a que no se tiene acceso a el servidor en el que se va a montar la fase de pruebas puede ser complicada. Tampoco se tiene acceso a la base de datos con los alumnos, salones, profesores, etc por políticas de la institución.

El ITAM será el encargado de verificar el funcionamiento de la aplicación con sus bases de datos y del mantenimiento posterior de la aplicación

### 2.6 Documentación del usuario
El usuario contará con un manual para las inscripciones, los administrativos con un manual para dar de alta grupos, salones y alumnos. También algunos administrativos tienen un manual para aprobar las listas de espera

### 2.7 Supuestos y dependencias
El proyecto depende enteramente del funcionamiento de las bases de datos existentes y del correcto acoplamiento del servidor de bases de datos con la nueva aplicación

## 4. Funcionalidades del Sistema

### 4.1 Entrar al sistema con correo y contraseña del usuario 

#### Descripción y prioridad
Pantalla de login para el usuario del sistema de inscripciones.
En esta pantalla el usuario puede ingresar los datos necesarios para ingresar al sistema.
Esta nueva funcionalidad tiene alta prioridad.

#### Secuencias de respuesta
* Si el usuario inserta una combinación de nombre de usuario y contraseña correctos, se le redirigirá a los menús
* Si el usuario inserta una combinación de nombre de usuario y contraseña incorrectos, mostrar un mensaje acorde. Eg. "Usuario/Contraseña incorrectos"
* Si el usuario no recuerda su contraseña, hará clic una etiqueta que lo redirigirá a una pantalla de recuperación de usuario/contraseña

#### Requerimientos funcionalidades
1. Los usuarios con que cuentan con su correo del ITAM y su contraseña deben de poder entrar al sistema.
i. La pantalla de inicio cuenta con dos campos para ingresar texto (nombre de usuario y contraseña), un botón para validar los campos ingresados
2. La pantalla de inicio debe de contar con una etiqueta para redirigir a otra pantalla de recuperación de contraseña
i. La funcionalidad de esta pantalla de recuperación de contraseña todavía esta por ser decidida
3. Cuando un usuario no cuenta con un nombre y contraseña correctos el sistema debe de mostrar un mensaje acorde, en donde se indique que el error es debido a que la combinación no fue correcta.

### 4.2 Inscribir Materia

#### Descripción y prioridad
Esta función permitirá que el usuario (alumno) inscriba sus materias en el semestre y período correspondiente. La prioridad de esto es muy alta.

#### Secuencias de respuesta
* Si el usuario intenta inscribir sus materias en un horario diferente al que se le asignó en el sorteo, el sistema no le permitirá realizar la inscripción
* Si el usuario no cumple con los prerrequisitos necesarios para inscribir alguna materia, el sistema mostrará un mensaje de error y no permitirá inscribir dicha materia
* Si el usuario intenta inscribir dos materias en un mismo horario, el sistema arrojará un mensaje de error indicando que hay dos clases que se empalman

#### Requerimientos funcionales
Req-1: Pantalla de selección de período
Req-2: Pantalla de error
Req-3: Pantalla de búsqueda avanzada
Req-4: Pantalla de Visualización del horario
Req-5: Pantalla de búsqueda por departamentos

### 4.3 Baja de Materias

#### Descripción y prioridad
El usuario tiene la opción de dar materias de baja pero para que esto sea posible primero es necesario tener materias inscritas. Este proceso se puede hacer después de haber inscrito una materia y que por cualquier razón necesite ser modificada para el beneficio del usuario. La prioridad de esta acción es alta ya que el costo de no poder dar de baja una materia involucraría decisiones finales en cada movimiento de la inscripción y le daría menos libertad a los usuarios por poder tener un margen de error de 0%.

#### Secuencias de respuesta
* Si el usuario requiere dar de baja una materia sin tener ni una sola inscrita el sistema arrojara un mensaje de error por no contar con materias inscritas.
* Si el usuario requiere dar de baja una materia que no tiene inscrita el sistema arrojara error por no tener esa materia inscrita
* Si el usuario proporciona el número de matricula incorrecto el sistema arrojara error por que no existe ninguna materia con esa matricula.

#### Requerimientos funcionales
1. Para que el usuario pueda hacer la función de Baja de Materias requiere tener un correo y una contraseña para poder ingresar al sistema.
2. Es necesario que el usuario haya inscrito materias este semestre para que de esta forma pueda dar de baja cualquiera de las ya inscritas
3. Proporcionar la matricula adecuada de la materia que se quiera dar de baja
