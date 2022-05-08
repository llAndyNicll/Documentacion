# ######################################################################################################### #


## -- Configurar SweetAlert2 -- ##


# Instalacion:


    npm install sweetalert2


# ######################################################################################################### #





# ######################################################################################################### #


## -- Configurar SweetAlert2 y Ejemplo -- ##


# Nota: Vamos a mostrar un mensaje de error ya que el email esta mal escrito y no es valido.


    import validator from 'validator';
    import Swal from 'sweetalert2';


    const mensajeError = 'El email no es valido';

    if ( validator.isEmail('foo@gamaaal.com') ) { // El email esta mal escrito por lo cual causara un error.

        return Swal.fire( 'Error', mensajeError, 'error' ); // Se mostrara una alerta como error por el email.  

    };


# ######################################################################################################### #