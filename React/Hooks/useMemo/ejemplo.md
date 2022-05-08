# ######################################################################################################### #


## -- Ejemplo del useMemo -- ##


# Nota: Este componente cada vez que se renderizaba ejecutaba la funcion 'procesoPesado' lo cual colapsaba la Ram, entonces lo guardaremos en memoria con useMemo para que se llame la funcion solamente cuando cambie su valor.


    export const MemoHook = () => { // Componente.

        const { counter, increment } = useCounter( 10 ); // Usamos un Custom Hook de contador.

        const [ show, setShow ] = useState( true ); // Creamos un state.

        const memoProcesoPesado = useMemo( () => procesoPesado( counter ), [ counter ] ); // Memorizamos esta funcion pesada que retorna un valor de string.

        return (
            <div>

                <h1>MemoHook</h1>
                <h3> Counter: <small> { counter } </small> </h3>
                <hr />

                <p> { memoProcesoPesado } </p>

                <button className="btn btn-primary" onClick={ increment } >
                    + 1
                </button>

                <button
                    className="btn btn-outline-primary"
                    onClick={ () => {

                        setShow( !show );

                    }}
                >
                    Show/Hide { JSON.stringify( show ) }
                </button>

            </div>
        );

    };


# ######################################################################################################### #