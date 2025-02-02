# Configuración del Esquema de Red  

## Descripción del Esquema  

El servidor está configurado con **dos tarjetas de red**:  

- **enp0s3**: Adaptador en **puente**.  
- **enp0s8**: Configurada en **red interna**.    

![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/esquema-red0.png) 
![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/esquema-red1.png)  
![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/esquema-red2.png)

---

## Configuración de las Redes  

Para la configuración de las redes, se debe modificar el archivo de configuración correspondiente.  

- **enp0s3**: Configurada con **DHCP**.  
- **enp0s8**: Configurada con **IP estática**.  

![servicio](https://github.com/N1tr0Zeu5/nginx/blob/main/img/nginx/netplan-setting.png)

Es necesario **aplicar los cambios** y **reiniciar el NetworkManager** para que la configuración surta efecto.  
