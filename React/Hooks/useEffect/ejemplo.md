# ######################################################################################################### #


## -- Ejemplo del useEffect -- ##


# Nota: Realizaremos una toma de los movimientos del mouse usando el useEffect.


    export const Message = () => { // Este es el componente.

        const [ coords, setCoords ] = useState({ x: 0, y: 0 });

        const { x, y } = coords;
    
        useEffect( () => { // Este es el useEffect.

            console.log( 'Componente Montado' );

            const mouseMove = ( e ) => { // Crearemos la funcion que guardara en el state la x, y del mouse.

                const coords = { x: e.x, y: e.y }; // Mandaremos las coordenadas del event a la x,y del state.

                setCoords( coords ); // Mandaremos las coordenadas del event a la x,y del state.

            };

            window.addEventListener( 'mousemove', mouseMove ); // Crearemos el evento de las coords del mouse.

            return () => { // Aqui haremos la limpieza ya que se sigue ejecutando el evento y se multiplica.

                console.log( 'Componente Desmontado' );

                window.removeEventListener( 'mousemove', mouseMove ); // Eliminamos el evento para que no siga funcionando.

            };

        }, [] );

    return (
        <div>

            <h2>Eres Genial!!!</h2>

            <p>
                X:{ x } Y:{ y }
            </p>

        </div>
    );

}; 


# ######################################################################################################### #