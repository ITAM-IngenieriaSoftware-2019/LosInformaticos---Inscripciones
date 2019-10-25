# Los Informáticos - Inscripciones

## Descripción general

### Perspectiva del producto

### Funcionalidad del producto

### Clases de usuario y características

### Ambiente de operación

### Limitaciones de diseño e implementación

### Documentación del usuario

### Supuestos y dependencias

//Parte 3

## External Interface Requirement

### User Interfaces
"Los interfaces entre el usuario y el software son de gran importancia ya que un mal interface puede llegar a confundir al usuario y no darle la accesibilidad de lograr las acciones que desea realizar" 

**Interface 1**

El usuaurio se encuentra en la pantalla de log in en donde debería ingresar su correo del ITAM al igual que la contraseña que tiene asignada o que el especifico. En el caso en el que el usuario tenga alguno de los dos datos incorrectos sera marcado el error con letras rojas y tendra la oportunidad de volverlo a intentar. Si el usuario no recuerda la contraseña que asigno tendra la opción de asignar una nueva en otra pestaña, que sería la *segunda interface*. Si el usuario entra los datos de forma correcta sera mandado al *interface 3* 

**Interface 2**

El usuario se encuentra en el interface donde puede asignar una nueva contraseña. Primero debe mandar un correo a otra cuenta de correo electrónico en donde tendra el link para asignar una nueva contraseña. Una vez hecho esto el usuario deberá crear una nueva contraseña con las características que se requieran y cuando esto se cumpla el sistema cambiara la contraseña. El usuario será redigirido a la *primera interfaz* en donde podra acceder con su nueva contraseña.

**Interface 3**

El usuario entrara a la pagina donde podra dar de alta y baja materias. El interface cuenta con botones para buscar materias, que redirige a la *interface 4*, dar de alta una materia con su matrícula, dar de baja una materia con su matrículo y por ultimo guardar los cambios y/o salir. Si el usuario realiza una acción que no concuerde con el sistema se mandara un mensaje rojo de error junto con la descripción del problema. En el momento de dar de alta o baja una materia y guardar los cambios, si se hace de la forma correcta, el interface mandara un mensaje con la palabra éxito y la acción que se hizo de la forma correcta.

**Interface 4** 

Esta interface sirve para que el usuario pueda revisar las clases que están disponibles para poder meter en su horario y si van con su plan de estudio al igual que las principales caracteriísticas de la materia. Si el usuario coincide con la materia y esta de acuerdo puede copiar la matrícula y/o agregar directamente desde esta interface. Esta interface muestra sugerencias, errores y caracteristicas relacionadas sobre el usuario y su plan de estudios.
