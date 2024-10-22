Sistema de Gestión de Usuarios - README

Descripción

Este sistema es una aplicación web para la gestión de usuarios, con funcionalidades de registro, inicio de sesión, recuperación de contraseña, y un panel de administración que permite visualizar y eliminar usuarios. Está construido usando PHP con soporte para bases de datos MySQL y sigue buenas prácticas de seguridad como el uso de consultas preparadas, sanitización de entradas y manejo seguro de contraseñas.

Características

Registro de Usuarios: Los usuarios pueden registrarse con un nombre de usuario y contraseña.
Inicio de Sesión: Los usuarios pueden iniciar sesión con su nombre de usuario y contraseña.
Recuperación de Contraseña: Función para recuperar la contraseña utilizando el correo electrónico registrado.
Panel de Administración: Solo los usuarios con el rol de administrador pueden acceder a este panel para ver y eliminar usuarios.
Registro de Accesos: Cada inicio de sesión queda registrado en una tabla de auditoría de accesos.
Seguridad Mejorada: Implementa protección contra ataques de fuerza bruta, manejo de sesiones seguro, y manejo de errores mediante logs.
Requisitos
Servidor Web: Apache, Nginx u otro servidor web compatible con PHP.
PHP: Versión 7.4 o superior.
Base de Datos: MySQL o MariaDB.
Extensión PDO: Asegúrate de que PHP tenga habilitada la extensión PDO para conectarse a MySQL.
Composer (opcional): Para la gestión de dependencias y posibles futuras mejoras como la utilización de html purifier.

Estructura de Archivos


├── assets/                 # Archivos CSS y otros recursos

├─ controllers/            # Controladores PHP

│   ├── AuthController.php  # Controlador de autenticación

│   └── UserController.php  # Controlador de usuarios

├── includes/
│   └── db.php              # Archivo de conexión a la base de datos

├── logs/
│   └── php-error.log       # Archivo de logs de errores

├── views/

│   ├── register.php        # Página de registro

│   ├── login.php           # Página de inicio de sesión

│   └── admin.php           # Panel de administración

└── index.php               # Página principal (login)


Seguridad

Este sistema incluye varias mejoras de seguridad:

Contraseñas Hasheadas: Usa password_hash() para almacenar contraseñas seguras y password_verify() para verificarlas.
Protección contra Fuerza Bruta: Limita el número de intentos de inicio de sesión por usuario.
Sesiones Seguras: Las sesiones están configuradas con httponly, secure, y samesite para mitigar ataques XSS y de secuestro de sesión.
CSRF Tokens: Se generan tokens para prevenir ataques CSRF en formularios.

Notas Finales

Si encuentras problemas, revisa los logs de errores en logs/php-error.log. También es recomendable habilitar la depuración en un entorno de desarrollo y desactivarla en producción.
