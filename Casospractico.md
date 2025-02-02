# Enunciado

Acabamos de terminar el CFGS ASIR y encontramos trabajo en la empresa **Servicios Web RC, SA** en Huelva. Anteriormente utilizaban **Apache** como servidor web y quieren migrar a **Nginx**. Una vez instalado y configurado, procedemos a realizar todos los casos prácticos solicitados.



## A) Versión de Nginx instalado

Para ver la versión de **Nginx**, hay que ejecutar el comando correspondiente.

![version](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/version%20nginx.png)

## B) Servicio asociado

Para verificar que **Nginx** está configurado correctamente y en ejecución.
![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/servicio%20nginx.png)
### Nota:
Otros comandos para gestionar el servicio son:

- Iniciar el servicio  `start`
- Detener el servicio  `stop`
- Reiniciar el servicio  `restart`



## C) Inspeccionar los ficheros de configuración

El directorio de **Nginx** está situado en `/etc/nginx`.  
![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/configuracion%20nginx.png)

Su archivo de configuración es `nginx.conf`.    
![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/nginx.conf.png)


## D) Modificación de la página web

Para modificar la página predeterminada de **Nginx**, hay que editar el archivo correspondiente.  
![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/D-paginaweb.png)



## E) Virtual Hosting

El servidor poseerá **dos sitios web**. Para ello, hay que seguir los siguientes pasos:

1. **Creación de los directorios**  
  ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/directorios.png)
3. **Concesión de permisos para los directorios**
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/permisos.png) 
5. **Creación de los archivos `index.html` para cada sitio web**
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/index-web1.png)
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/index-web2.png)
8. **Creación de los archivos en `sites-available`**
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/sites-web1.png)
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/sites-web2.png)
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/e-creacionsites.png)
11. **Configuración del archivo `hosts`**  
    ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/e-configuracion-archiv.png)
13. **Reiniciar el servicio para aplicar los cambios y comprobamos el resultado**
  ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/e-resultado.png)



## F) Autenticación, autorización y control de acceso

- **La web1 puede acceder desde la red externa e interna.**  
- **La web2 solo puede accederse desde la red interna.**
 

Para conseguir esto, se deben realizar los siguientes pasos:

1. Modificar los archivos en `sites-available`.
  ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/f-modificar-web1-2.png) 
3. Modificar el archivo `hosts` con las IPs permitidas para cada red.
  ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/f-modificacion.png)  
4. Comprobación de la red interna.
  ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/f-curl-1.png)
  ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/f-curl-web2.png)   
6. Comprobación de la red externa.
![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/f-comprobacion.png)  



## G) Autenticación, autorización y control de acceso  


- **web1.org** contiene un directorio privado al que **solo pueden acceder usuarios válidos**.  

Pasos a seguir:

1. Modificar nuevamente los archivos en `sites-available`.
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/g-1.png)
3. Comprobar que `web1.org/privado` requiere autenticación.
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/g-pedircontrasena.png)  
5. Verificar que los usuarios autorizados pueden acceder.
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/g-acceso.png)  



## H) Autenticación, autorización y control de acceso

- **El directorio privado en web1 solo requiere autenticación desde la red externa.**  
- **Desde la red interna no pide credenciales.**  

Pasos a seguir:

1. Modificar nuevamente los archivos en `sites-available`.
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/H-autenticacion.png)  

## I) Seguridad

Para configurar un acceso seguro en **web1**, se deben realizar los siguientes pasos:

1. **Generar una clave privada y un certificado SSL.**
 ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/f-seguridad-1.png)  
3. **Modificar nuevamente los archivos en `sites-available` para aplicar la configuración HTTPS.**
   ![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/f-seguridad-2.png)   

