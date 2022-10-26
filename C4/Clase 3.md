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
    
## Configurar una ruta
   - Dentro de back se crean las carpetas *controllers* y *routes*
   - Dentro de la carpeta controllers creamos nuestro primer controlador relacionado con productos *productsController.js*
       -- Instalamos la extension Material Icon Theme para que los iconos de VSC se vean organizados en carpetas
   - Vamos a realizar esto para probar que el servidor funciona
        - Cuando ejecute un GET de los productos se visualice un mensaje
        - Creamos un metodo de caracter exportable(porque es una salida) que se llame getProducts
        - Que nos pide getProducts para funcionar, un requisito, me puede dar una respuesta y puede dar un paso siguiente de la siguiente forma
            `exports.getProducts=(req,res,next)`
            Puede que necesite algo --> Require
            Puede que responda algo --> Response
            Puede que ejecute una accion al terminar(una actividad siguiente) --> Next
            
            ```
            //Metodo de prueba que nos genera una respuesta al estado 200 en un archivo Json
            exports.getProducts=(req,res,next) => {
                res.status(200).json({
                    success:true,
                    message: "En esta ruta ud va a poder ver todos los productos"
                })

            }
            ```
    - Se relaciona cada controlador con una ruta en un archivo aparte
        - En la carpeta rutas creamos un archivo llamado *products.js*
        - Importamos la herramienta express
            `const express = require("express")` //Este elemento express que traemos nos permite crear un enrutador
            `const router = express.Router();` //Traemos el metodo Router que nos facilita la libreria de express
            `const {getProducts} = require("../controllers/productsController")`
            //Traemos la respuesta Json desde el controlador//Creamos una constante de un arreglo para visualizar los productos, en este caso e mensaje que creamos en el controlador para verificar si el servidor esta funcionando correctamente
            `router.route('/productos').get(getProducts)` //Establecemos desde que ruta queremos ver el getProducts
            
            `module.exports = router;` //Exportamos para que se pueda ver desde afuera, en este caso el router
        - *app.js* marcamos que recursos van a ser incluidos dentro de nuestra aplicación(todo lo que uqeramos mostrar, en caso de que un recurso no se encuentre listo no lo colocamos dentro)
            - Le decimos a nuestro archivo app.js que nuestro aplicativo si va a usar información manipulable en formato json por medio de express, que cuando a el le llegue un diccionario en respuesta formato Json, lo reconozca y lo utilice
                `app.use(express.json())`
            - Le decimos que si tenga en cuenta las rutas
            `const productos = require("./routes/products")`
                Modelo => Controlador => App
            - Definimos en que area queremos ver las cosas
                `app.use('/api',productos)` //Ruta alternativa para ver todo desde el navegador, para manejar las areas administrativas en una ruta diferente a la mostrada al usuario
                
        - Probamos la respuesta en Postman
            `localhost:4000/api/productos`
 ## Realizamos la configuración para que nos quede la Base de datos activa
 - En Windows nos dirigimos a la carpeta C: y creamos la carpeta *data* dentro de esta carpeta creamos otra carpeta con el nombre *db* // En esta carpeta se van a almacenar los datos de nuestra Base de datos, tenemos que verificar esto porque normalmente no se genera automaticamente
 - Vamos a la siguiente ruta en la consola
    `C:\Program Files\MongoDB\Server\6.0\bin\` y escribimos
    `mongod`