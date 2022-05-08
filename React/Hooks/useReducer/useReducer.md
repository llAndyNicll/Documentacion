# ######################################################################################################### #


## -- useReducer -- ##


# Nota: Este es un hook de estado igual que el useState solamente que este es mas global.


    import { useReducer } from 'react';


    const [ state, dispatsh ] = useReducer( reducer, initialState, init );


# Nota: useReducer es un hook de React para actualizar un estado interno por medio de una función llamada reducer. redux es una arquitectura que nos permite abstraer el manejo de un estado global en una aplicación.


# Nota: El dispatsh dirije las actions al reducer ( dispatsh( action ) ).


# ######################################################################################################### #





# ######################################################################################################### #


## -- Funcion Init -- ##


# Nota: Es una funcion que se ejecuta al comienzo del useReducer, la cual retornara el valor inicial del state del reducer ( esta funcion no es obligatoria por lo cual se puede borrar ).


    const init = () => {

        return [{

            id:  ,
            desc: ,
            done: , 
            etc: 
    
        }];

    };


# ######################################################################################################### #





# ######################################################################################################### #


## -- Reducer -- ##


# Nota: El reducer es una función pura que acepta 2 parámetros: el estado actual y un objeto de action. Dependiendo del objeto de action, la función reducer debe actualizar el estado de manera inmutable y devolver el nuevo estado.


    export const reducer  = ( state = initialState, action ) => {

        switch ( action.type ) {

            case '':
            
                return state;

            case '':

                return state;

            default:

                return state;
        };

    }; 

# Nota: Las action le mandan al reducer que tiene que hacer con el valor que le mandamos y el state se encarga del resto ( ejecutar la funcion correspondiente retornando un nuevo state ). 


# ######################################################################################################### #