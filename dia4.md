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

 



==========================================================================================================
# Comandos Atajos de Teclado:



==========================================================================================================
# Terminos nuevos:


==========================================================================================================
# Dificultades del dia: 

==========================================================================================================
# Lo que aprendi que no esperaba:
