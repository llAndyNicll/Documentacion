# ######################################################################################################### #


## -- PropTypes -- ##


# Nota: Se utilizan para exigir que la propiedad que nesesite el componente sea mandada correctamente.


    const PrimeraApp = ({ props }) => { // props = las propiedades que estamos recibiendo.

        return (
            <div>

                <h1> { props } </h1>

            </div>
        );

    };


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: Primero se importa en el componente que vaya a ser utilizado y luego se configura.


    import PropTypes from 'prop-types'


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: La configuracion siguiente se realiza al final y fuera del componenten en donde se estan recibiendo las propiedades.


    PrimeraApp.propTypes = { // PrimeraApp = nombre del componente.

        props: PropTypes.string.isRequired // La props puede ser de tipo bool, number o string.
    };


# ######################################################################################################### #





# ######################################################################################################### #


# Nota: La configuracion para que las propiedades recibidas tengan un valor default y no queden undefine.


    PrimeraApp.defaultProps = { // PrimeraApp = nombre del componente.

        props: '' // La props puede ser de tipo bool, number o string.
    };


# ######################################################################################################### #