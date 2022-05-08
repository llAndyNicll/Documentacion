# ######################################################################################################### #


## -- Ejemplo del useReducer -- ##


# Nota: Crearemos un Estado en general con useState mas el reducer, y lo que haremos sera crear funciones con un nuevo estado que se lo mandaremos al reducer.


    const initialState = [{ // El estado inicial del reducer.

        id: 864592734,
        tarea: 'Aprender React',
        done: false

    }];

    export const TareasApp = () => { // Componente.

        const [ state, dispatsh ] = useReducer( reducer, initialState ); // Usamos el useReducer.

        const agregarEstado = () => {

            const nuevoEstado = { // Creamos un estado nuevo para mandarlo.

                id: 5683237,
                tarea: 'Aprender Node',
                done: false

            };

            const action = { // La accion que tiene la instruccion de agregar mas el nuevo estado.

                type: 'agregar',
                payload: nuevoEstado

            };

            dispatsh( action ); // Dirigimos la accion hacia el reducer.

        };

        return (
            <div>

                { JSON.stringify( state, null, 3 ) }

                <button onClick={ agregarEstado }> // Boton que con el click disparara esta funcion.
                    Agregar
                </button>

            </div>
        );

    };


# ######################################################################################################### #





# ######################################################################################################### #


## -- Ejemplo del Reducer -- ##


# Nota: Crearemos el reducer vasado a las actions correspondientes que necesitamos para resolver el ejemplo anterior ya que por lo general el reducer se crea en un archivo totalmente aparte ( src/reducers/reducer.js ).


    export const reducer  = ( state = [], action ) => { // Este es el Reducer.

        switch ( action.type ) { // Aqui filtraremos las actions por el type.

            case 'agregar': // Este caso es agregar, si la action que mandamos, su type es agregar, caera aqui.
            
                return [ ...state, action.payload ]; // Retornaremos el nuevo state con lo que tenia, mas lo que este dentro del action.payload.

            default:

                return state; // Si el type no se encuentra en los casos retornara el valor anterior del state.
        };

    }; 


# ######################################################################################################### #