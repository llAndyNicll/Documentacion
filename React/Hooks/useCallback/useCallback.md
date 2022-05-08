# ######################################################################################################### #


## -- useCallback -- ##


# Nota: Este es un hook que memoriza funciones que se traspasan a otros componentes.


    import { useCallback } from 'react';


    const nombreFuncion = useCallback( () => {



    }, [ dependencia ] );


# Nota: Este “hook” nos permite memorizar la función que le pasemos como argumento, devolviéndonos siempre la misma “instancia” render tras render hasta que cambie alguna de las dependencias que especifiquemos. Las dependencias del “hook” useCallback funcionan del mismo modo que las del hook useEffect : son especificadas por medio de un array que pasamos como segundo argumento al hook. En el momento en que alguna de ellas cambie recibiremos una nueva versión de la función..


# ######################################################################################################### #