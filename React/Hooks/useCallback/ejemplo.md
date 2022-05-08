# ######################################################################################################### #


## -- Ejemplo del useCallback -- ##


# Nota: Estamos creando una funcion que sera mandada a otro componente para que la utilize. Tambien la guardaremos en memoria con el useCallback para que cada vez que se renderize el componente no cree una funcion igual.


    export const CallBackHook = () => { // Componente.

        const [ counter, setCounter ] = useState( 10 ); // Crearemos un contador con useState.

        const increment = useCallback( ( num ) => { // Esta es la funcion que mandaremos a otro componente.

            setCounter( c => c + num );

        }, [ setCounter ]); // Y esta con el hook para que la memorize y no se creen nuevas funciones iguales.

        return (
            <div>

                <h1>useCallBack Hook</h1>
                <h3> Counter: <small> { counter } </small> </h3>
                <hr />

                <ShowIncrement increment={ increment } /> // La funcion esta siendo mandada a otro componente.

            </div>
        );

    };


# ######################################################################################################### #