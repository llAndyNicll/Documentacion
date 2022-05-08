# ######################################################################################################### #


## -- Ejemplo de React en el Html -- ##


    <body>

        <div id="root"></div>

        <script type="text/babel">

            const divRoot = document.querySelector( '#root' );


            const nombre = 'Goku'

            const h1Tag = <h1> Hola, soy { nombre } </h1>; 

            
            ReactDOM.render( h1Tag, divRoot );

        </script>

    </body>


# ######################################################################################################### #
