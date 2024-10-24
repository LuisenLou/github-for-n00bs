
# GITHUB - ¿Qué es? 

Es una plataforma de alojamiento de código que permite a desarrolladores y equipos colaborar en proyectos mediante el uso de Git, un sistema de control de versiones. GitHub facilita el seguimiento de cambios, la colaboración en el desarrollo y la publicación de proyectos, entre otros aspectos.

## ¿Cómo funciona GITHUB?

1. **Git**: Sistema de control de versiones que rastrea los cambios en el código. Permite guardar el estado del código en diferentes "commits" (versiones) y moverse entre ellos.
2. **Repositorio**: Es un espacio donde se almacena el proyecto. Puede ser público (visible para todos) o privado.
3. **Commit**: Es un "punto de control" que guarda los cambios realizados. Cada commit lleva un mensaje que describe los cambios.
4. **Branch (Rama)**: Git permite trabajar en diferentes versiones de tu proyecto mediante ramas. La rama principal se llama "main" o "master". Puedes crear otras ramas para desarrollar   nuevas funcionalidades sin afectar el código principal.
5. **Pull Request**: Se utiliza para solicitar que los cambios en una rama sean fusionados (merge) con la rama principal o con otra.
6. **Issues y Wikis**: GitHub incluye herramientas para gestionar tareas y documentar proyectos.

## ¿Cómo iniciar un repositorio en GITHUB?

1. Abrir la consola o terminal.
   
2. Usar el comando 'git clone', seguido de la URL del repositorio previamente creado en GITHUB. La URL la puedes ubicar en el botón 'Code' en la página del repositorio de GITHUB.

    ```bash
    git clone https://github.com/your_user/yoour_repo.git

  Este comando descargará una copia local del repositorio en tu máquina.

3. Navega a la carpeta del repositorio.

    ```bash
    cd your_repo

4. Crea un archivo y haz commit.

    1. Mediante POWERSHELL de Windows.

        ```powershell
        New-Item -ItemType file -Path "C:\Users\YourUser\Documents\my_file.txt"


    2. Mediante Linux.

        ```bash
        touch my_file.txt

    3. Añade el archivo al "stagin area" de GITHUB.

        ```bash
        git add my_file.txt

    4. Realiza un commit para guardar los cambios en el historial de Git.

        ```bash
        git commit -m "Add file my_file.txt"

    El argumento "-m" permite añadir un texto corto con el commit.

5. Sube los cambios al repositorio en GITHUB.

    ```bash
    git push origin main

Este comando enviará tus cambios al repositorio remoto (en GitHub) en la rama main o master.


## ¿Cómo iniciar un repositorio vacío en GITHUB?

- Cuando se crea un repositorio en GITHUB por la interfaz web, este repositorio suele estar vacío por lo que
se debe crear un 'remote' desde este repositorio vacío para vincular tu repositorio local con el remoto en GITHUB
para poder empezar a trabajar de manera sincronizada entre ambos.

    ## Pasos para crear un remote desde un repositorio vacío.

    1. Crear el repositorio local (si no está creado ya).

        - En Linux:

            ```bash
            mkdir my_project
            cd my_project
            git init

        - En PowerShell:

            ```powershell
            New-Item -ItemType Directory -Path "my_project"
            cd my_project
            git init
    
    2. Agregar archivos y hacer el primer commit.

        - En Linux:

            ```bash
            touch my_file.txt
            git add my_file.txt
            git commit -m "First commit - add my_file.txt"

        - En PowerShell:

            ```powershell
            New-Item -ItemType file -Path "C:\Users\YourUser\Documents\my_project\my_file.txt"
            git add my_file.txt
            git commit -m "First commit - add my_file.txt"

    3. Vincular el repositorio local con el remoto en GitHub

       - Ahora se debe vincular el repositorio local con el repositorio remoto vacío en GITHUB utilizando el comando
        'git remote add'. Este comando le dice a Git que el repositorio remoto de GITHUB es un lugar donde se puede subir/push o del
        que podemos descargar/pull los cambios.

       - Copiamos la URL del repositorio remoto en GITHUB y escribimos en la terminal

            ```bash
            git remote add origin https://github.com/your_user/your_repo.git

        El comando 'origin' es el nombre que comúnmente se usa para referirse al repositorio remoto.

    4. Subir los archivos al repositorio remoto en GITHUB.

        - Una vez que ya se ha vinculado el repositorio remoto con el local, puedes subir tus archivos (commits) al repositorio en GITHUB usando el comando


            ```bash
            git push -u origin main

        El argumento '-u' es opcional pero establece la rama origin main como la rama predeterminada para los siguientes 'git push', de forma
        que las siguientes veces que realices 'git push' no será necesario añadir ningún argumento adicional.


## ¿Qué sucede si mi rama principal no es 'main' sino 'master'?

 - Si tu rama principal se llama master en lugar de main, no hay ningún problema funcional, ya que Git permite que las ramas se llamen como desees. Sin embargo, en los últimos años, muchos proyectos han migrado la rama predeterminada de master a main, 
    ya que es una práctica adoptada por plataformas como GitHub por razones inclusivas y de estandarización.

- Si deseas migrar de master a main debes:

    1. Renombrar la rama local.

        ```bash 
        git branch -m master main

    2. Actualizar el repositorio remoto.

        ```bash
        git push origin main

    3. Cambiar la rama predeterminada en el remoto:

        - Ve a Settings > Branches
        - Cambia la Branch default de master a main.
  
    4. Eliminar la rama master del remoto.

        ```bash
        git push origin --delete master

