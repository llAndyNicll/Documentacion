# ######################################################################################################### #


## -- useSelector -- ##


# Nota: useSelector es un Hook que nos permite extraer datos del store de Redux utilizando una función selectora, ésta debe ser pura ya que es potencialmente invocada múltiples veces. Con respecto a useDispatch, no tiene ningún misterio, retorna la función dispatch del almacén de Redux con la cual se pueden emitir acciones.


    import { useSelector } from 'react-redux'


    const state = useSelector( state => state.'reducer'); // Aqui extraemos el valor del reducer que necesitamos.


# ######################################################################################################### #