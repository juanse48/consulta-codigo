# Anotaciones C4 - Clase 1

## Metodologias de trabajo
- The box
- Scrum
## Herramientas de trabajo
- JavaScript
    - React (Frontend)
    - Express (Intercomunicador)
    - Node Js (Backend - Persistencia y base de datos)
    
- Mongo DB (Base de datos no Relacional)
    - Creación de cuenta de usuario para el proyecto*
    
- Github(Repositorio)
        - Cuando creemos el repositorio se debe ignorar el Lenguaje principal para que no tenga en cuenta los archivos de instalación en el repositorio.
        En este caso:
        `Git Ignore - Node`
        
 - Javascript
    - Print Hola Mundo en Pantalla - **Escribir dentro de las etiquetas body**
        
        ```html
        <script>
            document.write("Hola Mundo") 
        </script>
        ```
     - Print Hola Mundo en Alerta - **Escribir dentro de las etiquetas body**
     
        ```html
        <script>
            alert("Hola Mundo") 
        </script>
        ```
     - Ejercicio de JS salude por un nombre
     
     ```html
     <html>
         <head>
             <title>Mi primer JS</title>
         </head>
         <body>
             <p>Queremos saludarte pero para eso necesitamos saber tu nombre.</p>
             <br>
             <form id="formulario">
                 Escribe tu nombre aqui: <input type="text" id="nombre"><br><br>
                 <input type="button" value="Saludar" onclick="miFuncion()">
             </form>
             <script>
                 function miFuncion(){
                     var name = document.getElementById("nombre").value;
                     alert("Hola "+name+", Como estas?")
                 }
             </script>
             
         </body>
     </html>
     ```
     
    Se coloca la etiqueta ID para que podamos interactuar con ese campo creado
    
    Se puede probar en el navegador en la parte de inspeccionar - consola
    
        document.getElementById("nombre").value
        
    Para que se ejecute la función se llama en el ejemplo anterior dentro del boton