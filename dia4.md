# Da 3 - 2 de abril de 2026 

==========================================================================================================
# Comandos Linux aprendidos hoy:

Lecturra de Permisos: Para ver los permisos de un archivo o directorio se puede usar el comando "ls -l"
---------------------------------------------------------------------------------------------------------------
  Dato : El superUsuario Root puede ignorar los permisos y hacerlo TODO, es un Dios en pocas palabras, jajaj xd

  EJEMPLO:   drwxrwxr-x  2 kali kali 4096 Mar 26 22:46 videos_comprometedoras 
    -    propietario: kali
    -    grupo: kali
    -    otros: se refiere a todos los demas usuarios pero no aparece xq se sobreentiende         

 - En Archivos: el primer caracter indica el tipo de archivo, si es un "-" 
    ---> r : permiso de lectura, permite leer el contenido del archivo 
    ---> w : permiso de escritura, permite modificar el contenido del archivo 
    ---> x : permiso de ejecucion, permite ejecutar el archivo 
    ---> - : sin permiso, no permite realizar ninguna accion sobre el archivo o directorio

  - En Directorios: el primer caracter es una "d" que indica que es un directorio, los permisos de lectura, escritura y ejecucion tienen un significado diferente al de los archivos, 
    ---> r : permiso de lectura, permite listar el contenido del directorio 
    ---> w : permiso de escritura, permite crear, eliminar o renombrar archivos dentro del directorio 
    ---> x : permiso de ejecucion, permite acceder al directorio y ejecutar comandos dentro del directorio 
    ---> - : sin permiso, no permite realizar ninguna accion sobre el directorio
    ojo: cosas permisos como
        - (drw-) : permite leer y supuestamente escribir pero no ejecutar, ahora para escribir osea editar (borrar o crear archivos o direcorios dentro del directorio padre no se puede
                   porque primero se tiene que ingresar al directorio, asi que no sirve, "rw-" o "-w-" no sirve para nada en editar, existe solo por funcion no por logica, si o si es 
                   necesario el permiso de "x" para poder escribir dentro del directorio)  
        - (dr-x) : permite listar el contenido y acceder al directorio y ejecutar comandos dentro del directorio pero no crear, eliminar o renombrar archivos dentro del directorio
                   pero si los archivos o subdirecotiros dentro tienen "rwx" ellos si si pueden hacer todo normal pero no se pueden borrar a si mismos 


mkdir: sirve para crear directorios
    ejemplo: 
     - mkdir (nombre_directorio) : crea un direcotiro con el nombre "nombre_directorio"
     - mkdir (nombre_A) (nombre_B) (nombre_C) : crea 3 directorios con nombres A,B y C 

Asignacion de Permisos:
-----------------------------------------
  Dato: Solo el Root y el Propietario pueden cambiar los permisos, no importa si todo esta --- --- --- kali kali   , OJO(Root ignora eso es un Diossss!!)

  - Notacion Simbolica:
       - u : Usuario(Propietario)                  - "+" : agregar permiso
       - g : grupo                                 - "-" : quitar permiso
       - o : otros                                 - "=" : establecer permiso, osea defina de una
       - a : Todos(usuario,grupo,otros)

chmod : Permite cambiar los permisos de acceso a archivos y directorios
    --->  Ejemplo: drwxrwxr-x 2 kali kali 4096 Apr  3 23:09 nombreA
            - (chmod g-w nombreA) : quita el permiso de escritura a el grupo ===>   drwxr-xr-x 2 kali kali 4096 Apr  3 23:09 nombreA
            - (chmod u-wx,g-rx,o-r,o+w nombreA) : quita permiso de ejecucion y escritura a usuario(propietario) ===>   dr---w--wx 2 kali kali 4096 Apr  3 23:09 nombreA
                                                : quita permiso de lectura y ejecucion a grupo     
                                                : quita permiso de lectura y agrega escritura a otros
            - (chmod a=rx nombreA) : todos tiene solo lectura y ejecucion ===>   dr-xr-xr-x 2 kali kali 4096 Apr  3 23:09 nombreA
            - (chmod u=x nombreA)  : el usuario(propietario) solo puede ejecutar ===>   d--xrwxr-x 2 kali kali 4096 Apr  3 23:09 nombreA  


chgrp : Permite cambiar el grupo a archivos o directorios, OJO (solo si eres Propietario y perteneces al grupo nuevo que va a reemplazar al viejo)
    --->  Ejemplo: drwxrwxr-x 2 root root 4096 Apr  3 23:09 nombreA
            - (chgrp kali nombreA) : cambia el grupo root por el grupo kali ===>   drwxr-xr-x 2 root kali 4096 Apr  3 23:09 nombreA      


useradd: Sirve para crear un nuevo Usuario en el Sistema    OJO(solo lo puede hacer el root y los que puedan usar "sudo")
      ejemplo:
        - (useradd Persi) : crea el usuario Persi (por defecto sin contraseña)
        Dato Rpido : puedes crear el usuario con especificaciones para hacerlo mas rapido
        - (useradd Persi -s /bin/bash -d /home/Persi)
            -> "-s" : especifica el SHELL de inicio de sesion del Usuario (en este caso /bin/bash)
            -> "-d" : especifica el directorio personal del Usuario (en este caso /home/Persi)    ==> "yo ya cree el directorio "Persi" dentro de home
                      --> en caso de no existir el directorio que quieras asignar, lo puedes crear ahi mismo con "-m"
                      --> EJEMPLO (useradd Persi -s /bin/bash -d /home/Persi -m)  
            

passwd : Se utiliza para cambiar la contraseña de un Usuario o del actual
        ejemplo:
          - (passwd) : sirve solo para cambiar o crear la contraseña del usuario actual, te pedira una vez confirmar la contraseña nueva
          - (passwd Persi) : crea una contraseña (si no tiene) o cambia la contraseña del usuario "Persi", en este caso si estas en Root
          - (sudo passwd Persi) : lo mismo pero para quienes tengan el privilegio de sudo 


chown : Sirve para cambiar el Usuario(Propietario) de un archivo o directorio    ...OJO(solo lo puede hacer el root y los que puedan usar "sudo")
        ejemplo: drwxrwxr-x 2 root root 4096 Apr  3 23:09 nombreA
          - (chown Persi nombreA) : cambia el usuario root por el usuario Persi ===>   drwxr-xr-x 2 Persi root 4096 Apr  3 23:09 nombreA
          Dato Rpido : si no quieres hacer chgrp para cambiar de grupo y luego usar chown para cambiar usuario, puede usar "chown" para hacerlo junto
          - (chown Persi:kali nombreA) : establece como propietario a "Persi" y a grupo "kali" ===>   drwxr-xr-x 2 Persi kali 4096 Apr  3 23:09 nombreA  


groupadd : Crea grupos de Usuarios        ...OJO(solo lo puede hacer el root y los que puedan usar "sudo")
          ejemplo --> (groupadd Alumnos) : crea un grupo vacio con el nombre "Alumnos"

usermod : Modifica los atributos de un usuario existente en el sistema    ...OJO(solo lo puede hacer el root y los que puedan usar "sudo")
          puede cambiar (grupos,directorio home, shell, nombre de usuario, UID) en este caso mostrare las 4 primeras
          + Para Asignar un Usuario a un grupo   
             Ejemplo (usermod -a -G Alumnos Persi) : Se añadio el Usuario Persi al grupo Alumnos
                 - "-a" : para añadir un usuario(Persi) a un grupo sin eliminarlo de otros grupos al que ya pertenece [funciona solo en combiancion con "-G"]
                 - "-G" : para especificar una lista de grupos(Alumnos) adicionales al que se añadira el Usuario(Persi) [sin "-a", se borra el usuario de otros grupos, 
                          menos este nuevo que se añadio]
          + Para cambiar la shell del Usuario : (usermod -s /bin/bash Persi)
          + Para cambiar el directorio Personal : (usermod -d /home/nuevo Persi)   
          + Para cambiar el nombre al Usuario : (usermod -l nuevoNombre Persi)     

 



==========================================================================================================
# Cosas nuevas que Aprendi:

cat /etc/passwd : es un archivo del sistema que almacena la información básica de todos los usuarios creados en el sisteam, incluyendo su identificador (UID), grupo (GID),
                  directorio personal y el intérprete de comandos (shell) que utilizan
              
              Ejemplo: (cat /etc/passwd | grep "Persi") muestra solo la informacion del Usuario Persi porque filtramos por nombre "Persi"
                  - Persi:x:1001:1001::/home/Persi:/bin/bash
                    - nombre de Usuario : Persi
                    - contraseña : x "oculta obviamente"
                    - ID : 1001
                    - GUID(Grupo) : 1001
                    - descripcion : aca no se pero esta vacion xd, es lo que deberia estar entre "::" 
                    - carpeta personal : /home/Persi
                    - shell : /bin/bash


==========================================================================================================
# Terminos nuevos:


==========================================================================================================
# Dificultades del dia: 

==========================================================================================================
# Lo que aprendi que no esperaba:
