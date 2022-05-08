# ######################################################################################################### #


## -- Ejemplo del useLayoutEffect -- ##


# Nota: Tomaremos las medidas de la caja de texto con useLayoutEffect y useRef.


    export const LayoutEffect = () => { // Componente.

        const { counter, increment, decrement } = useCounter( 1 ); // Desestructuramos el Hook del contador.

        const { data } = useFetch(`https://www.breakingbadapi.com/api/quotes/${ counter }`); // Peticion/ url.

        const { quote } = !!data && data[ 0 ];  // Si hay data desestructuraremos el 'quote'.

        const pTag = useRef(); // Crearemos una referencia.

        const [ boxSize, setBoxSize ] = useState( {} ); // Tendremos un state que tendra valor de objeto.

        useLayoutEffect( () => { // El useLayoutEffect que se ejecutara cada vez que el quote cambie.

            setBoxSize( pTag.current.getBoundingClientRect() ); // Mandaremos al state las medidas del        cuadro de texto que 'ptag' le esta haciendo la referencia.

        }, [ quote ] );

    return (
        <div>

            <h1>LayoutEffect</h1>
            <hr />

            <blockquote className="blockquote text-right">
                <p 
                    ref={ pTag } // pTag tiene el valor de la referencia de este cuadro de texto.
                    className="mb-0"
                > 
                    { quote } 
                </p>
                <br />
            </blockquote>

            <pre> { JSON.stringify( boxSize, null, 3 ) } </pre> // Mostraremos el state como objeto.

            <button className="btn btn-primary" onClick={ () => decrement(1) }>
                Anterior quote
            </button>

            <button className="btn btn-primary" onClick={ () => increment(1) }>
                Siguiente quote
            </button>

        </div>
    );

};



# ######################################################################################################### #