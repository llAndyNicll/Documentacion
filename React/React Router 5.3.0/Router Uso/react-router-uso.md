# ######################################################################################################### #


## -- Configuracion basica de uso del React Router Dom -- ##


# Nota: Crea una nueva carpeta con el componente "AppRouter" 'router/AppRouter.js'.


    import React from "react";
    import {
        BrowserRouter as Router,
        Switch,
        Route,
        Link,
        Redirect
    } from "react-router-dom";


# ######################################################################################################### #





# ######################################################################################################### #


## -- Crear el componente y las rutas -- ##


    export const AppRouter = () => {

        return (
            <Router>
                <div>


# Nota: Este seria el navbar el cual tendria los link hacia las rutas del router.

                    <nav>
                        <ul>
                            <li>
                                <Link to="/">Home</Link>
                            </li>

                            <li>
                                <Link to="/about">About</Link>
                            </li>

                            <li>
                                <Link to="/users">Users</Link>
                            </li>
                        </ul>
                    </nav>

                
# Nota: Este seria el navbar el cual tendria los Navlink que es para activar la clase segun la ruta activa.

                    <nav className='navbar'>
                        <ul>
                            <li className='navbar-li'>
                                <NavLink exact activeClassName='active' to="/">Home</Link>
                            </li>

                            <li className='navbar-li'>
                                <NavLink exact activeClassName='active' to="/about">About</Link>
                            </li>

                            <li className='navbar-li'>
                                <NavLink exact activeClassName='active' to="/users">Users</Link>
                            </li>
                        </ul>
                    </nav>


# Nota: Aqui se definen las rutas las cual estan direccionadas a los componentes respectivos.

                    <Switch>

                        <Route path="/about" component={ AboutScreen } />

                        <Route path="/users" component={ UsersScreen } />

                        <Route exact path="/home" component={ HomeScreen } />


                        <Redirect to='/' /> // Como su nombre lo dice Reedirecciona a la siguiente ruta si no encuentra las rutas anteriores.

                    </Switch>
                </div>
            </Router>
        );

    };


# ######################################################################################################### #