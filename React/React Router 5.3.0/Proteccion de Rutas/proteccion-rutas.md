# ######################################################################################################### #


## -- Proteccion de Rutas -- ##


# Nota: Crea dos nuevos Componentes uno llamado 'PublicRoute.js' y el otro 'PrivateRoute.js' dentro de la carpeta en donde tengas el 'AppRouter.js'.Estos componentes van a resivir los valores de las rutas hijas.


    src/routes/PublicRoute.js

    src/routes/PrivateRoute.js


# ######################################################################################################### #





# ######################################################################################################### #


    export const AppRouter = () => { // Componente Padre de las rutas.

        const user = false; // La autenticacion.

        return (
            <Router>

                <div>

                    <Switch>

                        <Route exact path="/marvel" component={ MarvelScreen } /> // Se nesecita Privada.

                        <Route exact path="/dc" component={ DcScreen } /> // Se nesecita Privada.

                        <Route exact path="/login" component={ LoginScreen } /> // Se nesecita Publica.


                    </Switch>

                </div>

            </Router>
        );

    };


# Nota: Envolveremos las rutas con los Componentes creados anteriormente y les mandaremos los valores necesarios de la siguiente manera.


    export const AppRouter = () => { // Componente Padre de las rutas.

        const user = false; // La autenticacion.

        return (
            <Router>

                <div>

                    <Switch>

                        <PublicRouter // El Componente que tendra las rutas publicas.
                            exact path="/login" // Le mandaremos el pathname al cual se dirije.
                            component={ LoginScreen } // Mandamos el component, cual va dirigido al pathname.
                            isAuthenticated={ user.logged } // Mandamos la autenticacion.
                        />

                        <PrivateRouter // El Componente que tendra las rutas publicas.
                            path="/" // Le mandaremos el pathname al cual se dirije.
                            component={ DashRoutes } // Mandamos el component, cual va dirigido al pathname.
                            isAuthenticated={ user.logged } // Mandamos la autenticacion.

                        />

                    </Switch>

                </div>

            </Router>
        );

    };


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Configuraremos el componente con la autenticacion, para reedirigir a la ruta correspondiente si esta autenticado, y si no es asi lo sacaremos y lo mandaremos a la ruta publica generando una proteccion total que aun que traten de cambiar el pathname no se les permita acceder a las rutas privadas.


    export const PrivateRouter = ({ // El componente con las rutas Privadas.

        isAuthenticated,
        component: Component,
        ...rest

    }) => { Los valores, props, componentes, etc que le estavamos mandando a este componente.

        return (
            <Route { ...rest } // Desestructuraremos y le mandamos todo lo que tenia la ruta.
        
                component={ ( props ) => ( // El componente 'DashRoutes'.

                    ( isAuthenticated ) // La autenticacion.
                        ? ( <Component { ...props } /> ) // Si lo esta, nos mandara a la ruta '/'.
                        : ( <Redirect to="/login" /> ) // Si no, nos sacara a a la ruta '/login'.

                )

                }

            />
        );

    };


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Este componente es lo mismo que el anterior solamente que al reves.


    export const PublicRouter = ({ // El componente con las rutas Privadas.

        isAuthenticated,
        component: Component,
        ...rest

    }) => { Los valores, props, componentes, etc que le estavamos mandando a este componente.

        return (
            <Route { ...rest } // Desestructuraremos y le mandamos todo lo que tenia la ruta.
        
                component={ ( props ) => ( // El componente 'LoginScreen'.

                    ( isAuthenticated ) // La autenticacion.
                        ? ( <Component { ...props } /> ) // Si no, nos mandara a a la ruta '/login'.
                        : ( <Redirect to="/" /> ) // // Si lo esta, nos mandara a la ruta '/'.

                )

                }

            />
        );

    };


# ######################################################################################################### #
