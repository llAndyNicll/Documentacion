# ######################################################################################################### #


## -- ## LO BASICO DE 'firebase/firestore' ## -- ##


# Nota: Ejemplo del objeto que vamos a manipular en la coleccion.

    const usuario = {

        nombre: 'Bardock',
        activo: true,
        fechaNaci: 0,
        salario: 5000

    };
  

# ######################################################################################################### #





# ######################################################################################################### #


## -- Referencia a la coleccion -- ##


# Nota: Guardamos la referencia de la coleccion en una constante para manipularla mejor.


    const usuarioRef = db.collection( 'usuarios' );


# ######################################################################################################### #





# ######################################################################################################### #


## -- Insert info usuarios... -- ##


# Nota: Añade el objeto que nosotros le mandamos en una nueva colleccion atravez de una promesa async.


    await db.collection( 'usuarios' )

        .add( usuario )

            .then( docRef => {

                console.log( docRef )

            })
            .catch( e => {

                console.log( 'Error', e );

            });


# ######################################################################################################### #





# ######################################################################################################### #


## -- Update usuarios set activo = false where... -- ##


# Nota: Actualizacion del objeto seleccionado segun su id.

# SubNota: update = actualiza el objeto seleccionado o lo añade si no esta.


    await usuarioRef.doc( 'StYNytAyDn1WMQVHSmuJ' )

        .update({

            activo: false,
            fechaNaci: '27/03/2003'

        });


# SubNota: set = elimina todo lo que esta y sobrescribe lo nuevo.


    await usuarioRef.doc( 'StYNytAyDn1WMQVHSmuJ' )

        .set({

            activo: false,
            edad: 44

        });


# ######################################################################################################### #





# ######################################################################################################### #


## -- Delete from usuario where id = 'xxx' -- ##


# Nota: Elimina el objeto seleccionado segun la id.


    await usuarioRef.doc( 'StYNytAyDn1WMQVHSmuJ' )

        .delete()

            .then( () => console.log( 'Borrado' ) )

            .catch( e => console.log( 'Error', e ) );


# ######################################################################################################### #





# ######################################################################################################### #


## -- Select * from usuarios -- ##


# Nota: podemos llamar y traer la coleccion completa con todo sus datos.


# Opcion 1: 'Normal';

    await usuarioRef.onSnapshot( snap => {

        retornaDocumentos( snap )

    });


# Opcion 2: 'Entrega los valores de la data solamente';

# Nota: Los snap se los manda por determinado.

    usuarioRef.onSnapshot( retornaDocumentos );


# Opcion 3: 'No sigue obserbando la base de datos y no se actualiza aunque cambien sus valores';

    await usuarioRef.get()

            .then( snap => retornaDocumentos( snap ) )

            .catch( e => console.log( 'Error', e ) );

        
# Opcion 4: 'Combinacion opcion 2 y opcion 3';

    usuarioRef.get().then( retornaDocumentos );


# ######################################################################################################### #





# ######################################################################################################### #


#   // Extra: este es el componente al cual se le llama en las siguientes funciones:


    export const retornaDocumentos = ( snapshot: firebase.firestore.QuerySnapshot ) => {

        const documentos: any[] = [];

        snapshot.forEach( snapHijo => {

            documentos.push({

                id: snapHijo.id,
                ...snapHijo.data()

            });

        });

        console.log( documentos )

        return documentos;

    };


# ######################################################################################################### #





# ######################################################################################################### #


## -- Select * from usuarios -- ##


# Nota: Filtrar elementos del objeto por condiciones de la coleccion.


    await usuarioRef.where( 'activo', '==', true ).get().then( retornaDocumentos );

    await usuarioRef.where( 'salario', '>', 1800 ).get().then( retornaDocumentos );


# Nota: Se pueden hacer varias condiciones a la vez.


    await usuarioRef.where( 'salario', '>=', 1800 )

            .where( 'salario', '<=', 2300 )

            .get().then( retornaDocumentos );


# Nota: Se pueden hacer varias condiciones a la vez pero si son distintas hay que crear el indice.

# SubNota: En el error que da esto te dan un url para crear el indice en firebase mucho mas rapido.


    await usuarioRef.where( 'salario', '>=', 1800 )

            .where( 'activo', '==', true )

            .get().then( retornaDocumentos );


# ######################################################################################################### #





# ######################################################################################################### #


## -- Select *from usuarios order by nombre asc, salario asc -- ##


# Nota: Podemos ordenar la lista como lo nesecitemos.


    await usuarioRef.orderBy( 'nombre' )

            .orderBy( 'salario', asc )

            .get().then( retornaDocumentos );


# ######################################################################################################### #





# ######################################################################################################### #


## -- Limit -- ##


# Nota: Pudes traer la cantidad de elementos que quieras o nesecites.


    await usuarioRef.limit( 1 ).get().then( retornaDocumentos );



# ######################################################################################################### #





# ######################################################################################################### #


## -- Ejercicio para ir trallendo elementos dos en dos -- ##


# Nota: Esto trae de sos en dos.


    const btnNext = document.createElement( 'button' );

    btnNext.innerText= 'Next Page';

    document.body.append( btnNext );


    let lastDocument: any = null;
    let firstDocument: any = null;


    btnNext.addEventListener( 'click', () => {

        const query = usuarioRef.orderBy( 'nombre' ).startAfter( lastDocument );

        query.limit( 2 ).get().then( snap => {

            firstDocument = snap.docs[ 0 ] || null
            lastDocument = snap.docs[ snap.docs.length - 1 ] || null

            retornaDocumentos( snap )

        });


    });

    btnNext.click();


# Nota: Esto retrocede de dos en dos.


    const btnPrevius = document.createElement( 'button' );

    btnPrevius.innerText= 'Previus Page';

    document.body.append( btnPrevius );


    btnPrevius.addEventListener( 'click', () => {

        const query = usuarioRef.orderBy( 'nombre' ).endBefore( firstDocument );

        query.limit( 2 ).get().then( snap => {

            firstDocument = snap.docs[ 0 ] || null
            lastDocument = snap.docs[ snap.docs.length - 1 ] || null

            retornaDocumentos( snap )

        });


    });


# ######################################################################################################### #