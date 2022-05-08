# ######################################################################################################### #


## -- useLayoutEffect -- ##


# Nota: Este es un hook de efecto, que ese ejecuta al final.


    import React, { useLayoutEffect } from 'react';


    useLayoutEffect( () => {



    }, [] ); 


# Nota: useEffect es ASINCRONO. y ejecuta el efecto después que tu componente se renderiza asegurando así que tu efecto no bloquerá el proceso principal. Tu efecto se ejecutará así:

# 1_ El componente se actualiza por algún cambio de estado, props o el padre se re-renderiza.
# 2_ React renderiza el componente.
# 3_ La pantalla se actualiza “visualmente”.
# 4_ Tu efecto es ejecutado.


# ######################################################################################################### #