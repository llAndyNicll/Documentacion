# ######################################################################################################### #


## -- useRef -- ##


# Nota: Este es un hook de referencia.


    import React, { useRef } from 'react';


    const refContainer = useRef( 'initialValue' ); 


# Nota: El hook useRef nos permite trabajar con referencias en componentes funcionales. Este hook nos retorna un objeto con una propiedad current que es mutable y cuyo valor persiste durante los renderizados y ciclo de vida del componenterias.


# ######################################################################################################### #