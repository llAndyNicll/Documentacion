# ######################################################################################################### #


## -- Template String -- ##


# Descripcion: Se ocupa para concatenar variables mas textos o numeros.


# Nota: Esto es Valido pero ya no se ocupa.


    const nombre   = 'Tanjiro';

    const apellido = 'Kamado';

    const nombreCompleto = nombre + ' ' + apellido;


    console.log( nombreCompleto );


# Nota: Esta es la forma de ocuparlo correctamente.


    const nombre   = 'Tanjiro';

    const apellido = 'Kamado';

    const nombreCompleto = ` ${ nombre } ${ apellido } `;


    console.log( nombreCompleto );


# Nota: Tambien se pueden ocupar las dos formas anteriores en una sola funcion sin nigun problema. 


    const nombre = 'Tanjiro';

    const apellido = 'Kamado';

    function getSaludo( nombre, apellido ) {

        return 'Hola ' + nombre + ' ' + apellido;

    };
    

    console.log( `Este es un texto: ${ getSaludo( nombre, apellido ) }` );


# ######################################################################################################### #
