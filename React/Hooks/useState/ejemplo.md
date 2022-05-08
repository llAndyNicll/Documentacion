# ######################################################################################################### #


## -- Ejemplo del useState -- ##


# Nota: Realizaremos un contador con el useState ( lo cual seria nuestro propio Custom Hook ).


    export const CounterApp = () => { // Componente.

        const [ state , setState ] = useState({ // Este es el useState el cual tendria un valor de objeto.

            counter1: 10,
            counter2: 20,

        });

        const { counter1 , counter2 } = state; // Desestructuramos las dos variables del objeto.

        const handleAdd = () => { // Funcion que llamamos al hacer click en el boton.

            setState({ // Modificaremos el valor del state.

                ...state, // Con el operador spread desarmamos el state para no sobreescribir los valores.
                counter1: counter1 + 1 // Modificamos solamente este valor del objeto ( state ).

            });

    };

    return (
        <div>

            <h1>Counter1 { counter1 } </h1>
            <h1>Counter2 { counter2 } </h1>
            <hr />

            <button onClick = { handleAdd }>
                +1
            </button>

        </div>
    );

};


# ######################################################################################################### #