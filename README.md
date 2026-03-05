## Proyecto: Análisis de Comportamiento y Segmentación - ConnectaTel

#Análisis ejecutivo

⚠️ Problemas detectados en los datos

El análisis inicial reveló inconsistencias que requirieron limpieza para no sesgar los resultados:

Se realizó una estandarización de los datos, convirtiendo los tipos a los correctos

Inconsistencias en la columna city: Tenía un 11.7% de datos faltantes (469 filas) y la presencia del carácter "?" como sentinel, lo que se resolvió con reeplazo a nulos.

Inconsistencias en age: se encontraron sentinels ''-999' que se reemplazaron por la mediana.

Se detectó que los nulos en duration (55.2%) y en length (44.7%) se deben a la relación de estos valores con el type de dato: si es mensaje, la duración es nula y si es llamada, la longitud de texto es nula.

Se ajustaron estadísticamente los valores extremos (Winsorización) en cant_minutos_llamada para asegurar que el promedio de consumo no se viera inflado por comportamientos atípicos.

🔍 Segmentos por Edad El perfil demográfico de ConnectaTel muestra una distribución interesante:

Jóvenes y Adultos: La edad promedio de los usuarios ronda los 30-50 años, con una presencia notable en ciudades principales como Bogotá (la ciudad con mayor frecuencia).

Comportamiento: Se observa que el plan Básico es el más adoptado por la mayoría de los rangos de edad, representando a 2,595 usuarios del total de 4,000 analizados.

📊 Segmentos por Nivel de Uso

Se identificaron dos perfiles de consumo claros basados en el tipo de servicio:

Usuarios de Mensajería (Text): Es el servicio más frecuente con 22,092 registros de uso, superando a las llamadas de voz.

Usuarios de Voz (Call): Representan una menor frecuencia pero generan mayor variabilidad en los datos de duración.

Outliers (Uso Extremo): Se detectaron valores atípicos significativos, como llamadas de hasta 120 minutos y mensajes con longitudes de 1,490 caracteres.

➡️ Esto sugiere que... Valor para el negocio: Los clientes del plan Premium son los más valiosos económicamente, pero el volumen masivo de datos está en el plan Básico, donde existe una oportunidad de upselling (migración de plan) si detectamos quiénes exceden constantemente sus límites.

Implicación de Outliers: Los patrones de uso extremo (llamadas de 2 horas o mensajes larguísimos) sugieren que un pequeño grupo de usuarios está utilizando el servicio para fines comerciales o profesionales, lo que podría afectar la estabilidad de la red o los márgenes de los planes ilimitados.

💡 Recomendaciones

Optimización de Planes: Crear un plan intermedio. Dado que el salto del Básico al Premium puede ser grande, un plan "Básico Plus" enfocado en más SMS podría captar al segmento que más utiliza el servicio de texto.

Estrategia de Retención: Investigar el 11.7% de clientes con ciudad desconocida; la falta de datos geográficos puede estar ocultando problemas de cobertura regional que deriven en churn (cancelación).

Control de Consumo: Implementar alertas de consumo para los "outliers". Si un usuario del plan Básico alcanza duraciones de llamadas extremas, ofrecerle promociones inmediatas para migrar a un plan con más minutos.
