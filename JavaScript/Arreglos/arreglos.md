# ######################################################################################################### #


## -- Arreglos -- ##


# Descripcion: Es una coleccion de informacion que se encuentra dentro de una variable, como por ejemplo: una coleccion de numeros, de nombres, etc.


# Nota: Esto es valido pero no se deberia ocupar a menos que el valor y sus posiciones no se vallan a modificar.


    const arreglo = new Array( 100 );


    console.log( arreglo );


# Nota: Esta es la forma de crear un arreglo correctamente.


    const arreglo = [ 1, 2, 3, 4 ];


    console.log( arreglo );


# Nota: Tambien se pueden expandir de la siguiente manera, solamente que la idea no es ocupar el push porque se pasa a llevar directamente el arreglo lo cual se puede evitar con el operador express. 


    const arreglo = [ 1, 2, 3, 4 ];

    arreglo.push( 5 ); // se añade el 5 al arreglo.


    console.log( arreglo );



    let arreglo2 = { ...arreglo, 5 }; // se añade el 5 a todo el arreglo ya existente sin pasarlo a llevar.


    console.log( arreglo2 );


# Nota: Podemos modificar el valor de cada elemento dentro del arreglo, con una funcion. 


    const arreglo = [ 1, 2, 3, 4 ];

    const arreglo2 = arreglo.map( function( numero ) {

        return numero * 2;

    });


    console.log( arreglo2 );


# Nota: map lo que hace es recorrer por cada una de las posiciones del arreglo.


# ######################################################################################################### #
