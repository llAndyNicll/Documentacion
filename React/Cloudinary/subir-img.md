# ######################################################################################################### #


## -- Subir IMG a Cloudinary -- ##


# Nota: Aqui crearemos un boton y para subir una imagen desde nuestro ordenador.


    export const SubirIMG = () => { // El componente.

        const dispatch = useDispatch(); // ocuparemos y guardamos el dispatch.

        const handlePictureClick = () => { // Aqui tendremos una funcion que le hace click al input del file.

            document.querySelector( '#fileSelector' ).click();

        };

        const handleFileChange = ( e ) => { // En esta funcion llamamos a la funcion que subira la imagen.

            const file = ( e.target.files[ 0 ] ); // Recibimos el e, el cual trae la img seleccionada.

            if ( file ) {

                dispatch( startUploading( file ) ); // Le hacemos dispatch a la funcion y mandamos el file.

            };

        };

        return (
            <div className="notes__appbar">

                <input // El input file el cual hara la accion de target a una img de nuestro ordenador.
                    id='fileSelector'
                    type='file'
                    name='file'
                    style={{ display: 'none' }}
                    onChange={ handleFileChange } 
                />

                <div>

                    <button 
                        className="btn"
                        onClick={ handlePictureClick } // El boton que llmara las funciones.
                    >
                        Picture
                    </button>

                </div>

            </div>
        );

    };


# ######################################################################################################### #





# ######################################################################################################### #


## -- Subir IMG a Cloudinary -- ##


# Nota: Esta es la funcion la cual recibe el file y lo subira a cloudinary.


    export const fileUpload = async ( file ) => {

        const cloudUrl = 'https://api.cloudinary.com/v1_1/dy1o5vcd8/upload'; // El url de Cloudinary.

        const formData = new FormData();

            formData.append( 'upload_preset', 'el nombre de tu proyecto' );
            formData.append( 'file', file );

        try {
        
            const resp = await fetch( cloudUrl, {

                method: 'POST',
                body: formData

            });

            if ( resp.ok ) {

                const cloudResp = await resp.json();

                return cloudResp.secure_url

            } else {

                return null;

            };

        } catch ( error ) {
        
            throw error;

        };

    };


# ######################################################################################################### #





# ######################################################################################################### #


## -- Eliminar IMG de Cloudinary -- ##


# Nota: Este es el codigo para eliminar la imagen de cloudinary.


    cloudinary.v2.api.delete_resources( 'El id de la img' , {}, () => {

        console.log( 'Se elimino la imagen' );

    });


# ######################################################################################################### #