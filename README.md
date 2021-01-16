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



Esquema procesamiento NIFI: 
![alt text]
(https://github.com/maalal/MDA2020ejercicio2/blob/main/Captura%20de%20pantalla%202021-01-16%20a%20las%2018.16.01.png)

KIBANA 
1.- Generación de un index pattern a partir del index que viene de NIFI:


![alt text](https://github.com/maalal/MDA2020ejercicio2/blob/main/Captura%20de%20pantalla%202021-01-12%20a%20las%2011.03.53.png)
2.- Reindexado del index para categorizar el geopoint que en el procesamiento de NIFI viene aparece como String.
Codigo de generación de un nuevo index que recategoriza las coordenadas de la ciudad como Geopoint. 
Consola Kibana: 
![alt text](https://github.com/maalal/MDA2020ejercicio2/blob/main/Captura%20de%20pantalla%202021-01-12%20a%20las%2011.04.25.png)
3.- Visualizacion del plano 
Generación del plano a partir de nuevo index: 
![alt text](https://github.com/maalal/MDA2020ejercicio2/blob/main/Captura%20de%20pantalla%202021-01-12%20a%20las%2011.03.10.png)

