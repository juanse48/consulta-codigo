# Anotaciones C4 - Clase 7 Front

## Inicializamos un proyecto front

## Creación de app en react
    -   Para la instalación, en la terminal nos ubicamos en la carpeta front y ejecutamos el siguiente codigo
        `npx create-react-app .` => Enetr // Dejamos el . para que nos cree la aplicación en la carpeta raiz
        - Al finalizar la instalación tiene que aparecer el mensaje `Happy hacking!`
        - Si sale un mensaje de vulnerabilidades hacemos una auditoria con el siguiente comando
            `npm config set legacy-peer-deps true`
        - Ejecutamos el comando de auditoria forzada
            `npm audit fix --force`
        - Realizamos una instalación especifica de create-react si se tienen errores)
            `npx create-react-app@5.0.1 .`
## Instalación de dependencias que requerimos en el front
    - Ejecutamos el siguiente comando
        `npm i axios react-alert react-alert-template-basic react-bootstrap react-helmet react-redux redux redux-thunk redux-devtools-extension react-router-dom`
        axios
        react-alert => Nos permite crear alertas
        react-alert-template-basic => Nos permite generar templates a las alertas
        react-boostrap => Librerias de la parte grafica en html
        react-helmet => Para el manejo de los Header
        react-redux => Para trabajar nuestros estados del proyecto
        redux => Instalamos redux tambien, no solamente el de react
        redux-thunk => 
        redux-devtools-extension
        react-router-dom => Para el manejo de las rutas
        
## Inicializamos el front
    `npm start`
    - Si llega a salir error ejecutamos el siguiente comando
        `npm config set legacy-peer-deps true`
    - Si llega a salir error de React ejecutamos importamos en el archivo *App.js*
        `import React from 'react'`
    - Para verificar la version de node escribimos
        `node --version`
        
## Ajustar front
    - En la carpeta *public* podemos hacer modificaciones ir limpiando el proyecto, agregando un nuevo logo, favicon
    
    - El App.js se esta relacionando con el index.html por medio del index.js el cual por medio de la herramienta ReactDom que enlaza
    
    - Si quiero quiero se visualice en el index tengo que hacer la modificación en el archivo App.js y luego importarlo en el index.js y llamarlo desde el cuerpo del archivo index.js
    - Creamos carpeta images en la carpeta de public para guardar el contenido de las imagenes del proyecto
    
        App.js(modificación) => index.js(exportar y vincular(llamar)) => index.html(visualizar)
    - En la carpeta *src* se crea la carpeta *components* y dentro se crea la carpeta *layout*