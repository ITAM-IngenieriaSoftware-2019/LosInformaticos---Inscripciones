# Los Informáticos - Inscripciones

## Introducción

### Propósito
El propósito de este proyecto es crear un sistema que le permita a los alumnos del Instituto Tecnológico Autónomo de México (ITAM) realizar el proceso de inscripción de sus materias en un período correspondiente.

### Convenciones del Documento
Las prioridades elegidas para los requerimientos funcionales se eligieron de acuerdo a cómo se encuentran relacionadas unas con otras. Asimismo cada requisito tiene su propia prioridad y consideramos que todas las prioridades son altas por el hecho de que sin uno de esos requisitos el sistema no estaría completo y no funcionará adecuada y correctamente.

### Audiencia prevista y sugerencias de lectura
La audiencia prevista para este proyecto son todos los alumnos que actualmente estudian en el ITAM.

### Alcance del producto
El beneficio de este sistema es que permitirá un fácil y sencillo proceso de inscripción para los alumnos, tomando en cuenta que muchos alumnos se inscriben en horarios iguales y checando que no falle al momento de inscribirse. La meta del sistema es que los alumnos no tengan dificultad para inscribir materias y que las ventanas del sistema sean agradables y de fácil uso para los usuarios.

### Referencias
http://grace.itam.mx/EDSUP/twbkwbis.P_WWWLogin
http://catarina.udlap.mx/u_dl_a/tales/documentos/lis/alvarez_m_v/capitulo4.pdf
https://medium.com/uxlatam/50-login-y-formularios-de-registro-para-inspirarse-96f9282e4c3e


## Descripción general

### Perspectiva del producto

### Funcionalidad del producto

### Clases de usuario y características

### Ambiente de operación

### Limitaciones de diseño e implementación

### Documentación del usuario

### Supuestos y dependencias


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
