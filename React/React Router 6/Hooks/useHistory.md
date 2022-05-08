# ######################################################################################################### #


## -- useNavigate -- ##


# Nota: Hay dos formas de navegar programáticamente con React Router: < Navigate /> y navegar(). Puede obtener acceso a Navigate importándolo desde el paquete react-router-dom y puede obtener acceso para navegar utilizando el useNavigate Hook personalizado.


# Opcion 1 :


    import { useNavigate } from "react-router-dom"


    const Navigate = useNavigate();


# Opcion 2 :
    

    import { Navigate } from "react-router-dom";


    <Navigate to='/pathname' />


# ######################################################################################################### #