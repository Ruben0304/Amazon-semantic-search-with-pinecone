# Buscador de Productos de Amazon

Este proyecto es un buscador de productos de Amazon que utiliza técnicas de procesamiento de lenguaje natural y búsqueda semántica para ofrecer resultados relevantes en múltiples idiomas.

## Descripción del Proyecto

Este buscador de productos de Amazon permite a los usuarios realizar búsquedas en español, inglés o francés, y obtener resultados traducidos al idioma seleccionado. El proyecto utiliza las siguientes tecnologías y librerías:

- **Sentence Transformers**: Para la codificación semántica de las consultas de búsqueda.
- **Pinecone**: Como base de datos vectorial para almacenar y buscar eficientemente los productos.
- **Google Translator**: Para la traducción de consultas y resultados.
- **Pandas**: Para el manejo de datos.
- **IPython Widgets**: Para crear una interfaz de usuario interactiva.

## Características Principales

1. **Búsqueda Multilingüe**: Los usuarios pueden realizar búsquedas en español, inglés o francés.
2. **Traducción Automática**: Las consultas se traducen al inglés para la búsqueda y los resultados se traducen al idioma seleccionado por el usuario.
3. **Interfaz Gráfica Interactiva**: Incluye una barra de búsqueda, un selector de idioma y una visualización atractiva de los resultados.
4. **Resultados Detallados**: Muestra imagen, título, precio, valoración y enlace directo a Amazon para cada producto.

## Cómo Funciona

1. El usuario ingresa una consulta de búsqueda y selecciona un idioma.
2. La consulta se traduce al inglés (si es necesario).
3. Se vectoriza la consulta utilizando el modelo de Sentence Transformers.
4. Se realiza una búsqueda semántica en la base de datos de Pinecone.
5. Los resultados se traducen al idioma seleccionado por el usuario.
6. Se muestran los productos en una interfaz gráfica con detalles y enlaces a Amazon.

## Instrucciones de Uso

Para utilizar este buscador de productos, siga estos pasos:

1. Abra el siguiente enlace en Google Colab:
   [Buscador de Productos Amazon en Colab](https://colab.research.google.com/drive/12aw93WMdyCygvjrpsBluV4v0UoQsY3eC?usp=sharing)

2. Ejecute todas las celdas del notebook en orden.

3. En la interfaz de usuario que aparece:
    - Escriba su consulta de búsqueda en el campo de texto.
    - Seleccione el idioma deseado en el menú desplegable.
    - Haga clic en "Buscar" o presione Enter.

4. Espere a que se muestren los resultados. Podrá ver los productos con sus imágenes, títulos, precios y valoraciones.

5. Haga clic en "Ver en Amazon" para ir directamente a la página del producto en Amazon si desea más información.

## Notas Adicionales

- Este proyecto utiliza una API key de Pinecone. Por razones de seguridad, se recomienda no compartir públicamente esta clave.
- El rendimiento de la búsqueda y la traducción puede variar dependiendo de la conexión a internet y la carga de los servidores.

## Preparación de Datos y Configuración Inicial

Este proyecto requirió una preparación de datos y configuración inicial que se realizó una sola vez. A continuación, se describe brevemente este proceso:

1. **Carga de Datos**:
    - Se montó Google Drive para acceder a los archivos CSV.
    - Se cargaron datos de productos y categorías de Amazon desde archivos CSV.

2. **Procesamiento de Datos**:
    - Se combinaron tablas de productos y categorías.
    - Se creó una columna de texto combinado con título y nombre de categoría.

3. **Generación de Embeddings**:
    - Se utilizó el modelo SentenceTransformer para generar embeddings de los textos combinados.
    - Los embeddings se añadieron al DataFrame y se guardaron en un nuevo archivo CSV.

4. **Carga de Datos en Pinecone**:
    - Se inicializó el cliente de Pinecone con la API key.
    - Los datos se procesaron en fragmentos para su carga eficiente.
    - Cada producto se cargó en Pinecone con su embedding y metadatos relevantes.

Este proceso de preparación permitió crear la base de datos vectorial en Pinecone, que es utilizada por el buscador para realizar búsquedas semánticas eficientes.

Nota: Este código de preparación no necesita ejecutarse nuevamente para el funcionamiento normal del buscador, ya que los datos ya están cargados en Pinecone.
