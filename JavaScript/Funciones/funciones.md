# ######################################################################################################### #


## -- Funciones -- ##


# Descripcion: Se utilizan para cambiar valores, realizar otras tareas, sumar valores, etc.


# Nota: Esto es una funcion.

    function 'nombre de la funcion'() {

        return 'valor o accion a retornar de la funcion'

    };

    function(); // llamar la funcion por el nombre dado a esta.


# Nota: Esto es una funcion normal de JS la cual no es recomendable ocupar ya que es muy facil caerle encima como cambiarle el valor a un numero ejemplo.


    function saludar( nombre ) {

        return `Hola, ${ nombre }`;

    }; 


    console.log( saludar( 'Vegeta' ) );


# Nota: Esta es la mejor forma de hacer una funcion para JS y React sin caerles encima y cambiar su valor.


    const saludar = function( nombre ) {

        return `Hola, ${ nombre }`;

    };


    console.log( saludar( 'Vegeta' ) );


# Nota: Tambien se puede hacer una funcion de flecha se sirve solamente para React. 


    const saludar = ( nombre ) => {

        return `Hola, ${ nombre }`;

    };


    console.log( saludar( 'Vegeta' ) );


# Nota: Las funciones de flecha se pueden simplificar de la siguiente manera si tienen 1 return. 


    const saludar = ( nombre ) => `Hola, ${ nombre }`;


    console.log( saludar( 'Vegeta' ) );


# Nota: Las funciones tambien pueden retornar un objeto y llamarlas y darle su valor a una nueva const.


    const getUser = ( name ) => {

        return {
            uid: 'ABC636476',
            username: name
        };
    };

    const user = getUser( 'El_Kokun3000' );


    console.log( user );


# ######################################################################################################### #
