# ######################################################################################################### #


## -- Cadenas de consulta -- ##


# Nota: Podremos hacer cadenas de consulta en el pathname para obtener informacion o traspasar informacion a travez de la ruta ya que eso se almacena el la location de la ruta.

    http://localhost:3000/search?q=batman // '?q=' Esa es la cadena y el valor siguiente es la busqueda.

# Ejemplo de hacer cadenas de consulta:


# Ejemplo 1:

    <Link to={ `/account?name=${ valor x }` }><Link/>


# Ejemplo 2:

    <Link to={ `/account?name=${ valor x }` }><Link/>


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Ahora necesitamos obtener el valor para poder manipularlo, como generando filtros de busqueda, mostrar pantallas, elementos etc. Y Para eso ocuparemos el useLocation().


    // El pathname sera el siguiente: http://localhost:3000/search?q=batman


    const location = useLocation();

    console.log( location ); // Esto tendra el siguiente valor:

    {
        hash: "",
        key: "r8m5dcd5",
        pathname: "/search",
        search: "?q=batman", // Aqui esta nuestra busqueda por lo cual para manipularlo lo desestructuramos.
        state: null
    }


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Necesitaremos el valor en limpio porque si lo estraemos ahora estara '?name=batman' y no queremos eso. Entonces podemos acceder a la cadena de consulta a través de esto: location.search entonces podemos analizarlo usando una biblioteca llamada query-string. Esta biblioteca tiene una función parse() que analiza la cadena de consulta y devuelve un objeto totalmente limpio.


# Instalacion necesaria: 

    npm install query-string


# Nota: Ahora en cualquier componente podemos tener ese valor y ocuparlo con el siguiente codigo:


    import querySting from 'query-string';
    import { useLocation } from 'react-router-dom';


    const location = useLocation();

    const { name = '' } = queryString.parse( location.search );

    console.log( name ); // Y tendremos el valor de 'batman';


# ######################################################################################################### #