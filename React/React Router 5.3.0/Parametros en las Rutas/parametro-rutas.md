# ######################################################################################################### #


## -- Parametros en las Rutas -- ##


# Nota: Podemos usar el useParams Hook para obtener un parámetro de URL definido en Routes. Podemos aceptar parámetros de URL en un Route poniendo dos puntos antes del nombre del path y ese se convertira en un parámetro, como path=”/:id”.


    <Route exact path="/heroe/:heroeId" component={ HeroesScreen } /> // El parametro seria heroeId;


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: En otro componente necesitaremos lo parametros y los obtendremos con el hook.


    const parametros = useParams();

    console.log( parametro ) // Esto tendra el valor de un objeto que dentro tendra los parametros que creamos y en este caso estara el 'heroeId'.


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Y le pondremos mandar valores al parametro.


    export const Heroe = () => {

        const heroe = {

            id: 'DC-Comics-Superman'
            nombre: 'Superman'

        }

        return (
            <div>

                <Link to={ `/heroe/${ heroe.id }` }> // heroe.id sera el valor del parametro.

            </div>
        );

    };


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Y ahora al mandarlo anteriormente vamos a extraerlos y mostraremos una imagen con el parametro mandado.


    export const HeroeScreen = () => {

        const { heroeId } = useParams

        return (
            <div>

                <img src={ `../assets/heroes/${ heroeId }.jpg` } /> // La imagen tiene el nombre del id.

            </div>
        );

    };


# ######################################################################################################### #