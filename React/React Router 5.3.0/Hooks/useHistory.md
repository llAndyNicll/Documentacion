# ######################################################################################################### #


## -- useHistory -- ##


# Nota: El hook useHistory, permite acceder al objeto history, que posee varios métodos para navegar, y acceso al objeto location igualmente. Algunos de los métodos más importantes son push(pathname, state), que nos dirige a una ruta, con un estado opcional asociado, y replace(pathname, state), que funciona similar, sólo que reemplazando la ruta y sobre el historial de navegación. Los métodos goBack() y goForward(), que nos permitirán navegar hacia atrás y hacia adelante.


    import { useHistory } from "react-router-dom"


    const history = useHistory();


# ######################################################################################################### #