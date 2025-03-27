# Caso-practico-bike-compartidas
Este es un caso practico sobre el uso de bicicletas compartidas, cuyo objetivo es entender la diferencia entre el uso de bicicletas y usuarios tanto anuales como ocasionales
## Preguntar
Cual es la diferencia en terminos de uso de las bicicletas por parte de los usuarios anuales y ocasionales?
Tarea Empresarial
Objetivo:
Diseñar estrategias de marketing basadas en datos para aumentar la conversión de ciclistas ocasionales en miembros anuales del sistema de bicicletas compartidas.
Descripción:
Cyclistic ofrece servicios de bicicletas compartidas con opciones de pases de un solo viaje, pases diarios y membresías anuales. Actualmente, hay dos tipos de usuarios:
1.	Socios anuales: Usuarios frecuentes con suscripción.
2.	Ciclistas ocasionales: Usuarios esporádicos que pagan por pase individual o diario.

El equipo de análisis de datos debe recopilar, procesar y analizar la información de uso de ambos tipos de usuarios para identificar patrones clave y diferencias en comportamiento. A partir de estos hallazgos, se diseñarán estrategias de marketing enfocadas en:

•	Entender las diferencias de uso entre los socios anuales y los ciclistas ocasionales.

•	Identificar los factores que motivarían a los ciclistas ocasionales a adquirir una membresía anual.

•	Utilizar medios digitales para incentivar la conversión de usuarios ocasionales en miembros anuales.

El análisis debe estar respaldado por datos y proporcionar recomendaciones accionables para la estrategia de marketing de Cyclistic.
## Preparar
Se descargan 12 ultimos meses de viajes, archivos en formato CSV, correspoden al año 2024, los datos han sido proporcionados por Motivate Interacional INC. Los datos son confiables, originales, integrales, actuales y citados. 

## Procesar
Los archivos CSV, se han descargado y procesado por mes a través de la herramienta Excel. Adicionalmente se usara R para integrar la data en un solo archivo. Se seleccionan estas herramientas por su funcionalidad y versatilidad. Se codifican los nombres de los archivos identificando el mes a que corresponde. La información esta en trece columnas, las cuales contienen id de viaje, tipo de bicicleta, fecha y hora de inicio del viaje, fecha y hora fin del viaje, nombre de la estación de inicio, id de estación de inicio, nombre de la estación fin, id estación fin, tipo de miembro, star_lat, star_ing, end_lat y end_ing. Los datos originales por mes son:

Enero 144.873 registros, Febrero 223.165 registros, Marzo 301.688 registros, Abril 415.025 registros, Mayo 609.494 registros, Junio 710.722 registros, Julio 748.963 registros, Agosto 755.640 registros, Septiembre 821.276 registros, Octubre 616.281 registros, Noviembre 335.075 registros, Diciembre 178.372 registros. TOTAL 5.860.574 registros.

Para efectos del análisis se consideran 4 columnas que serán la base: rideable_type, started_at, ended_at, member_casual. Se incluyen 4 columnnas: ride_length que calcula la extensión de cada viaje que es la diferencia entre las columnas ended_at - started_at, day_of_week que calcula el día de la semana en que empezo el viaje, month que indica el mes de la información y una ultima columna que se agrupa en 6 ragos de tiempo.

De la base se eliminan todos aquellos registros en el que tiempo de duración es igual a cero, se eliminan aquellos registros que tengan un tiempo de duración inferior a 1 minuto, se corrigen aquellos valor en los cuales el tiempo de finalización (enden_at) es mayor al del inicio (started_at). Como resultado de laa depuración en total quedan 5.742.455 registros

## Analizar
Se analizaron 5.742.455 registros, que corresponden a viajes realizados en las diferentes tipos de bicicletas por los dos grupos de usuarios (casual y member), para un periodo de 12 meses contados desde enero a diciembre de 2024, el 64% de los recorridos realizados fueron hechos por los usuarios member, el 36% corresponden a recorridos realizados por usuarios casual.

Los recorridos realizado por tipo de bicicleta (rideable_type) se distribuyen asi: 50,1% electric_bike, el 47,5% classic_bike y el 2,4% electric_scooter. En la distribución de los promedio de los recorridos por día el sábado tiene la mayor participación. El mes que tuvo mas recorridos fue el mes de septiembre y el mes que tuvo menos recorridos fue el mes de enero, es decir que en las estaciones de invierno y otoño baja la demanda y en las estaciones de primavera y verano los recorridos aumentan.


<img width="429" alt="image" src="https://github.com/user-attachments/assets/ce285a0e-3080-4871-b965-28410f6112fc" /> <img width="432" alt="image" src="https://github.com/user-attachments/assets/da4eca1b-3efa-45a3-bfff-dbf0a1eaf646" />


La longitud de los recorridos en terminos de tiempo indica que el 86% de los recorridos estan en el intervalo de 1 a 30 minutos. La longitud promedio de tiempo de recorrido por usurios es: casual: 00:23:09, member: 00:13:25. La longitud promedio de tiempo recorrido por tipo de bicicleta es: classic_bike 00:20:52, electric_bike 00:11:58 y electric_scooter 00:13:18.

Los tiempos de longitud de recorrido mes día por tipo de usuario, graficamente son:

<img width="616" alt="image" src="https://github.com/user-attachments/assets/80028d04-6796-4639-8070-d681bfe38cb2" /> <img width="600" alt="image" src="https://github.com/user-attachments/assets/61b697c1-148d-40bd-b433-3ffd1d6abfdb" />

El promedio en terminos de longitud de tiempo viaje - mes por tipo de usuario se muestra a continuacion:

<img width="361" alt="image" src="https://github.com/user-attachments/assets/d0493eb7-da66-4128-94df-f3f685c2e3ba" />


El promedio en terminos de longitud de viaje - mes por tipo de bike es:

<img width="361" alt="image" src="https://github.com/user-attachments/assets/4bca23f9-8379-4ced-9f5d-a44fd21ba25c" />

El promedio de viajes día por tipo de usuario es :

<img width="492" alt="image" src="https://github.com/user-attachments/assets/86dfa582-548d-43fd-b7ff-74fcff3b7340" />

La longitud de viaje en términos de tiempo por tipo de bike y usuario se indican a continuación:

Grupo Member - Casual CASUAL
![image](https://github.com/user-attachments/assets/4012c287-7bb1-466d-8c11-a48b97d0b7a7)

Grupo Member - Casual MEMER
![image](https://github.com/user-attachments/assets/44f98b28-57b0-41d4-8394-397efe8d4db5)

La diferencias que se pueden observar en cuanto al uso de bicicleta por cada tipo de usuario las podemos resumir así:

La mayor cantidad de recorridos la realizan los usuarios identificados como miembros (member) 64%.

La mayor longitud en términos de tiempo en los recorridos la realizan los usuarios identificados como casual con un promedio de 00:23:09 frenta a 00:13:25 de los member

Las preferencia de uso en términos de logitud de tiempo por tipo de bike para ambos grupos de usuarios es la misma, optan por las classic bike, manteniendo la misma tendencia en terminos de tiempo promedio es decir que los recorridos de los usurios CASUAL son más extensos, 00:35:23 frente a 00:14:18 de los usuarios MEMBER

El 50% del total de recorridos se realizan en electric_bike frente al 47% que se realizan en classic_bike.

El 86% de longitud de los recorridos en terminos de tiempo esta entre 1 y 30 minutos.

Los recorridos realizados por tipo de bicicleta (rideable_type) se distribuyen así: 50,1% electric_bike, el 47,5% classic_bike y el 2,4% electric_scooter. En la distribución de los promedio de los recorridos por día el sábado tiene la mayor participación. El mes que tuvo más recorridos fue el mes de septiembre y el mes que tuvo menos recorridos fue el mes de enero, es decir que en las estaciones de invierno y otoño baja la demanda y en las estaciones de primavera y verano los recorridos aumentan.

En consideración al comportamiento en cuanto al uso de las bike que tiene cada grupo de ciclistas Member - Casual y con el fin de capitalizar el mismo para aumentar las membrecias, se recomendaria:

Descuentos y Beneficios Exclusivos​

Ofrecer descuentos y beneficios exclusivos puede atraer a más ciclistas hacia las membresías anuales, aumentando la participación.​

Atención al Cliente Excepcional​

Mejorar la experiencia del usuario mediante una atención al cliente excepcional es crucial para fomentar la lealtad entre los miembros.​

Uso de medios digitales para influenciar conversiones​

Importancia de los Medios Digitales​

Los medios digitales son esenciales para llegar al público objetivo y maximizar el impacto de las campañas de marketing.​

Campañas Creativas​

Implementar campañas creativas puede captar la atención del consumidor y guiar sus decisiones de compra de manera efectiva.​

Influencia en Decisiones de Compra​

Las campañas bien diseñadas pueden influir significativamente en las decisiones de compra y aumentar la base de usuarios.​

## Compartir

## Actuar
