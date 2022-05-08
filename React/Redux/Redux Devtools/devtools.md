# ######################################################################################################### #


## -- Redux Devtools -- ##


# Nota: Redux DevTools para depurar los cambios de estado de la aplicación. La extensión proporciona potenciadores para su flujo de trabajo de desarrollo de Redux. Además de Redux, se puede usar con cualquier otra arquitectura que maneje el estado. Esto lo encontraremos en las extenciones de google:


    https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=es


# ######################################################################################################### #





# ######################################################################################################### #


## -- Configurar Redux Devtools -- ##


# Nota: Esta const debemos ponerla en el archivo store y despues la configuraremos con los Midderware.


    import { createStore, applyMiddleware, compose } from 'redux';


    const composeEnhancers = window.__REDUX_DEVTOOLS_EXTENSION_COMPOSE__ || compose;

    const store = createStore(

        reducer, 
        composeEnhancers( applyMiddleware( ...middleware ) );

    ));


# ######################################################################################################### #