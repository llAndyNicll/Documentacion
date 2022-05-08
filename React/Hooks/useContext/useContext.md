# ######################################################################################################### #


## -- useContext -- ##


# Nota: Este es un hook que administra informacion a sus componentes hijos.


    import React, { useContext } from 'react';


    const { variables o funciones  } = useContext( 'El create Context' );


# Nota: Context provee una forma de pasar datos a través del árbol de componentes sin tener que pasar props manualmente en cada nivel.


# ######################################################################################################### #





# ######################################################################################################### #


## -- Crear Context -- ##


# Nota: Primero, se crea el context en un componente totalmente aparte, al cual le mandaremos los valores a proveer.


    import { createContext } from "react";


    export const Context = createContext( null );


# ######################################################################################################### #





# ######################################################################################################### #


## -- Proveer el Context -- ##


# Nota: Segundo, debemos ir a la rama mas alta de nuestro proyecto para proveerlo y  despues ya podremos extraer la informacion del Context con el hook.


    export const MainApp = () => {

        return (

            <Context.Provider value={ 'La info que queremos proveer' }> // El Context es el que creamos.

                <AppRouter />

            </Context.Provider>

        );

    };


# ######################################################################################################### #