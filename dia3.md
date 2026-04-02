# Da 2 - 31 de marzo de 2026 

==========================================================================================================
# Comandos Linux aprendidos hoy:
Concatenar Comandos: Escribir varios comandos en una sola linea.
    - Uso de ";" para ejecutar varios comandos en una sola linea, es como escribir un comando y luego otro sin necesidad de esperar a que el primero termine para escribir el
      segundo, se ejecutan ambos al mismo tiempo, por ejemplo: "whoami ; ls" ejecuta ambos comandos uno tras otro sin importar el resultado del primero   

    - Uso de "&&" para ejecutar varios comandos en una sola linea pero solo si el comando anterior tuvo exito, es como escribir un comando y luego otro pero el segundo solo se
      ejecuta si el primero se ejecuta correctamente, por ejemplo: "whoami && ls" ejecuta ambos comandos uno tras otro pero el segundo solo se ejecuta si el primero se ejecuta correctamente,
      si son 3 comandos por ejemplo "whoami && ls && pwd" el segundo comando se ejecuta solo si el primero se ejecuta correctamente y el tercero solo si el segundo se ejecuta correctamente, 
      es como una cadena de comandos que dependen del resultado del anterior

    - Uso de "||" para ejecutar varios comandos en una sola linea pero solo si el comando anterior tuvo error, es como escribir un comando y luego otro pero el segundo solo se
      ejecuta si el primero tuvo un error al ejecutarse, por ejemplo: "whoami || ls" ejecuta ambos comandos uno tras otro pero el segundo solo se ejecuta si el primero tuvo un error al ejecutarse,
      si son 3 comandos por ejemplo "whoami || ls || pwd" el segundo comando se ejecuta solo si el primero tuvo un error al ejecutarse y el tercero solo si el segundo tuvo un error al ejecutarse, 
      es como una cadena de comandos que dependen del resultado del anterior pero en este caso dependen de que el anterior tenga un error al ejecutarse

echo $? : muestra el resultado del ultimo comando ejecutado, si el resultado es 0 significa que el comando se ejecuto correctamente, 
          si es diferente de 0 significa que hubo un error al ejecutar el comando, es como una forma de verificar si un comando se ejecuto correctamente o no

touch: comando para crear un archivo vacio o actualizar la fecha de modificacion de un archivo existente, por ejemplo: "touch archivo.txt" crea un archivo llamado "archivo.txt"
       si no existe o actualiza la fecha de modificacion si ya existe, OJO (funcioanan mas para archivos de texto plano)

echo "texto" > archivo.txt : comando para escribir texto en un archivo, si el archivo no existe lo crea, si el archivo existe lo sobreescribe
  ----> por ejemplo: (echo "Hola Mundo" > archivo.txt) escribe "Hola Mundo" en el archivo archivo.txt
  ----> Apilar texto (echo "Adios Mundo" >> archivo.txt) escribe "Adios Mundo" en el archivo archivo.txt pero sin borrar el texto anterior

rm : Sirve para eliminar archivos o directorios 
  ----> por ejemplo: "rm archivo.txt" elimina el archivo llamado "archivo.txt"
    - rm -r nombre_directorio : Elimina un directorio y su contenido
    - rm -r * : Elimina todos los archivos y directorios del directorio actual, OJO solo borra el contenido y te pedira confirmacion para eliminar todo
    - rm -r * .[^.]* : Hace lo mismo que el anterior pero tambien elimina los archivos ocultos 
    - PELIGROSO: rm -rf * : Elimina todos los archivos y directorios del directorio actual sin pedir confirmacion, OJO este comando es muy peligroso ya que 
                            puede eliminar todo el contenido de tu directorio actual
    - PELIGROSO: nuca borrar los archivos "./" ni "../" del sistema si lo ejecutas en el directorio raiz "/" ni del direcotio actual ya que lo borra el 
                 directorio actual y al padre del directorio actual 

nano "nombre_archivo" : abre el editor de texto nano y crear o edita un archivo con el nombre especificado, 
  ----> por ejemplo: "nano archivo.txt" abre el editor de texto nano y crea un archivo llamado "archivo.txt"
    - (ctrl + o) : guarda el archivo en nano
    - (ctrl + x) : cierra el editor de texto nano

vi "nombre_archivo" : abre el editor de texto vi y crear o edita un archivo con el nombre especificado, 
  ----> por ejemplo: "vi archivo.txt" abre el editor de texto vi y crea un archivo llamado "archivo.txt"
    - (i) : para entrar en modo de insercion y poder escribir en el archivo
    - (esc) : para salir del modo de insercion y volver al modo normal
    - (shift + :) : para entrar en modo de comandos y poder ejecutar comandos como guardar o salir del editor de texto vi
            - (w) : para guardar el archivo en vi
            - (q) : para salir del editor de texto vi
            - (wq) : para guardar el archivo y salir del editor de texto vi


==========================================================================================================
# Comandos Atajos de Teclado:



==========================================================================================================
# Terminos nuevos:


==========================================================================================================
# Dificultades del dia: 

==========================================================================================================
# Lo que aprendi que no esperaba:
