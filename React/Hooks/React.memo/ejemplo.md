# ######################################################################################################### #


## -- Ejemplo del React.memo -- ##


# Nota: Este componente se estaba llamando cada vez que se hacia click en un boton lo cual lo guardaremos en memoria para que eso no pase con React.memo.


    import React from "react";


    export const Small = React.memo( ({ value }) => { // Este componente se renderizara nuevamente cuando cambie el valor de la propiedad llamada value, que ya esta guardada en memoria.

        console.log( 'Me volvi a llamar :(' ); // Esto se ejecutaba cada vez que se renderizaba el componente.

        return (
            <small>

                { value }

            </small>
        );

    });


# ######################################################################################################### #