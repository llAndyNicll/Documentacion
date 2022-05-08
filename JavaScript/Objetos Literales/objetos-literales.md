# ######################################################################################################### #


## -- Objetos Literales -- ##


# Descripcion: Se ocupa para agrupar llaves o mini variantes con distintos valores dentro de una sola variante.


# Nota: Esto es un objeto.


    const persona = {
        nombre: 'Tony',
        apellido: 'Stark',
        edad: 45,
    };


    console.log( persona );


# Nota: Tambien se puede tener un objeto dentro de otro.


    const persona = {
        nombre: 'Tony',
        apellido: 'Stark',
        edad: 45,
        direccion: {
            ciudad: 'New York',
            zip: 6793479379,
            lat: 14.7575,
            lng: 34.8585
        } 
    };


    console.log( persona );


# Nota: Tambien se puede imprimir el valor del objeto como una tabla. 


    const persona = {
        nombre: 'Tony',
        apellido: 'Stark',
        edad: 45,
        direccion: {
            ciudad: 'New York',
            zip: 6793479379,
            lat: 14.7575,
            lng: 34.8585
        } 
    };


    console.table( persona );


# Nota: Tambien se pueden clonar los objetos en nuevas variables y modificarlas sin ningun problema. 


    const persona = {
        nombre: 'Tony',
        apellido: 'Stark',
        edad: 45,
        direccion: {
            ciudad: 'New York',
            zip: 6793479379,
            lat: 14.7575,
            lng: 34.8585
        } 
    };

    const persona2 = { ...persona };

    persona2.nombre = 'Peter';


    console.log( persona );

    console.log( persona2 );


# Nota: Los objetos se desestructuran de la siguiente manera para que queden las variables por separado y tambien se pueden desestructurar un objeto dentro de otro.


    const persona = {
        nombre: 'Tony',
        apellido: 'Stark',
        edad: 45,
        direccion: {
            ciudad: 'New York',
            zip: 6793479379,
            lat: 14.7575,
            lng: 34.8585
        } 
    };

    const { nombre, apellido, edad, direccion } = persona;

    const { ciudad, zip, lat, lng } = direccion;


    console.log( nombre, apellido, edad );

    console.log( ciudad, zip, lat, lng );


# ######################################################################################################### #
