Este proyecto fue realizado como forma de examen en la asignatura de Bases de datos de nueva generación del Master de Big Data Analytics de la Universidad Europea de Valencia. Este proyecto fue adecuado para que pueda ser reproducido en su totalidad en este portafolio.

Para el funcionamiento correcto de este proyecto. Primero se deberá de crear un entorno de desarrollo (entorno virtual) con gitbash. Esto con el fin de que nuestro proyecto no se vea afectado por diferentes programas o versiones en el mismo. Tras esto, se opta por ejecutar en el entorno virtual el archivo requirements.

Al tener todo el proceso instalado. Se procede a realizar este caso, el cual se verá su desarrollo en el notebook llamado pipeline_GeoJSON_AWS_Snow.ipynb y cuya explicación de cada paso está mencionado en los siguientes detalles:

Este proyecto trabajara con los datos adjuntos que están en el .zip llamado requiredfiles, los cuales son: 
• Valencia_data.csv 
• Madrid_data.csv 
• Valencia_geojson.json
• Madrid_geojson.json

Estos ficheros tienen datos de geolocalización, datos de ciudades del mundo y un json que delimita un 
área respectivamente.

Las actividades que hay que realizar son:

1. Leer los csv de Valencia _data y Madrid_data con python y filtrarlos solamente por las columnas 
id, latitude, longitude y price. Escribir esos nuevos csv.

2. Cargar los datos de valencia modificados en athena y realizar las siguientes 
consultas:
 
• Filtrar por los que tienen precios superiores a 100 dólares en Valencia. 
• Seleccionar los 10 primeros id con mayor precio en Valencia. 
• Hacer un join de Valencia y Madrid para ver que ids tienen el mismo precio. 

3. Ingestar los datos de Valencia modificados en una tabla de snowflake a través de S3. 

4. Crear una transient table de esos datos mediante una tarea para quedarnos solo con el 90% de 
los apartamentos con los precios más altos.

5. Ingestar Valencia_geojson.json en una tabla de snowflake en una celda del tipo Variant.

6. Una vez creada la transient, leer los datos con python de Valencia y el geojson para crear un 
dataframe que contenga: 

• Todos los apartamentos que estén dentro del área de ese geojson. 
• Distancia desde el apartamento hasta el centro de Valencia.

7. Una vez creado el dataframe, ingestarlo en una tabla de snowflake directamente desde python. 
Ingestar desde snowfalke a S3 de nuevo.