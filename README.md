# unso_PDS
login_system

https://pentesting.cat sitio para visualizar el login, acceder unicamente con IPs de Argentina porque el waf bloquea IPs internacionales

Debian:

Importacion de base de datos:  sudo mysql -u root -p < /ruta/del/archivo/loginsystem_db.sql

Acceso a la base de datos: sudo mysql -t test -p Login12345@


Observaciones: crear boton de retroceso en recover.php porque tira error las cookies, solucionar el LFI con un .htaccess. 

Arreglar en las lineas el path: error_log("Too many login attempts for user: " . $username, 3, '/path/to/php-error.log'); 

Agregar(opcional):  Content Security Policy (CSP), X-Frame-Options (Anti-Clickjacking),X-Content-Type-Options

