# ######################################################################################################### #


## -- useEffect -- ##


# Nota: Este es un hook de efecto.


    import React, { useEffect } from 'react';


# Opcion 1:

    useEffect( () => {



    }, [] );


# Opcion 2:


    useEffect( () => {

        return () => { // Se ocupa generalmente para poder limpiar o eliminar lo que este haciendo el efecto.

        }

    }, [] );


# Nota: El hook useEffect podremos ejecutar código cada vez que nuestro componente se renderice (ya sea por una actualización o sea la primera vez).


# Nota: Lo ideal es que si se crean ciertos eventos usando el useEffect, la obligacion siempre es limpiar o eliminar esos eventos para no generar loop infinitos que haran colapsar sus memorias.


# ######################################################################################################### #