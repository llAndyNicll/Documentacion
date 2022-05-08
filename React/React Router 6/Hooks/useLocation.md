# ######################################################################################################### #


## -- useLocation -- ##


# Nota: El hook useLocation, permite acceder al objeto location. Este objeto nos permitirá acceder a los atributos de la ruta, como es pathname, que es la ruta actual, search que es el query asociado a la ruta del tipo ?foo=bar, el hash de la ruta del tipo #foo-bar, y el estado de navegación pasado a la ruta, sólo si la navegación se hizo con dicho estado, sino, será undefined.


    import { useLocation } from "react-router-dom"


    const location = useLocation();


# ######################################################################################################### #