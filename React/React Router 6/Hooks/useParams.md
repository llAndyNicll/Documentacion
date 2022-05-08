# ######################################################################################################### #


## -- useParams -- ##


# Nota: El hook useParams, permite acceder un objeto que retiene cada parámetro dinámico ajustado sobre la ruta. Cuándo se especifica una ruta, esta puede contener parámetros de la forma :foo o :bar, referentes a parámetros dinámicos, que adquirirán el valor que establezca el usuario, sobre la url. Por ejemplo, la ruta /clients/client/:id, podrá acceder al parámetro id que contenga el valor dado por el usuario, como, /clients/client/c018, referente al usuario c018, o si se accede a la ruta /clients/client/d970, ahora el parámetro id tomará el valor de d970. Estos parámetros son útiles para recuperar valores colocados sobre el pathname de la ruta, de tal forma que nos genera una ruta dinámica y rica en información. Por ejemplo, la ruta /facturas/:uuid/proveedores/:pid, nos permitirá acceder a dos parámetros dinámicos sobre la url, que son uuid y pid, de tal modo, que podremos consultar los datos del proveedor de una factura, conociendo el uuid de la factura y el id del proveedor.


    import { useParams } from "react-router-dom"


    const params = useParams();


# ######################################################################################################### #