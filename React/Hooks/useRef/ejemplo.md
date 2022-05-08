# ######################################################################################################### #


## -- Ejemplo del useRef -- ##


# Nota: Haremos un focus en el input a travez del boton haciendo un click y la funcion llamara la referencia del input.


    export const FocusScreen = () => { // Componente.

        const inputRef = useRef(); // La variable con la referencia.

        const handleClick = () => { // La funcion que se llamara haciendo click en el boton.

            inputRef.current.select(); // Le hara un select al valor del inputRef, el cual seria el input.

        };

    return (
        <div>

            <h1>Focus Screen</h1>
            <hr />

            <input
                ref={ inputRef } // Aqui esta la referencia a la variable que tendra el valor de input.form.
                className="form"
                placeholder="Escriba su nombre"
            />

            <br />

            <button className="btn btn-outline-primary" onClick={ handleClick }>
                Focus
            </button>

        </div>
    );

};


# ######################################################################################################### #