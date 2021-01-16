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

Inline-style: 
![alt text]

2.- Procesador SplitJson
Para que los datos se separen en ficheros que podamos ingestar en Elastic utilizamos en procesador 

3.- PutElasticsharehttp



Inline-style: 
![alt text](https://github.com/maalal/MDA2020ejercicio2/blob/main/Captura%20de%20pantalla%202021-01-10%20a%20las%2022.50.54.png)

KIBANA 
1.- Generación de un index pattern 
Inline-style: 
![alt text](https://github.com/maalal/MDA2020ejercicio2/blob/main/Captura%20de%20pantalla%202021-01-12%20a%20las%2011.03.53.png)
2.- Reindexado del index para geopoint 
3.- Visualizacion del plano 
Inline-style: 
![alt text](https://github.com/maalal/MDA2020ejercicio2/blob/main/Captura%20de%20pantalla%202021-01-12%20a%20las%2011.03.10.png)

