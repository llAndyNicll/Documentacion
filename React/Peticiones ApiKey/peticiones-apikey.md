# ######################################################################################################### #


## -- Peticiones Apikey -- ##


# Nota: Este  es un ejemplo de una peticion normal a una apikey externa que nosotros no hemos creado.


    const peticion = async() => {

        const url = https://wi9ebvoibdpfn...etc // Esta es la url a donde realizaremos la peticion.

        const resp = await fetch( url ); // Se realiza la peticion.

        const { data } = await resp.json(); // obtendremos la data del la respuesta del json.

    };


# ######################################################################################################### #
