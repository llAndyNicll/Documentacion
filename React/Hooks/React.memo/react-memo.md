# ######################################################################################################### #


## -- React.memo -- ##


# Nota: Este es un hook que memoriza componentes.


    export const NombreComponente = React.memo( ({ value }) => {

        return (
            <>

                { value }

            </>
        );

    } );


# Nota: React.memo es un hook que permite memorizar un componente en memoria, esto quiere decir:

# React toma nuestro componente que envolvemos con React.memo, lo renderiza y lo almacena en memoria.

# Ahora, antes del siguiente render de nuestro componente memorizado, React evaluará si las propiedades han cambiado, si existe un cambio, lo volverá a renderizar y grabar en memoria, de lo contrario, utilizará el que esta en la memoria.


# ######################################################################################################### #