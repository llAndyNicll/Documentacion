# ######################################################################################################### #


## -- useMemo -- ##


# Nota: Este es un hook que memoriza valores.


    import { useMemo } from 'react';


    const nombreVariable = useMemo( () => funcion(), [ dependencia ] );


# Nota: El hook useMemo nos sirve para memorizar valores. Recibe una función que retorna el valor a memorizar y como segundo parámetro opcional, un array de dependencias. Si no pasamos el array de dependencias, se ejecutará en cada renderizado.


# ######################################################################################################### #