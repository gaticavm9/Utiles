Paso 1: Crear el archivo .htaccess dentro del directorio raíz de la web

Paso 2: Debemos configurar el fichero .htaccess añadiendo el siguiente código:

```bash
RewriteEngine on
RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}.php -f
RewriteRule ^(.*)$ $1.php

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME}.html -f
RewriteRule ^(.*)$ $1.html
```

Paso 3: Crearemos un archivo info.php e ingresamos el siguiente código:

```php
<?php
phpinfo();
?>
```

Verificar si está instalado el módulo mod_rewrite revisando el archivo info.php

Paso 4: Si no está instalado el módulo mod_rewrite, instalar con el siguiente comando y activar.

```bash
sudo a2enmod rewrite
sudo service apache2 restart
sudo gedit /etc/apache2/sites-available/000-default.conf
```

Agregar estás lineas, después de **DocumentRoot "directorio raíz de la web":

```bash
<Directory "directorio raíz de la web">
AllowOverride All
< / Directory >
```

Paso 5:
Reiniciar Apache:

```bash
sudo service apache2 restart
```
