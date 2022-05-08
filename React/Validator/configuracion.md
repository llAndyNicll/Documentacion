# ######################################################################################################### #


## -- Configurar Validator -- ##


# Instalacion:


    npm i validator


# ######################################################################################################### #





# ######################################################################################################### #


## -- Configurar Validator y Ejemplo -- ##


# Nota: Vamos a validar si el Email es un Email correcto y valido.


    import validator from 'validator';


    if ( validator.isEmail('foo@bar.com'); //=> true ) {

        return console.log( 'El correo es valido' )

    };


# ######################################################################################################### #