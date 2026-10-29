# Mi bóveda y contenedor seguro

## Objetivo

En esta práctica creé una bóveda de contraseñas y un contenedor cifrado para aprender a proteger credenciales y archivos personales. También documenté las configuraciones realizadas mediante capturas de pantalla.

## Herramientas utilizadas

- **KeePassXC:** gestor de contraseñas que permite guardar credenciales en una base de datos cifrada.
- **Archivo llave (Key File):** configurado como protección adicional de la bóveda, junto con la contraseña maestra.
- **VeraCrypt:** herramienta utilizada para crear y montar un contenedor cifrado de 100 MB.

## 1. Configuración de la bóveda

Creé una base de datos llamada `Boveda_Ciberseguridad` en KeePassXC.

Dentro de la bóveda agregué tres registros de prueba correspondientes a un correo electrónico, una plataforma educativa y una tienda online. Para cada registro utilicé una contraseña ficticia generada con el gestor, de al menos 16 caracteres, incluyendo números y símbolos.

También configuré un archivo llave adicional a la contraseña maestra para proteger el acceso a la base de datos.

### Evidencias

- `01-boveda-keepassxc.png`: muestra los tres registros de ejemplo sin exponer sus contraseñas.
- `02-keepassxc-archivo-llave.png`: muestra la configuración de seguridad de la base de datos y el archivo llave asociado.

## 2. Creación del contenedor cifrado

Con VeraCrypt creé un contenedor de archivos cifrado de 100 MB. Mantuve las opciones predeterminadas de cifrado, utilizando AES y SHA-512 con PBKDF2 para la derivación de claves.

Elegí una contraseña diferente de la contraseña maestra de KeePassXC y guardé la credencial del contenedor dentro de la bóveda.

Después monté el contenedor como la unidad `Z:` para poder acceder a su contenido.

### Evidencias

- `03-veracrypt-volumen-montado.png`: muestra el contenedor montado, su letra de unidad y el algoritmo de cifrado.
- `04-aprendizajes-contenedor.png`: muestra el archivo `aprendizajes.txt` dentro de la unidad `Z:`.

## 3. Archivo de aprendizajes

Dentro del volumen cifrado creé `aprendizajes.txt`, donde resumí tres conceptos importantes:

1. Los gestores de contraseñas permiten almacenar credenciales en una bóveda cifrada y generar contraseñas únicas.
2. La autenticación multifactor (MFA) agrega una capa adicional de protección a las cuentas.
3. VeraCrypt permite proteger archivos mediante contenedores cifrados que deben montarse para acceder a su contenido.

## 4. Buenas prácticas aplicadas

- Utilizar contraseñas diferentes para cada cuenta.
- Generar contraseñas largas y aleatorias.
- Proteger la bóveda con una contraseña maestra y un archivo llave.
- Utilizar una contraseña diferente para el contenedor de VeraCrypt.
- Evitar mostrar contraseñas reales en las capturas.
- Conservar copias de respaldo seguras de los archivos necesarios para recuperar el acceso.

## Conclusión

Esta práctica me permitió conocer el funcionamiento de un gestor de contraseñas y crear un contenedor cifrado para proteger archivos. También comprendí la importancia de conservar las credenciales de recuperación y de no compartir información sensible al documentar un entorno de seguridad.
