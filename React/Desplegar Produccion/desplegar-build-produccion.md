# ######################################################################################################### #


## -- Desplegar Build de Produccion -- ##


# Nota: Lo primero que se hace es verificar que no hayan errores y luego en la terminal en donde se encuentra el proyecto escribir el siguiente comando.


    npm run build


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Luego vamos a inicializar el proyecto con git por lo cual debemos escribir en la terminal en donde se encuentra el proyecto el siguiente comando.


    git init


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Luego vamos a preparar todos lo archivos para subirlos a git por lo cual debemos escribir en la terminal en donde se encuentra el proyecto el siguiente comando.


    git add .


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Luego vamos a sacar la "foto" la cual capturara a todos los archivos como estan en el momento de hacerlo, por lo cual debemos escribir en la terminal en donde se encuentra el proyecto el siguiente comando.


    git commit -m "Nombre que le quieras dar al primer commit"


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Luego vamos a cambiar el nombre de la carpeta "build" por "docs", seguido de eso tenemos que volver a sacar la "foto" por lo cual repetiremos estos comandos.


    git add .

    git commit -m "Nombre que le quieras dar al commit"


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Luego tenemos que ir a git y crear un nuevo repositorio, y cuando este listo debemos copiar los comando que estan al ultimo que generalmente son estos y pegarlos en la consola donde esta el proyecto.


    git remote add origin "el repositorio que te da git"

    git push -u origin master


# Nota: La idea para que no hayan errores es que lo copien directo de git, luego les pedira su nombre y contraseña y con eso estara su proyecto subido a git.


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Ahora tenemos que desplegarlo a la web con el hosting gratuito que tiene git, por lo cual nos tendremos que ir a settings y bajar hasta donde dice GitHub Pages y seleccionar en Source la opcion de master branch /docs, y esperaremos a que el enlace se vuelva de color verde y estamos listo ( se demora entre 3 a 5 minutos en este listo ).


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Por ultimo tendremos que ir a la carpeta docs, abrir el archivo html y se vera minimizado por lo cual iremos a la barra de VS code y haremos click en "View", seleccionaremos "Command Palette" y escribiremos "Format Document" y precionaremos Enter.Tendremos que agregarle un punto a todos los Link que tengan "Href" al comienzo para reubicar esos documentos y para finalizar tendremos que escribir secuencialmente estos comandos y estaremos listo.

    git add .

    git commit -m "Nombre que le quieras dar al commit"

    git push


# ######################################################################################################### #