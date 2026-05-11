## Análisis Operadores Empresa de Telefonia CallMeMaybe

La retención de clientes es fundamental para todas las industrias, fomentar la creación de estrategias donde se garantice la permanencia de los clientes comprometidos, leales y satisfechos a largo plazo. El siguiente análisis permite a la cadena de gimnasios Model Fitness diseñar estrategias de fidelización efectivas, aumentar la participación de los clientes actuales con el fin de anticiparse a la cancelación del servicio.


### Herramientas y tipo de proyecto

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge)

![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge)

![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)

![Data Analysis](https://img.shields.io/badge/Análisis_de_Datos-1E3A8A?style=for-the-badge)


### Preguntas clave

1. ¿Qué operadores presentan el mayor número de llamadas perdidas?
2. ¿Existe relación entre llamadas entrantes y llamadas perdidas?
3. ¿Qué operadores tienen baja gestión de llamadas salientes?

### Metodología 

* Preprocesamiento de datos: Entendimiento del contexto, revisar tamaño, una muestra de cada Dataset. Identificar si hay valores nulos o duplicados, si los tipos de datos son los esperados. Se limpiaron y estandarizaron, eliminaron inconsistencias.
* Análisis Exploratorio de Datos (EDA): Identificar registros sin operadores, total de operadores con identificador. Crear columna con el tiempo de espera de cada llamada. 
* Métricas: 
    * Tasa de llamadas perdidas por operador por mes 
        Tasas perdidas = llamadas perdidas / total llamadas.
    * Tasa de llamadas entrantes y salientes por operador 
        Tasa llamadas in = llamadas in / total llamadas
        Tasas llamadas out = llamadas out / total llamadas
    * Tiempo de espera prolongado por operador  
        Tiempo promedio espera = tiempo espera / total llamadas.
* Umbrales definidos:
    * 10% tasa de pérdida representa perdida directa de contacto con los clientes y deterioro del nivel de servicio.
    * 30s tiempo de espera indica problemas de capacidad, organización en el flujo de llamadas.
    * <30% tasa saliente Señala baja contribución a la gestión proactiva y desbalance operativo.
* Criterio de clasificación
Un operador que cumpla 2 o más condiciones de los umbrales se clasificará como operador ineficaz. 


### Conclusiones y recomendaciones 

* Actualmente la empresa cuenta con 1092 operadores, el 7.1% correspondiente a 78 operadores que se clasificaron como menos eficaces durante el análisis.
* El principal factor es la tasa de llamadas perdidas.
* No se observa relación fuerte entre el volumen de llamadas y el tiempo de espera.
* Existen casos de alto impacto que requieren revisión minuciosa.
* El problema es mayormente individual, el cumplimiento de los indicadores es por cada operador no es un problema sistémico.


## Estrategias recomendadas 

* Corto plazo
    •	Intervención directa a operadores críticos.
    •	Revisión de asignación de llamadas.

* Mediano plazo
    •	Capacitación focalizada.
    •	Ajuste de balance inbound/outbound para cada operador.

* Largo plazo
    •	Monitoreo mensual.
    •	Ajuste dinámico de umbrales de acuerdo al volumen de operación.


### Diccionario de datos 

La empresa de servicio de telefonía virtual ha compartido los datasets que continene información sobre el uso del servicio.

El dataset telecom_dataset_us.csv contiene las siguientes columnas:
* user_id: ID de la cuenta de cliente
* date: fecha en la que se recuperaron las estadísticas
* direction: "dirección" de llamada (out para saliente, in para entrante)
* internal: si la llamada fue interna (entre los operadores de un cliente o clienta)
* operator_id: identificador del operador
* is_missed_call: si fue una llamada perdida
* calls_count: número de llamadas
* call_duration: duración de la llamada (sin incluir el tiempo de espera)
* total_call_duration: duración de la llamada (incluido el tiempo de espera)

El conjunto de datos telecom_clients_us.csv tiene las siguientes columnas:
* user_id: ID de usuario/a
* tariff_plan: tarifa actual de la clientela
* date_start: fecha de registro de la clientela