# Como Bloquear el Acceso a un Archivo de un Servidor Nginx (Casos de Uso)

### Directivas de Protección de Archivos (nginx.conf)

##### Bloqueo de archivo con retorno 404 Not Found
  location = /proyecto/img/logo.png {
		deny all;
	       return 404;
	    }

##### Bloqueo de Archivo por Contraseña
	    location ^~ /proyecto/img/logo.png {
		     auth_basic_user_file .htpasswd;
		     auth_basic "Restricted";
		}

##### Bloqueo de Archivo y Redireccionar
		location = /proyecto/img/logo.png {
		  	return 301 /proyecto/;
		}

##### Bloqueo de Archivo por IP
		location /proyecto/img/logo.png {
		    allow 111.222.333.44;
		    deny all;
		}
		
### Usuario y Password (.htpasswd)
admin:123456 
