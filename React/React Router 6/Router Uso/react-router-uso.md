# ######################################################################################################### #


## -- Configuracion basica de uso del React Router Dom -- ##


# Nota: Crea una nueva carpeta con el componente "AppRouter" 'router/AppRouter.js'.


    import React from "react";
    import {
        BrowserRouter,
        Route,
        Link,
        Routes,
    } from "react-router-dom";


# ######################################################################################################### #





# ######################################################################################################### #


## -- Crear el componente y las rutas -- ##


    export const AppRouter = () => {

        return (
            <BrowserRouter>
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
                                <NavLink 
                                    className={ ({ isActive }) => "nav " + ( isActive ? "active" : "" ) } 
                                    to="/home"
                                >
                            </li>

                            <li className='navbar-li'>
                                <NavLink 
                                    className={ ({ isActive }) => "nav " + ( isActive ? "active" : "" ) } 
                                    to="/about"
                                >
                            </li>

                            <li className='navbar-li'>
                                <NavLink 
                                    className={ ({ isActive }) => "nav " + ( isActive ? "active" : "" ) } 
                                    to="/users"
                                >
                            </li>
                        </ul>
                    </nav>


# Nota: Aqui se definen las rutas las cual estan direccionadas a los componentes respectivos.

                    <Routes>

                        <Route path="/about" element={ <AboutScreen /> } />

                        <Route path="/users" element={ <UsersScreen /> } />

                        <Route path="/home" element={ <HomeScreen /> } />.

                    </Routes>
                </div>
            </BrowserRouter>
        );

    };


# ######################################################################################################### #