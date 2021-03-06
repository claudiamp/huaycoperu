# Technical people:
url: http://emergenciaperu.com/
github: https://github.com/edutrul/huaycoperu
Steps to deploy:

1. git clone git@github.com:edutrul/huaycoperu.git
2. Setup vhost local.emergenciaperu.com
2. create database db_local_huaycoperu
3. Import DB: db_local_huaycoperu_2017-03-18.sql (attached)
4. On your browser go to local.emergenciaperu.com
5. Add your changes and ping @edutrul to pull changes (we are not doing forks but you are free to do it and submit PR)

# For trello process.
Please assign a task and move it to IN PROGRESS, once done please move it to DONE (and ping in fb chat that you've done that task)

# Users

Here are dummy users

user: superadmin@example.com
contraseña: superadmin
role: superadmin(TODOS LOS PRIVILEGIOS)

user: administrador@example.com
contraseña: administrador
role: admin(CASI TODOS los privilegios)

user: member@example.com
contraseña: member
role: member (Acceso al perfil del usuario)

# Team

- Benji Santos
- Carlos Salvatierra
- Jhon Mendoza
- Eduardo Telaya
- Edwin Junior Deza
- Elvis Rivera
- Claudia Márquez
- Laura Márquez
- David Vilca
- Alvaro Concha
- Cristhian Huertos
- Edwin (edwin245)
- Renzo Telenta
- Patricia Mejia
- Fernando Balta


Pasos para revisar los tweets de usuarios que usaron los hashtags "huaycoperu, FuerzaPerú, UnidosXPiura, UnaSolaFuerza" y apartir de ellos con un solo click (los pueden convertir en incidencias)
Loguearse como administrador en
http://emergenciaperu.com/login
user: superadmin@example.com
contraseña: superadmin

Ir a http://emergenciaperu.com/admin/messages/index/3
y veran aprox más de 7000 tweets!!

Determinar si un tweet es una incidencia

En cada registro de tweet veran un enlace "Crear incidencia?" (hacer click)
Les llevara a una página para crear incidencia donde el tweet aparecera en el campo descripción (si el tweet tiene una dirección entonces manualmente copian y pegan la dirección en la casilla del mapa. además si el tweet pertenece a una categoria entonces marcar la categoría

Click Guardar Inciencia

Van a la página principal emergenciaperu.com y deberian de ver su incidencia reportada gracias al tweet
--
fin de los pasos

# Pasos para crear tareas/issues/bugs en trello

toda tarea debe tener un título (inicia con un verbo)
al realizar click en la cartilla de trello debe tener la siguiente estructura:

Descripción
{{ La descripción
y sus respectivos pasos para reproducir o nuevo requerimiento a implementar(si paso a paso)
}}
Implementación
{{ opcional: es como implementar esta solución
agregar implementación es buen para que otro Developer(sea backend/frontend) pueda leerlo y ejecutar }}

# Pasos para probar
{{ son los pasos para verificar que esta tarea este completa y funcional - tener descrito esto nos ayudara para que otra persona pueda revisar si esta tarea esta terminada o no(o determinar los siguientes pasos }}

# Correo
https://mail.zoho.com
User: contacto@emergenciaperu.com
Pass: emergenciaperu2017

# Significado de ETIQUETAS en trello
- (colores) a las tareas de front
- (amarillo), back
- (celeste) y
- contenidos (naranja)

Ushahidi Platform
=================
The Ushahidi Platform is an open source web application for information collection, vizualisation and interactive 
mapping. It allows people to collect and share their own stories using various mediums such
as SMS, Web Forms, Email or Twitter. For more information about the platform and use cases (case studies) visit: http://www.ushahidi.com


System Requirements
-------------------
To install the platform on your computer/server, the target system must meet the following requirements:

* PHP version 5.2.3 or greater (5.3 or greater is recommended)
* MySQL version 5.0 or greater
* An HTTP Server. Kohana, which Ushahidi is built on, is known to work with the following web servers:
    - Apache 1.3+
    - Apache 2.0+
    - lighttpd
    - nginx
    - Microsoft Internet Information Server (MS IIS)
* Unicode support in the operating system


Required Extensions
-------------------
The follwing is a list of PHP extensions that must be installed on your server in order for Ushahidi to run properly:

* PCRE (http://php.net/pcre) must be compiled with –enable-utf8 and –enable-unicode-properties for UTF-8 functions to work properly.
* iconv (http://php.net/iconv) is required for UTF-8 transliteration.
* mcrypt (http://php.net/mcrypt) is required for encryption.
* SPL (http://php.net/spl) is required for several core libraries.
* mbstring (http://php.net/mbstring) which speeds up Kohana's UTF-8 functions.
* cURL (http://php.net/curl) which is used to access remote sites.
* MySQL (http://php.net/mysql) is required for database access.
* IMAP (http://php.net/imap) is required for email functionality.
* GD (http://php.net/gd) is required for image processing

__NOTE: Need to figure out what extensions you already have installed on your server? Here are instructions to do just that: http://jontangerine.com/silo/php/phpinfo/__


Optional Server Requirements
----------------------------
To use Ushahidi's "Clean URLS" feature on an Apache Web Server, you will need the mod_rewrite module
and the ability to use local `.htaccess` files. 

###Installing mod_rewrite

#####Debian/Ubuntu flavours of Linux
    
    sudo a2enmod rewrite

#####CentOS, OS X and Windows

Make sure the following line is __NOT__ commented in your `httpd.conf`

    LoadModule rewrite_module


###Additional Configuration
To check if local `.htaccess` files are allowed, verify that the "AllowOverride" directive in your Apache config 
(for the web server directory in which you have installed Ushahidi) has been set to "All" i.e.:

    <Directory [your-document-root-directory]>
        ...
        AllowOverride All
        ...
    </Directory>

__NOTE:__ 

* Clean URLs means that the URLs of your deployment will not have the 'index.php' prefix
* You __MUST__ restart your Apache web server after making the changes outlined above


Installation
------------
* ####Download and extract Ushahidi
    You can obtain the official release of the software from [the download site](http://download.ushahidi.com). 
    Alternatively, you can find downloads for the current and previous releases on the [Wiki](https://wiki.ushahidi.com/display/WIKI/Ushahidi+Platform+Downloads)
    
    To unzip/extract the archive on a typical Unix/Linux command line:
    
        tar -xvf Ushahidi_Web-xxxx.tar.gz
    
    or in the case of a zip file:

        unzip Ushahidi_Web-xxxx.zip

    This will create a new directory Ushahidi_Web-xxxx containing all the Ushahidi platform files and directories - Move the contents of this directory
    into a directory within your webserver's document root or your public HTML directory.

    #####Getting the latest develop code (CAUTION: only do this if you know what you're doing) 

    clone the latest code from github

        git clone --recursive git://github.com/ushahidi/Ushahidi_Web.git

    We add the recursive flag so that git will clone the submodules too      

* ####Ensure the following directories are writable (i.e. have their permission values set to 777)
    - application/config
    - application/cache
    - application/logs
    - media/uploads
    - .htaccess
    
    On Unix/Linux, you can change the permissions as follows:

        cd path-to-webserver-document-root-directory
        chmod -R 777 application/config
        chmod -R 777 application/cache
        chmod -R 777 application/logs
        chmod -R 777 media/uploads
        chmod 777 .htaccess
        
    __NOTE: The process of configuring file permissions is different for various operating systems. Here are some helpful links about permissions for the Windows (http://support.microsoft.com/kb/308419) and Unix (http://www.washington.edu/computing/unix/permissions.html) operating systems.__

* ####Create the Ushahidi database
    Ushahidi stores all its information in a database. You must therefore create this database in order to install Ushahidi. This is done as follows:
    
        mysqladmin -u 'username' -p create 'databasename'
    
    MySQL will prompt for the password for the <username> database password and then create the initial database files. Next, you must log in and set the 
    database access rights:
    
        mysql -u 'username' -p
    
    Again, you will be prompted for the 'username' database password. At the MySQL prompt, enter the following command:
    
        GRANT SELECT, INSERT, DELETE, UPDATE, CREATE, DROP, ALTER, INDEX, LOCK TABLES on database.* 
        TO 'username'@'localhost' IDENTIFIED BY 'password';
    
    Where:
    - 'databasename' is the name of your database
    - 'username@localhost' is the name of your MySQL account
    - 'password' is the password required for that username

    __NOTE: Your account must have all the privileges listed above in order to run Ushahidi on your webserver.__

* ####Ensure PHP error_reporting level is compatable
    As of PHP-5.4 Ushahidi doesn't work with the error_reporting level E_STRICT.  Ensure this level is excluded from the error_reporting configuration.

* ####Run the install script
    To run the install script, point your browser to the base url of your website: (e.g. http://www.example.com).
    
    You will be guided through a series of screens to set up the database and site settings depending on the installation method you choose (Basic or Advanced)

* ####Clean up
    ##### Delete the installer
    Leaving the installer files in your installation is a security risk.
    Now you've installed successfully, **Delete the entire installer directory**

    ##### Remove write permissions from config files

        cd path-to-webserver-document-root-directory
        chmod -R 755 application/config
        chmod 644 application/config/*
        chmod 644 .htaccess

Additional Information
----------------------
For further references and documentation, head over to our wiki (http://wiki.ushahidi.com). Also, we encourage you to drop by our forums (https://wiki.ushahidi.com/display/forums/Ushahidi+Forums) if you have any additional questions or concerns.
