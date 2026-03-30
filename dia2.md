Da 1 - 29 de marzo de 2026

==========================================================================================================
Comandos Linux aprendidos hoy:

whoami : ver usuario actual
id : muestra a que grupo estamos
sudo su : te convierte en el usuario con mas privilegios "root" , solo sirve si estas en el grupo (sudo) y si sabes tu contraseña de usuario, si no eres un impostor jejeje xd
 - sudo (comando) : para ejecutar un comando con privilegio de root sin tener que convertirte en root
exit : para salir de la sesion actual en la que estas por ejemplo para salir del usuario root a tu usario normal
cat /etc/group : te muetra todos los grupos del sistema
 - ejemplo    ---->   sudo:x:27:usuario1,usuario2
    - Grupo: sudo
    - GID(ID del grupo): 27
    - Usuarios dentro: usuario1, usuario2
which (comando) : Te dice la ruta exacta del ejecutable que se va a usar cuando escribes ese comando, util para saber si la herramienta esta disponible antes de usarla
command -v (comando) : Hace lo mismo que "which" en caso de que no exista
pwd : muestra la ruta absoluta en el directorio actual que te encuentras
ls : lista todo los archivos de la carpeta o directorio que estes ahora
 - ls -la :lista todo con detalles y incluso los archivos acultos, si no quieres los ocultos escribe "ls -l"
cd : cambiar de carpeta o directorio mediante ruta absoluta o relativa
 - cd .. : subir un nivel en jeraquia del directorio, es decir al directorio padre, es como retroceder basicamente al directorio anterior de la jerarquia
 - cd ~ : cambia al directorio de incio del usuario actual. osea "/home/usuarioactual" o tambien puedes hacer solo "cd".
 - cd - : cambia al directorio ultimo que ingresaste, no importa si su ubicacion es muy disitnta, es como un cambio de A a B y B a A si lo haces de nuevo

==========================================================================================================
Comandos Atajos de Teclado:

Control + l : limpia la pantalla sin borrar la linea de comando que estas escribiendo

==========================================================================================================
Terminos nuevos:

input: termino para referirse a cualquier dato que se le proporciona a un programa para que lo procese.
 - stdin: es el canal por el cual un programa recibe datos de entrada, ya sea desde el teclado, un archivo o la salida de otro comando
          cuando se refiere a salida se puede hacer con el pipe "|" osea la salida del comando1 en la entrada del comando2 -> " comando1 | comando2 "
ouput: termino general para cualquier salida de un programa, es comun que se refiera a "stdout" pero tambien puede ser "stderr"
 - stdout: se refiere a la salida estandar de un programa o comando (el resultado que sale)
 - stderr: "       "      "     " de un ERROR al ejecutar un comando (el resultado que sale)


==========================================================================================================
Dificultades del dia: 
No saber como comenzar y ser muy procrastinador, soy el tipico metodo de si o si necesito leer un guia 
o tener un plan de pasos a pasos, justo me encontre video de S4vitar y me resulto bien, osea hay cosas detalladas al 
principio que no entendi pero lo esencial de los comandos y otras cosas relacionada a esos comandos si fue util
==========================================================================================================

Lo que aprendi que no esperaba:
que tendria que investigar y aprender terminos nuevos para entender su explicacion, y eso para alguien como yo que no
sabe nada y es mucho de enrollarse en eso es un fastidio literal 10 minutos para buscar y entender terminos de palabras nuevas