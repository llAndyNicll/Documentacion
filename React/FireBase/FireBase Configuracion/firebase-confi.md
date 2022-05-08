# ######################################################################################################### #


## -- Instalar FireBase en la app -- ##


    npm install firebase@7.14.5 // npm install firebase@8.10.0


# ######################################################################################################### #





# ######################################################################################################### #


## -- Configuracion basica de FireBase -- ##


# Nota: Crea una nueva carpeta con el documento 'firebase/firebase-confi.js'.


    import firebase from 'firebase/app';
    import 'firebase/firestore';

# Nota: Esta constante 'firebaseConfig' su contenido se lo dara la pagina de firebase, esto es un ejemplo.


    const firebaseConfig = {

        apiKey: "AIzaSyCWK_akB3z-iS5tObNABxH9uYSB14kYdkc",
        authDomain: "react-app-cursos-6b615.firebaseapp.com",
        projectId: "react-app-cursos-6b615",
        storageBucket: "react-app-cursos-6b615.appspot.com",
        messagingSenderId: "441290452280",
        appId: "1:441290452280:web:3859058a69b51d2cf2e5cd"

    };


    firebase.initializeApp( firebaseConfig );

    const db = firebase.firestore();

    export {
        db,
        googleAuthProvider,
        firebase
    };



# ######################################################################################################### #





# ######################################################################################################### #


## -- Autentificador de Google -- ##


# Nota: Esto se añade al documento de '/firebase-confi.js'.


    import 'firebase/auth';

    const googleAuthProvider = new firebase.auth.GoogleAuthProvider();

    export googleAuthProvider.


# ######################################################################################################### #