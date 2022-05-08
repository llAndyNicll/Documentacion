# ######################################################################################################### #


## -- Inportar React en el Html -- ##


# Nota: Los script tienen que estar dentro del html y antes que el body.


    <script crossorigin src="https://unpkg.com/react@16/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>


# ######################################################################################################### #





# ######################################################################################################### #


## -- Configurar React en el Html -- ##


# Nota: Esto tiene que estar dentro del body.


    <body>

        <div id="root"></div>


# Nota: Lo que vallamos a ocupar de react tiene que estar dentro de un script con el type="text/babel" para que el lenguaje se combierta correctamente.


        <script type="text/babel">


# Nota: Esto es para que React renderize el codigo escrito.

            const divRoot = document.querySelector( '#root' );

            
            ReactDOM.render( constante, divRoot );

        </script>

    </body>


# ######################################################################################################### #



