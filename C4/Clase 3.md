# Anotaciones C4 - Clase 3

## Arranque del servidor
    -   Dentro del archivo server.js configuramos el arranque del servidor(los archivos app.js y server.js trabajan de la mano)
        ```server.js
        ...
        
        //Setear el archivo de configuración
        const dotenv=require("dotenv"); //Traer la libreria dotenv para que funcione el process.env
        dotenv.config({path: 'back/config/config.env'}) //Llamamos el archivo config.env
        
        const server=app.listen(process.env.PORT, () => {
            console.log(`Servidor iniciado en el puerto: ${process.env.PORT} en modo: $process.env.NODE_ENV`) // Mensaje - concatenar la variable
        }) // Le decimos que escuche(Estamos llamando) - Forma de declarar metodos en JS
        ```
## Instalación y configuración de nodemon

Nodemon: Motor que esta todo el tiempo vigilando si hicimos cambios y relanzando el servidor para que no nos toque hacer ese proceso manual

- En la consola vamos a escribir

    `npm i nodemon --save-dev` --> Enter
    
- Verificamos que la instalación se realizo correctamente en el archivo package.json

- En el archivo package.json en la parte de scripts modificamos el atributo test que se encuentra por defecto, de la siguiente forma:
    `"start": "node_back/server.js",` // Le estamos diciendo al entorno que cuando le demos start el tiene que ejecutar el comando entre comillas
    `"dev": "SET NODE_ENV=DEVELOPMENT& nodemon back/server",` // Le decimos que cuando lo envie a desarrollo, le pedimos que configure el metodo de desarrollo NODE_ENV va a ser DEVELOPMENT
    `"prod": "SET NODE_ENV=PRODUCTION& nodemon back/server"`
    //Le vamos a configurar un modo de producción, mas adelante cuando vayamos a hacer el despliege el automaticamente cambie de modo de DEVELOPMENT a PRODUCTION

##Iniciar Servidor y Lanzarlo
    `npm run dev`