MDA DATA ANALITICS 
EJERCICIO 2: NIFI + ELK 

Alumno: Marta Alvarez 

PROYECTO 
Usando nifi+ELK presentar una solución que muestre sobre un mapa la disposición de delitos presentes en esta api:

 https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9

LEVANTAR DOCKER COMPOSE 

Levantamos un docker que contenga las aplicaciones a utilizar en el proyecto. 

- Elasticshare
- Nifi
- Kibana 

INGESTION 
1.- Procesador Inovokehttp
En primer lugar conectamos nifi con la Api de datos que contiene los datos de llamadas de emergencia que queremos mapear. El conector que utilizamos es Inovokehttp

fuente de datos: https://data.cityofnewyork.us/resource/erm2-nwe9.json



2.- Procesador SplitJson
Para que los datos se separen en ficheros que podamos ingestar en Elastic utilizamos en procesador 

3.- PutElasticsharehttp



KIBANA 
1.- Generación de un index pattern 
2.- Reindexado del index para geopoint 
3.- Visualizacion del plano 

https://raw.githubusercontent.com/usuario/repositorio/rama/ruta/al/asset
