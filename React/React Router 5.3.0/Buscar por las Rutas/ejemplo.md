# ######################################################################################################### #


## -- Ejemplo de Cadenas de consulta -- ##


# Nota: Vamos a buscar en un input el heroe, el valor lo mandaremos al pathname y luego lo desetructuraremos y al final filtrateros nombres de heroes con el valor del query recivido.


    export const SearchScreen = ({ history }) => { // Tenemos el componete con el history.

        const location = useLocation(); // Obtenemos el valor de la location

        const { q = '' } = queryString.parse( location.search ); // Desestructuramos el valor del search.

        const [ { inputValue }, handleInputChange ] = useForm({

            searchText: q

        }); // Un hook de formulario para el input que tendra el  valor inicial del q.

        const heroesFiltered = getHeroesByName( q );

        const handleSubmit = ( e ) => { // La funcion que se accionara al boton de buscar.

            e.preventDefault();

            history.push(`?q=${ searchText }`); // Mandaremos el valor del input como una cadena de consulta.
            // Y a la vez navegaremos a esa ruta.
        };

        return (
            <div>

                <form onSubmit={ handleSubmit }> // La funcion de buscar.

                    <input
                        type="text"
                        placeholder="Escribe tu heroe..."
                        className="form-control" 
                        name="searchText"
                        autoComplete="off"  
                        value={ searchText } // Donde buscaremos los heroes.
                        onChange={ handleInputChange }
                    />

                    <button
                        type="submit" 
                    >
                        Buscar...
                    </button>

                </form>

                    {
                        heroesFiltered.map( hero => ( // Mostraremos los heroes filtrados por el nombre. 

                            <HeroesCard
                                key={ hero.id }
                                { ...hero }
                            />

                        ))
                    }

            </div>
        );

    };


# ######################################################################################################### #