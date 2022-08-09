# Documentación   
   
   




### **Este documento fue creado para indicar los principales problemas encontrados en el momento de la instalación de los servidores y describir la solución aplicada.**   
    
      

   
*Agregar el usuario ansible y darle permisos sin contreseña*  
> - Con un editor de texto editar el archivo /etc/sudoers.   
> - Añadir luego de la línea %sudo ALL=(ALL:ALL) ALL   
USUARIO    ALL=NOPASSWD: ALL   
> - Guardar el archivo 



*Falla e autenticación con Git al realizar pull desde controlador contra repositorio remoto*   
> - Se debió generar un token nuevo en Github y copiarlo localmente en lugar del password solicitado, de esta forma fue posible la autencticacion y se pudo realizar el pull

*Durante pruebas con playbooks accidentalmente se borro un archivo .yml en el controlador y posteriormente al realizar un pull al repo remoto se generaron inconsistencias que generaban un error y no se podia continuar. Esto fue solucionado con:*   

>  `` git reset --hard HEAD   ``   
    ``git stash   ``   
    ``git pull ``   



Agregar nombre o IP de los Hosts en inventario de Ansible para que sea accesibles   
> - Se modificó en controlador el archivo hosts ubicado en /etc/ansible y se agregaron las ip de los servidores instalados, en este caso 192.168.56.104 y 192.168.56.107.


