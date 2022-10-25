# Anotaciones C4 - Clase 2

## Definir el proyecto
   - Tienda
   
## Descargas necesarias
   - Descargar NodeJs - Recomendada 16.17.1 LTS - (nodejs.org/es)
        - Instalar NodeJs, viene con la instalación de npm
   - Descargar y instalar Postman (postman.com/downloads)
   - Descargar y instalar MongoDB Compass - Archivo tipo MSI (mongodb.com/try/download/community2) Version Community Server
        - Para probar que nos instalo correctamente colocamos:
                `mongod`
                
            Cuando genera un error en la instalación de MongoDb Compass debemos:
            
                1. Ir a la ruta y copiarla:
                    - Archivos de programa->MongoDb->Server->6.0->bin
                2. Buscar en el simbolo de Windows - Editar variables de entorno del sistema
                3. Ir al boton Variables de Entorno
                4. Donde dice variables del sistema editar donde dice Path
                5. Creamos uno nuevo, y pegamos la ruta que copiamos
                6. Aceptamos y cerramos todo, reiniciamos nuestro Visual Studio Code
                7. Abrimos desde Visual Studio Code y escribimos:
                   mongod
                8. Si tenemos una respuesta, significa que MongoDB trabaja
                
## Iniciando el proyecto
- Desde VSC abrimos la carpeta donde vamos a alojar nuestro proyecto
- Abrimos una terminal y verificamos que nos encontremos en la carpeta de nuestro proyecto
- Dentro de la carpeta del proyecto en VSC creamos un folder que se llame *back* y otro folder llamado *front*
- Dentro de la terminal que abrimos vamos a escribir `npm init` (Comando de NodeJS) para realizar la configuración inicial de nuestro proyecto
    ```
    Creación de ficha tecnica y archivo proncipal de nuestro aplicativo (package.json --> es similar al archivo pom en java):
    - package name:(nombre-proyecto) --> Enter
    - version: (1.0.0) --> Enter
    - description: --> Agregamos una descripción del proyecto y Enter
    - entry point: (index.js) --> server.js (Cambiamos el punto de arranque)
    - test command: --> Enter
    - git repository (https://github.com/...)  --> Enter o pegar un repositorio donde queramos trabajar el proyecto
    - keywords: --> Enter
    - author: --> Nombre de la empresa y Enter
    - license: (ISC)  --> Enter
    Is this Ok?(yes) --> yes y Enter
    ```
- Realizamos la instalación en consola de lo que necesitamos para trabajar en nuestro proyecto (Creamos un entorno de desarrollo)
    - Express - Es el intercomunicador entre el back y el front
    - Dotenv - Sirve para configurar el entorno de trabajo (maquina virtual para hacer pruebas)
    - Mongoose - Nos permite comunicarnos con la base de datos MongoDB que instalamos para el proyecto
    
    Ejecutamos el comando de instalación de los paquetes necesarios
        ```
        npm i express dotenv mongoose
        ```
- Nos ubicamos en la carpeta de *back* y creamos dos archivos
    - app.js - 
        - Definimos en una variable *express* para que podamos utilizar los recursos que nos provee esta libreria
            `const express = require("express");`
        - Definimos una variable *app* para darle congruencia a la existencia de el archivo
            `const app = express();`
        En JS tenemos que preparar el archivo para poder utilizar los recursos que contiene dentro de otros archivos(desde otro archivo podemos llamar lo con `require = ("app")`)
            `module.exports = app`
        
    - server.js -
        - Creamos una constante llamada *app* y llamamos el archivo
            `const app = require("app")`
    
    ** *Respirar dar una vuelta y volver a resolver problemas - Si le funciona a alguien a mi tambien me puede funcionar - Que a uno le de rabia no va a cambiar el echo que asi son las cosas* **
    
- Nos ubicamos en el folder back y creamos un folder llamado config, dentro de este nuevo folder creamos un archivo llamado config.env (Para que se configure nuestro entorno de desarrollo con dotenv) este archivo sirve para configurar los puertos y las direcciones donde se va a trabajar, es similar a un application.properties de Java (Cuando se sube el archivo config.env a github se sube oculto)
    - Configuramos el puerto y le asignamos el 4000 ya que la mayoria de veces cuando estamos trabajando con este tipo de herramientas con JS o NodeJS se maneja este puerto
        `PUERTO=4000`
        `NODE_ENV=DEVELOPMENT`