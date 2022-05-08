# ######################################################################################################### #


## -- Precauciones de los Hooks -- ##


# Nota: Los Hooks NO se pueden poner condicional ya que genenran un error y React detecta inmediatamente un error.


# Ejemplo:


    import { useState } from 'react';


    if ( true ) {

        const [ state, setState ] = useState( '' );

    } else {

        console.log( error );

    };


# Nota: Esto NO se hace.


# ######################################################################################################### #