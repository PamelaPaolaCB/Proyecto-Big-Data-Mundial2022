# Proyecto del Curso Big Data Analytics – G7 (Fundación Telefónica) ⚽💯

El Proyecto responde a la necesidad de predecir a través de datos históricos y actualizados disponibles, los equipos probables que levantarían la copa en el MUNDIAL QATAR 2022. 

![22](https://user-images.githubusercontent.com/60514118/180075090-0bb43061-e6c2-4ba4-a026-6ddb67e8e8d1.jpg)

## Nombre del proyecto:

Análisis y predicción del mundial Qatar 2022.

## Nombre del equipo:

DJ PBL (Grupo #01)


## Integrantes:


⚽ [Deygerson Méndez Guédez](https://www.linkedin.com/in/deygerson-mendez/) || Data Engineer (TL)

⚽ [Luis Solis Navarro](https://www.linkedin.com/in/luisfernandosolisnavarro/) || Data Scientist

⚽ [Pamela Paola Contreras Bardales](https://www.linkedin.com/in/pamela-paola-contreras-bardales/) || Business/Data Analyst

⚽ [Bonie Pazimiño González](https://www.linkedin.com/in/bonie-scarlet-pazimi%C3%B1o-gonz%C3%A1lez-76484b18/) || Business/Data Analyst

⚽ [Jean P. Flores De La Cruz](https://www.linkedin.com/in/jeanpflores/) || Data Scientist



## Problema identificado:

El fútbol es el deporte más popular del mundo. De acuerdo con el portal de la Federación Internacional de Fútbol Asociado (FIFA, 2022), más de 265 millones de personas practican este deporte, lo que representa alrededor del 3,4% de la población mundial. Por otro lado, el evento más grande de este deporte, la Copa Mundial de la FIFA, alcanza las mayores visualizaciones a nivel de deporte individual, alcanzando los 620 millones de espectadores; siendo esta seguida por la visualización del Super Bowl estadounidense con 110 millones de espectadores.
La masividad del deporte, y sobre todo de la Copa del Mundo, trae consigo muchas pasiones. Millones de oportunidades de comercio se crean alrededor del fútbol y sus hinchas. Basta recordar la participación de nuestro país en la anterior Copa Mundial de Rusia, y el dinamismo alcanzado tanto en el consumo interno como por aquellos viajeros entusiastas que acompañaron a la selección en tan épica gesta. El hincha israelita y los miles de peruanos que gritaron en Saransk, Ekaterimburgo y Sochi; consiguieron para sí el honroso título de «la mejor hinchada del mundo».
Aquellos peruanos que alentaron desde casa o trabajos buscaban participar de la fiesta intentando adivinar los resultados de los partidos venideros. Apuestas personales, concursos de predicción de resultados incentivados por las marcas, hasta pollas grupales se volvieron el pan de cada día. Cada uno, según su intuición o método buscaba predecir la mayor cantidad de resultados; a veces sesgados por el corazón, como para pensar que Perú le ganaría a Francia, y otras usando resultados pasados de las selecciones en competencia para aproximar los resultados futuros. Inclusive salió Credicorp Capital a decir que Brasil ganaría el mundial, otra vez; fallando otra vez, como ahora sabemos.
Este proyecto nació en las vísperas del repechaje que enfrentaría la selección peruana por un cupo a Catar 2022. La idea que tuvo el grupo es de ***implementar un modelo que permita predecir al ganador del próximo mundial basado en un conjunto de datos disponibles de manera pública***.
No con la intención de predecir efectivamente al ganador sino de, a través de la aplicación de las técnicas de machine learning y visualización aprendidas en el curso, alejarnos un poco de las emociones que trae este lindo deporte e intentar aprender a ser más objetivos con la información existente. 
Sea cual sea el ganador de Qatar 2022, los participantes de este proyecto reconocemos desde ya que aprenderemos junto con nuestro modelo y buscaremos estar listos para la siguiente iteración.


## Diseño Conceptual:

La solución propuesta es la construcción de un modelo de Machine Learning, capaz de predecir a los equipos clasificados por cada grupo y al ganador de la Copa Mundial de Catar 2022. 
Para ello, es necesario obtener datos desde fuentes públicas, utilizando web scraping, esta información debe ser almacenada en un lago de datos, para poder ser consumida por el modelo y también por una solución de visualización de datos.


![Captura](https://user-images.githubusercontent.com/60514118/178649722-0ded8a16-a25f-45d6-987a-bc1d13a064e1.PNG)

## Diseño tecnológico:

Para la implementación de la solución se utilizan los servicios de Google Cloud Platform, mediante la siguiente arquitectura Batch:

* **Ingesta:** Pipelines de proceso EL(Extracción y Carga), a través de lenguaje de programación Python, en entorno Jupyter Lab, del servicio Vertex AI (Workbench). La periodicidad de la ingesta es diaria, una vez por día, de manera automatizada utilizando las ejecuciones programadas del servicio Vertex AI.

* **Almacenamiento:** Cloud Storage, BigQuery.

* **Machine Learning:** Vertex AI.

* **Analytics:** Google Data Studio.

![Captura1](https://user-images.githubusercontent.com/60514118/178650280-efffd85b-d13a-44b9-8cc4-2545cdef5eb6.PNG)

* **Código de la solución:** Link de Github


## Implementación de la solución END2END:

> 1) Creación de un nuevo proyecto “Proyecto-Final-BigData” en cuenta GCP.

![Captura3](https://user-images.githubusercontent.com/60514118/178650675-2605fd37-5829-42b0-83fb-d9a0aaed8c0e.PNG)

> 2) Asignación de permisos y roles sobre el proyecto, en el servicio IAM, para los usuarios correspondientes.

![2](https://user-images.githubusercontent.com/60514118/178650810-bdf666ae-bbf1-4f6c-974e-7a8cebf7a4c8.PNG)

> 3) Despliegue y autorización de las API’s de los distintos servicios de GCP:

* VertexAI(Workbech): Se crea nuevo notebook “proyecto-final-bigdata-notebook”.

![3](https://user-images.githubusercontent.com/60514118/178651082-83c7c0d5-2f91-4bd2-b68d-f89f5c71ac2f.PNG)

* Cloud Storage: Se crea nuevo bucket “proyecto_final_bigdata_bucket”

![4](https://user-images.githubusercontent.com/60514118/178651214-888f4217-f876-4c1a-beae-4f141e60b862.PNG)

* BigQuery: Se generan los datasets “raw_data y analytics”, los cuales contienen las tablas, que son consumidas por la solución visual.

![5](https://user-images.githubusercontent.com/60514118/178651329-b3b29704-85e8-4acd-b19f-818d7075b93b.PNG)


> 4) Desarrollo de código de pipelines y modelo de Machine Learning en entorno Jupyter Lab, del servicio Vertex AI. 

![5](https://user-images.githubusercontent.com/60514118/178651576-5d81327f-716f-488a-8c76-aa3f684c6367.PNG)


> 5) Creación de tablero en Google Data Studio:

El tablero lo puedes ver el el siguiente [link](https://datastudio.google.com/reporting/7d262f32-c37e-4943-bb9a-d377d4d5fa38)


>  6) Modelado:

>  7) Visualización con Data Studio:

La visualización de los datos es muy importante en todo proyecto, como bien lo menciona la autora de “La introducción a la visualización de datos” (Milanes guisado, Yusnelkis,2020), que con la visualización estadística de los datos, podemos ver patrones de comportamiento, tomar decisiones y mantenemos la interactividad.
Mencionado lo anterior, para el presente trabajo se propone trabajar con un herramienta en la nube y open source, como lo es Data Studio.

Pero ¿Qué es Data Studio?
Es una herramienta Open Source de Google, que opera en la nube, creada para visualización de datos, y según Google, Data Studio puede: crear informes fácilmente sobre datos de una amplia variedad de fuentes, sin tener que escribir código. En tan solo unos instantes, puedes conectarte a conjuntos de datos como: 

* Bases de datos, como BigQuery, MySQL o PostgreSQL,Productos de Google Marketing Platform, como Google Ads, Analytics, Display & Video 360 o Search Ads 360.

* Productos de consumo de Google, como Hojas de cálculo, YouTube o Search Console.

* Archivos de texto plano, mediante Google Cloud Storage o la subida de archivos CSV.

* Plataformas de redes sociales, como Facebook, Reddit o Twitter.

* Datos combinados de cualquier combinación de fuentes relacionadas.

En conclusión para los fines del proyecto es la herramienta que se alinea a las necesidades para mostrar de manera dinámica la información que nos arrojan los datos.
A continuación muestro unas capturas del Tablero en Data Studio que se elaboró para el proyecto:

![6](https://user-images.githubusercontent.com/60514118/178652278-7da2a4ad-6ec9-4dc7-bf0b-4ebe33cbcba8.PNG)






















