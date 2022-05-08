# ######################################################################################################### #


## -- Ejemplo del useContext -- ##


# Nota: Vamos a proveer informacion a nuestras rutas hijas atravez del Context y lo primero es crearlo.


    import { createContext } from "react";


    export const UserContext = createContext( null ); // Creamos el context en un archivo aparte.


# ######################################################################################################### #





# ######################################################################################################### #


## -- Ejemplo del useContext -- ##


# Nota: Vamos a proveer informacion a nuestras rutas hijas atravez del Context y lo segundo es mandar la informacion a proveer.


    export const MainApp = () => { // El componenet Raiz.

        const [ user, setUser ] = useState( {} ); // Creamos un estado de usuario.

        return (

            <UserContext.Provider value={ { user, setUser } }> // Aqui proveemos la informacion.

                <AppRouter />

            </UserContext.Provider>

        );

    };.


# ######################################################################################################### #





# ######################################################################################################### #


## -- Ejemplo del useContext -- ##


# Nota: Vamos a proveer informacion a nuestras rutas hijas atravez del Context y lo ultimo es extraer esa informacion y usarla en sus rutas o componentes hijos.


    export const HomeScreen = () => {

        const { user } = useContext( UserContext ); // Extraemos el user de la referencia del UserContext.

        return (
            <div>

                <h1> HomeScreen </h1>
                <hr />

                <pre>

                    { JSON.stringify( user, null, 3 ) }

                </pre>

            </div>
        );

    };


# ######################################################################################################### #