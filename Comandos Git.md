#### Comandos basicos Git
- Consultar ramas branch Git

    ```git branch```

- Eliminar rama Git

    ```git branch -d origin/master```

- Crear branch(rama) Git

    ```git branch juanSebastian```

- Trabajar sobre la rama que cree

    ```git checkout juanSebastian```

- Actualizar a GitHub

    ```git push origin juanSebastian (nombre rama)```

- Unir rama con archivo principal, primero ubicarse en rama donde se reciben esos cambios

    ```git merge juanSebastian master```

- Se hace un pull para bajar los datos

    ```git pull```

- Se hace un push para subir los datos

    ```git push```

- Cuando se presenta un error de esta clase **Your branch and 'origin/master' have diverged,
and have 1 and 13 different commits each, respectively.** se puede arreglar con el siguiente comando

    ```git reset --hard origin```

    Luego:

    ```git status -s```

- Cuando se presenta un error de Merge

    ```git merge --abort``` o ```git reset --merge```

- Cuando se genera un conflicto, revisar archivo y eliminar las divisiones

    ```====``` 

### Pasos para generar un merge correctamente
1. Creamos la rama para modificar

    ``` git branch nueva-rama```

2. Nos posicionamos en la nueva rama

    ```git checkout nueva-rama```
    
3. Realizamos los cambios que necesitemos, actualizamos la rama y generamos el commit

    ```git add .```
    ```git commit -m "Actualización"```
    
4. Cambiamos a la rama principal (master)

    ```git checkout master```
    
5. Generamos el merge primero colocando la rama del cambio y luego la principal

    ```git merge nueva-rama master```

6. Generamos el push
    
    ```git push```
    o
    ```git push origin master```
    
- Cuando se genera un cambio que queremos restaurar

    ```git restore (nombre del archivo)```

### Generar nuevo proyecto

1. Crear proyecto desde IDE (Intellij)
2. Generar Clase principal (Java)
3. Ir a la carpeta del proyecto -File - Open in - Explorer
4. Abrir consola Git Bash desde la carpeta
5. Inicializar Git desde la carpeta con el comando

    ```git init```
    
6. Asociar usuario (En caso de utilizar por primera vez git)

    ```git config --global user.name "USUARIO"```
    
7. Asociar correo con el que esta asociada la cuenta en GitHub

    ```git config --global user.email "CORREO"```
    
8. Revisar el estado de la carpeta
    
    ```git status -s```

9. Agregar todos los archivos

    ```git add .``` o ```git add (nombre_archivo)```

10. Generamos el commit

    ```git commit -m "Texto que describe el cambio"```
    
11. Mostrar historial de nuestro repositorio

    ```git log```

- Cuando tengamos un archivo de lectura podemos salir de el con la tecla **q**
- Salir archivo de lectura, presionamos **Ctrl+c**, luego escribirmos **:qa** y presionamos **Enter**

## Subir repositorios a GitHub
1. Crear repositorio en GitHub
2. Verificar si nos encontramos en la rama principal
    
    ```git branch```

3. Agregar la rama principal
    
    ```git branch -M master```
    
4. Asociar nuestro repositorio GibHub al Local con la dirección que nos proporciona GitHub

    ```git remote add origin https://github.com/juanse48/prueba123.git```
    
5. Subir nuestro repositorio a GitHub

    ```git push -u origin master```
    
    - Recordar que **master** es la rama donde estamos trabajando, en caso que nos encontremos en otra rama debemos agregar el nombre de la misma
    
    - Cuando un colaborador genera cambios dentro del repositorio tenemos que actualizar nuestro repositorio local descargando la ultima información incluida

        ```git pull -u origin master```


## Comandos Git Log

   ```git log --oneline```
    
   ```git log --decorate```

   ```git log --graph```

   ```git log --all```
 
 * Ver la configuración del repositorio
 
     ```git config -l```
     
 * Add y Commit al tiempo
    
   ```git commit -am "Mensaje"```
    
* Para hacer comparaciones entre dos commit se utiliza

   ```git diff (codigo de ambos commit)```
   
* Para forzar un pull

    ```git pull origin main --allow-unrelated-histories```