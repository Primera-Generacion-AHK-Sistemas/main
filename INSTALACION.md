
# SISTEMA:  - Sistema de MetricArs

El sistema MetricArs
Demo: https://metricars.ga/#/analisis-tecnico
# Empezando
  En esta sección detallaremos el procedimiento de instalacion para usar MetricArs de forma local. 

## Requisitos Previos 
- Navegador Web <br/>Para un mejor rendimiento recomendamos [Google Chrome](https://www.google.es/chrome/browser/desktop/index.html) aunque MetricArs es compatible con todos los exploradores 

- Servidor Web Local
    * NodeJS. El mismo puede descargarse desde este [link](https://nodejs.org/en/download/). 
    * Python 3. El mismo puede descargarse desde este [link](https://www.python.org/). 
    * Java 8. El mismo puede descargarse desde este [link](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html). 

- IDE ó Editor de texto <br/>Cualquier editor de texto es útil, incluso el bloc de notas. Otras posibles alternativas son: 
    * [Visual Studio Code](https://code.visualstudio.com/)
    * [Sublime Text](https://www.sublimetext.com/3)
    * [Notepadd++](https://notepad-plus-plus.org/download/v7.5.1.html)
- Administrador de Base de Datos : 
    * [MongoDB Compass](https://www.mongodb.com/products/compass)
    * [DBeaver](https://dbeaver.io/)


## Instalación

### Modulo Análisis Técnico
 - #### Clonar el [repositorio](https://github.com/Primera-Generacion-AHK-Sistemas/AngularArgonDashboard) de GitHub
	 - `git clone https://github.com/Primera-Generacion-AHK-Sistemas/technicalAnalisysAPI`
 - #### nos paramos en la carpeta del repositorio
	 - `cd technicalAnalisysAPI`
 - #### Instalamos las dependencias del proyecto
	 - `python3 -m pip install -r .\requirements.txt`
 - #### probamos que funcione
	 - `python3 -m uvicorn fastapp:app --reload`


### Modulo Datos de usuario
 - #### Clonar el [repositorio](https://github.com/Primera-Generacion-AHK-Sistemas/AngularArgonDashboard) de GitHub
	 - `git clone https://github.com/Primera-Generacion-AHK-Sistemas/repo-springboot`
 - #### nos paramos en la carpeta del repositorio
	 - `cd repo-springboot`
 - #### Instalamos las dependencias de maven del proyecto
	 - `maven:update`
 - #### Compilamos el proyecto
	 - `javax compile`
 - #### probamos que funcione
	 - `java -jar repo-springboot.jar`

### Base de datos PostgreSQL
 - #### Descargar desde la pagina  de [descargas](https://www.postgresqltutorial.com/postgresql-getting-started/) de la web oficial o configure una base de datos con https://www.elephantsql.com/
	 - `git clone https://github.com/Primera-Generacion-AHK-Sistemas/repo-springboot`
 - #### nos paramos en la carpeta del repositorio
	 - `cd PostgreSQL`



 - En el administrador de base de datos 
    <br/>2.1. Creamos un esquema de base de datos.
    <br/>2.2. Ejecutamos el script **"Esquema####.sql"** - Este script creará todas las tablas correspondientes al modelo de datos que implementa ####.
    <br/>2.3. Ejecutamos el script **"ConfiguracionInicial.sql"** - El mismo cargará todos los parametros necesarios para comenzar a utilizar ####.
 - Con el editor de texto ó IDE buscamos el archivo **database.php**. El mismo se encuentra dentro del package **"application/config"**.
    En caso de que no exista este archivo podemos copiar y pegar el archivo database.php.dist (también se encuentra en el mismo package) y cambiarle el nombre a database.php
 - Dentro de este archivo se encuentran todos los parámetros necesarios para la configuración de la base de datos. Debemos configurar los parámetros por default **$db['default']** con los siguientes valores para que funcione de forma local:

```
   'hostname' => '127.0.0.1'
   'username' => 'root'
   'password' => '' 
   'database' => 'nombreBd'
```

Tanto el username como password dependen de la configuración que se le haya dado al administrador de base de datos de XAMPP al momento de la instalación. Por defecto toma los valores 'root' y ' '.


### Base de datos MongoDB
 - #### Descargar e Instalar
	 - desde la pagina  de descargas de la web oficial el  [MongoDB Community Server](https://www.mongodb.com/try/download/community)
		 - `https://www.mongodb.com/try/download/community`
	 - Instalamos siguiendo la guia oficial segun nuestro sistema operativo
		 - `https://docs.mongodb.com/guides/server/install/`

 - #### Configurar
	 1. Abra la línea de comando (CLI) de su computadora (powershell, linux terminal, etc.)  y ejecute el siguiente comando:
	```
	mongo
	```
	 2. En el shell mongo ejecute los siguientes comandos:
	```
	use admin;
	db.createUser({user: "root", pwd: "password", roles:[{role: "readWrite" , db:"myDatabase"}]});
	```
	 3. Para conectarse a travez de mongodb compass use la siguiente URL:
	```
	mongodb://root:password@localhost:27017/myDatabase
	```

	[Fuente](https://lukaneco.blogspot.com/2020/05/install-mongodb-on-docker-windows-10.html)



### Servicio de autenticacion de usuarios
este es provisto por Auth0 

### Servicio de bases de datos no relacionales
 - cloud


### Modulo Web App
 - #### Clonar el [repositorio](https://github.com/Primera-Generacion-AHK-Sistemas/AngularArgonDashboard) de GitHub
	 - `git clone https://github.com/Primera-Generacion-AHK-Sistemas/AngularArgonDashboard`
 - #### nos paramos en la carpeta del repositorio
	 - `cd AngularArgonDashboard`
 - #### Instalamos las dependencias del proyecto
	 - `npm install`
 - #### Configuramos nuestro servicio de Auth0
El proyecto debe configurarse con su dominio Auth0 y su ID de cliente para que funcione el flujo de autenticación.

Para hacer esto, primero copie `auth_config.sample.json` en un nuevo archivo en la misma carpeta llamada `auth_config.json`, y reemplace los valores con sus propias credenciales de la aplicación Auth0:


```json
{
  "domain": "<YOUR AUTH0 DOMAIN>",
  "audience": "<YOUR AUTH0 API IDENTIFIER>",
  "clientId": "<YOUR AUTH0 CLIENT ID>"
}
```

 - #### Configuramos las rutas a los módulos del proyecto
 - 
Para hacer esto, primero copie `data_sources.sample.json` en un nuevo archivo en la misma carpeta llamada `data_sources.json`, y reemplace los valores con sus propias credenciales de la aplicación Auth0:


```json
{

"technicalAnalisysAPI": "<YOUR TECHNICAL ANALISYS API ADDRESS>",
"userDataAPI": "<YOUR USER DATA API ADDRESS>"",
"mongoDB": "<YOUR MONGODB HOST>"",
"postgreSQL": "<YOUR POSTGRESQL HOST>""

}
```



5. Ejecutamos con privilegios de administrador XAMPP. Tenemos que asegurarnos de que Apache y MySql inicien correctamente.
6. Abrimos cualquier browser y nos dirigimos a la ruta **localhost/####**. <br/> Si la instalación fue correcta deberiamos ver la pantalla de inicio de sesión. Podemos ingresar con el usuario generado por el script inicial: 

``` 
usuario: 'admin'
contraseña: '123456'
``` 

Estos datos pueden ser cambiados a futuro.
### Modulo Almacenamiento de datos de usuario

### Modulo Proveedor de datos de acciones
 - Clonar el [repositorio](https://#######) de Gitlab en la carpeta de "/.../xampp/htdocs/"
 - En el administrador de base de datos 
    <br/>2.1. Creamos un esquema de base de datos.
    <br/>2.2. Ejecutamos el script **"Esquema####.sql"** - Este script creará todas las tablas correspondientes al modelo de datos que implementa ####.
    <br/>2.3. Ejecutamos el script **"ConfiguracionInicial.sql"** - El mismo cargará todos los parametros necesarios para comenzar a utilizar ####.
 - Con el editor de texto ó IDE buscamos el archivo **database.php**. El mismo se encuentra dentro del package **"application/config"**.
    En caso de que no exista este archivo podemos copiar y pegar el archivo database.php.dist (también se encuentra en el mismo package) y cambiarle el nombre a database.php
 - Dentro de este archivo se encuentran todos los parámetros necesarios para la configuración de la base de datos. Debemos configurar los parámetros por default **$db['default']** con los siguientes valores para que funcione de forma local:

```
   'hostname' => '127.0.0.1'
   'username' => 'root'
   'password' => '' 
   'database' => 'nombreBd'
```

Tanto el username como password dependen de la configuración que se le haya dado al administrador de base de datos de XAMPP al momento de la instalación. Por defecto toma los valores 'root' y ' '.

5. Ejecutamos con privilegios de administrador XAMPP. Tenemos que asegurarnos de que Apache y MySql inicien correctamente.
6. Abrimos cualquier browser y nos dirigimos a la ruta **localhost/####**. <br/> Si la instalación fue correcta deberiamos ver la pantalla de inicio de sesión. Podemos ingresar con el usuario generado por el script inicial: 

``` 
usuario: 'admin'
contraseña: '123456'
``` 

Estos datos pueden ser cambiados a futuro.








# Despliegue


# Herramientas utilizadas para la construcción
* Lenguaje base: PHP
* Framework: Codeigniter
* ORM: Doctrine
* Templates & Views: Smarty 
* Generador de PDFs: TCPDF 
* Generador de XLS: Spout & PHPExcel
* Interacción con lado cliente: JavaScript, jQuery

# Para contribuir con el proyecto
1. Crear un fork (bifurcación) del repositorio
2. Crear una rama (git checkout -b MiRama)
3. Trabajar en los cambios localmente
4. Commit de los cambios locales (git commit -am 'Agrego funcionalidad X')
5. Push de los cambios del commit (git push origin MiRama)

# Versiones
- Python: 3.8
- Java: 8u261
- NodeJS: 12.19.0
- Angular: 7.xx
- PostgreSQL: x.xx
- MongoDB: 4.4

# Autores


# Licencia
Todos los derechos son reservados para 

# Agradecimientos
