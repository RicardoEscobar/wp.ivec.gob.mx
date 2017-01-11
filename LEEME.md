2017-01-10 09:24
# LEEME.md

Este proyecto es una propuesta para modernizar el sitio web del __Instituto Veracruzano de la Cultura (IVEC).__ El propósito es recrear la funcionalidad del sitio actual, bajo el uso de __Wordpress__ el cual permite usar un gestor de contenido y aplica un diseño responsivo el cual permite visualizar el sitio web en dispositivos móviles como teléfonos inteligentes y tabletas.

# Instalación

Se asume que ya cuentas con un servidor web y con el software necesario para ejecurar __PHP__ y una base de datos que por lo general es __MySQL__ o __MariaDB__.

## Descarga de Wordpress versión 4.7

Primero hay que descargar los archivos PHP de wordpress, yo descargue el software de la siguiente liga: [Wordpress 4.7 Español México](https://es-mx.wordpress.org/wordpress-4.7-es_MX.tar.gz)

A continuación se descomprimen los archivos en la raíz del servidor web a ser instalado.

>__Nota:__ Al descomprimir el archivo , `wordpress-4.7-es_MX.tar.gz` se crea una carpeta llamada `wordpress/` y dentro de esta carpeta se encuentran los archivos del software. Asegurate que los archivos dentro de esta carpeta se encuentren en la raíz de tu servidor web ya que de lo contrario será necesario agregar `/wordpress` al final de la URL del sitio para poder acceder al mismo.

## wp-config.php

Se crea un archivo llamado `wp-config.php` y debe llevar el siguiente contenido:

```php
<?php
/**
 * The base configuration for WordPress
 *
 * The wp-config.php creation script uses this file during the
 * installation. You don't have to use the web site, you can
 * copy this file to "wp-config.php" and fill in the values.
 *
 * This file contains the following configurations:
 *
 * * MySQL settings
 * * Secret keys
 * * Database table prefix
 * * ABSPATH
 *
 * @link https://codex.wordpress.org/Editing_wp-config.php
 *
 * @package WordPress
 */

// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define('DB_NAME', 'wpivec');

/** MySQL database username */
define('DB_USER', 'wpivec');

/** MySQL database password */
define('DB_PASSWORD', 'wpivec');

/** MySQL hostname */
define('DB_HOST', 'localhost');

/** Database Charset to use in creating database tables. */
define('DB_CHARSET', 'utf8');

/** The Database Collate type. Don't change this if in doubt. */
define('DB_COLLATE', 'utf8_spanish_ci');

/**#@+
 * Authentication Unique Keys and Salts.
 *
 * Change these to different unique phrases!
 * You can generate these using the {@link https://api.wordpress.org/secret-key/1.1/salt/ WordPress.org secret-key service}
 * You can change these at any point in time to invalidate all existing cookies. This will force all users to have to log in again.
 *
 * @since 2.6.0
 */
define('AUTH_KEY',         'put your unique phrase here');
define('SECURE_AUTH_KEY',  'put your unique phrase here');
define('LOGGED_IN_KEY',    'put your unique phrase here');
define('NONCE_KEY',        'put your unique phrase here');
define('AUTH_SALT',        'put your unique phrase here');
define('SECURE_AUTH_SALT', 'put your unique phrase here');
define('LOGGED_IN_SALT',   'put your unique phrase here');
define('NONCE_SALT',       'put your unique phrase here');

/**#@-*/

/**
 * WordPress Database Table prefix.
 *
 * You can have multiple installations in one database if you give each
 * a unique prefix. Only numbers, letters, and underscores please!
 */
$table_prefix  = 'ivec_';

/**
 * For developers: WordPress debugging mode.
 *
 * Change this to true to enable the display of notices during development.
 * It is strongly recommended that plugin and theme developers use WP_DEBUG
 * in their development environments.
 *
 * For information on other constants that can be used for debugging,
 * visit the Codex.
 *
 * @link https://codex.wordpress.org/Debugging_in_WordPress
 */
define('WP_DEBUG', false);

/* That's all, stop editing! Happy blogging. */

/** Absolute path to the WordPress directory. */
if ( !defined('ABSPATH') )
	define('ABSPATH', dirname(__FILE__) . '/');

/** Sets up WordPress vars and included files. */
require_once(ABSPATH . 'wp-settings.php');

```
Es muy importante notar que el nombre de la base de datos, el usuario de la base de datos y la contraseña deben coincidir con la base de datos a usar.

## Base de datos

Este punto varia dependiendo de cada instalación, el único requisito es que el nombre de la base de datos, el usuario de la base de datos y la contraseña deben coincidir con el los mismos datos contenidos dentro del archivo `wp-config.php`. Y el usuario debe tener permisos completos sobre la base de datos.

Agrego a este projecto el archivo `wpivec.sql` el cual contiene el script requerido para la creación de la base de datos. Se debe usar un manejador de base de datos para importar dicho archivo y recrear esta base de datos en tu servidor.

>__Nota:__ Si la base de datos se encuentra en blanco, al ir a la URL del sitio web, se verá la pantalla de instalación. La base de datos debe ser restaurada antes de poder verl el sitio correctamente.

## Tipografía oficial

El archivo `fonts-GEV.zip` contiene las fuentes oficiales a usar, estas fuentes ya se encuentran instaladas en el sitio web en

Las fuentes oficiales pueden ser descargadas de: [Descargar tipografía oficial](http://intranet.veracruz.gob.mx/files/2012/01/fonts-GEV.zip)

### Uso de la tipografía oficial

- `Neo Sans Pro Light` para pies de página y/o legales.
- `Neo Sans Pro Italic` para pies de página y/o legales
- `Neo Sans Pro Regular` para párrafos de texto.
- `Neo Sans Pro Italic` para resaltar palabras dentro de párrafos de texto que tengan cierto grado de relevancia.
- `Neo Sans Pro Bold` para cabezas en comunicación, títulos y/o para destacar palabras importantes dentro de párrafos de texto.
- `Neo Sans Pro Bold Italic` puede utilizarse también para cabezas en comunicación y/o títulos para resaltar palabras dentro de los mismos.
