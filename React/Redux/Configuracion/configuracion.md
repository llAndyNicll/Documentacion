# ######################################################################################################### #


## -- Configurar Redux -- ##


# Nota: Lo primero que tendremos que hacer es crear una carpeta en 'src' que se llamara 'store' y tambien crearemos un archivo llamado store.js.

    src/store/store.js


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Y por ultimo debemos probeerlo a nuestra aplicaccion, y para eso tendremos que ir al componente mas alto de nuestra aplicacion.


    import { Provider } from 'react-redux'
    import { store } from "./store/store";


    export const JournalApp = () => { // El componente raiz de mi app.

        return (

            <Provider store={ store }> // Y con eso proveemos nuestro store a todos nuestros componentes.

                <AppRouter />

            </Provider>

        );

    };


# Nota: En los hook veremos como podemos hacer  los dispatch globales a nuestros reducers, tambien como podremos desestructurar y obtener esa informacion, etc.


# ######################################################################################################### #