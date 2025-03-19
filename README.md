# Caso-practico-bike-compartidas
Este es un caso practico sobre el uso de bicicletas compartidas, cuyo objetivo es entender la diferencia entre el uso de bicicletas y usuarios tanto anuales como ocasionales
# Preguntar
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
# Preparar
Se descargan 12 ultimos meses de viajes, archivos en formato CSV, correspoden al año 2024, los datos han sido proporcionados por Motivate Interacional INC. Los datos son confiables, originales, integrales, actuales y citados. 

# Procesar
Los archivos CSV, se han descargado y procesado por mes a través de la herramienta Excel. Adicionalmente se usara R para integrar la data en un solo archivo. Se seleccionan estas herramientas por su funcionalidad y versatilidad. Se codifican los nombres de los archivos identificando el mes a que corresponde. La información esta en trece columnas, las cuales contienen id de viaje, tipo de bicicleta, fecha y hora de inicio del viaje, fecha y hora fin del viaje, nombre de la estación de inicio, id de estación de inicio, nombre de la estación fin, id estación fin, tipo de miembro, star_lat, star_ing, end_lat y end_ing. Los datos originales por mes son:

Enero 144.873 registros, Febrero 223.165 registros, Marzo 301.688 registros, Abril 415.025 registros, Mayo 609.494 registros, Junio 710.722 registros, Julio 748.963 registros, Agosto 755.640 registros, Septiembre 821.276 registros, Octubre 616.281 registros, Noviembre 335.075 registros, Diciembre 178.372 registros. TOTAL 5.860.574 registros.

Para efectos del análisis se consideran 4 columnas que serán la base: rideable_type, started_at, ended_at, member_casual. Se incluyen 4 columnnas: ride_length que calcula la extensión de cada viaje que es la diferencia entre las columnas ended_at - started_at, day_of_week que calcula el día de la semana en que empezo el viaje, month que indica el mes de la información y una ultima columna que se agrupa en 6 ragos de tiempo.

De la base se eliminan todos aquellos registros en el que tiempo de duración es igual a cero, se eliminan aquellos registros que tengan un tiempo de duración inferior a 1 minuto, se corrigen aquellos valor en los cuales el tiempo de finalización (enden_at) es mayor al del inicio (started_at). Como resultado de laa depuración en total quedan 5.742.455 registros

# Analizar
Se analizaron 5.742.455 registros, que corresponden a viajes realizados en las diferentes tipos de bicicletas por los dos grupos de usuarios (casual y member), para un periodo de 12 meses contados desde enero a diciembre de 2024, el 64% de los recorridos realizados fueron hechos por los usuarios member, el 36% corresponden a recorridos realizados por usuarios casual.

Los recorridos realizado por tipo de bicicleta (rideable_type) se distribuyen asi: 50,1% electric_bike, el 47,5% classic_bike y el 2,4% electric_scooter. En la distribución de los promedio de los recorridos por día el sábado tiene la mayor participación. El mes que tuvo mas recorridos fue el mes de septiembre y el mes que tuvo menos recorridos fue el mes de enero, es decir que en las estaciones de invierno y otoño baja la demanda y en las estaciones de primavera y verano los recorridos aumentan.

La longitud de los recorridos en terminos de tiempo indica que el 86% de los recorridos estan en el intervalo de 1 a 30 minutos. La longitud promedio de tiempo de recorrido por usurios es: casual: 00:23:09, member: 00:13:25. La longitud de recorrido por tipo de bicicleta es: classic_bike 00:20:52, electric_bike 00:11:58 y electric_scooter 00:13:18.






# Compartir

# Actuar
