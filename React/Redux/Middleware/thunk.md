# ######################################################################################################### #


## -- Thunk -- ##


# Nota: Redux Thunk es un middleware que le permite llamar a creadores de acciones que devuelven una función en lugar de un objeto de acción. Esa función recibe el método de envío al store, que luego se usa para enviar acciones síncronas regulares dentro del cuerpo de la función una vez que se han completado las operaciones asíncronas..


    npm install redux-thunk


# ######################################################################################################### #





# ######################################################################################################### #


## -- Configurar Thunk -- ##


# Nota: Esto lo colocaremos en el archivo 'store'.


    import thunk from 'redux-thunk';


    export const store = createStore(  

    reducers,
    composeEnhancers( applyMiddleware( thunk ) ) // Va como Middleware dentro del store
    
    );


# ######################################################################################################### #