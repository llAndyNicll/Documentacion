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
            <BrowserRouter>

                <div>

                    <Routes>

                        <Route path="/marvel" component={ MarvelScreen } /> // Se nesecita Privada.

                        <Route path="/dc" component={ DcScreen } /> // Se nesecita Privada.

                        <Route path="/login" component={ LoginScreen } /> // Se nesecita Publica.


                    </Routes>

                </div>

            </BrowserRouter>
        );

    };


# Nota: Envolveremos las rutas con los Componentes creados anteriormente y las props se mandan automaticamente entre ruta padre e hija.


    export const AppRouter = () => { // Componente Padre de las rutas.

        const user = false; // La autenticacion.

        return (
            <BrowserRouter>

                <div>

                    <Routes>

                        <PublicRouter> // Esta es la ruta publica y este componente es el padre de la ruta.

                            <LoginScreen />

                        </PublicRouter>

                        <PrivateRouter> // Esta es la ruta Privada y este componente es el padre de la ruta.

                            <DashRoutes />

                        </PrivateRouter>

                    </Routes>

                </div>

            </BrowserRouter>
        );

    };


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Configuraremos el componente con la autenticacion, para reedirigir a la ruta correspondiente si esta autenticado, y si no es asi lo sacaremos y lo mandaremos a la ruta publica generando una proteccion total que aun que traten de cambiar el pathname no se les permita acceder a las rutas privadas.


    export const PrivateRoutes = ({ children }) => { // El componente recibe el children, este es el componente envuelto en este componente en este caso es LoginScreen.

        const { user } = useContext( AuthContext );

        return user.logged
                ? children // Si esta autenticado lo mandara al componete DashRoutes. 
                : <Navigate to='/login' /> // Si no lo esta lo sacaremos al login.
    };


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Este componente es lo mismo que el anterior solamente que al reves.


    export const PublicRoutes = ({ children }) => { // El componente recibe el children, este es el componente envuelto en este componente en este caso es LoginScreen.

        const { user } = useContext( AuthContext );

        return user.logged
                ? children // Si eno esta autenticado lo mandara al componete LoginScreen. 
                : <Navigate to='/' /> // Si lo esta lo mandaremos al inicio.
    };


# ######################################################################################################### #
