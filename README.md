# Bases de datos codornices

Este repositorio contiene las bases de datos resumidas y las funciones para expandir y completar las databases obtenidas de datos de acelrómetros montados sobre el lomo de codornices japonesas (_Coturnix coturnix_) macho. Se decidió trabajar con codornices japonesas (_Coturnix coturnix_) como modelo animal, dado que es considerada una excelente especie modelo para estudios de aves de granja en laboratorio.

Los datos han sido procesados para mejorar su comprensión, eliminando variables ruidosas y se han incorporado nuevas características con el propósito de facilitar la clasificación de los eventos comportamentales llevados a cabo por las codornices.

Se considera que el entorno social donde vive un individuo influencia su comportamiento imponiendo patrones de control social, generando o limitando oportunidades para desarrollar ciertas conductas, reduciendo o provocando estrés, o estableciendo restricciones a las opciones individuales. En animales de granja, se ha propuesto que el entorno social además tiene el potencial de modular la organización temporal del comportamiento de los individuos que conforman el grupo social (Guzman-Flesia et al., 2017 Sci Rep:7), (Alcalá et al. 2019, Comm. Biol.:2). Un evento comportamental de interés se refiere a un comportamiento particular o conjunto de comportamientos que son seleccionados para su observación, análisis o estudio debido a su relevancia en un contexto específico. Algunos de los eventos de interés que se analizan en esta base de datos son los **eventos reproductivos**, o los **baños de arena**, entre otros, que se encuentan en los archivos de comportamientos.

Las databases aquí presentadas fueron utilizadas en la tesina de la bióloga **María Victoria De La Fuente** defendida el 11 de septiembre de 2023 titulada: _Estudio de la relación entre señales de aceleración y comportamiento reproductivo en machos adultos de codornices_ (Coturnix japonica) _bajo diferentes contextos sociales_. En la tesina se transformaron los registros crudos en diversas métricas utilizadas para caracterizar algunos comportamientos de interés. En la base de datos resumida se tienen las aceleraciones dinámicas de cada eje (columnas: Axis-X, Axis-Y, Axis-Z), que refleja la aceleración generada por los movimientos individuales (columnas: DBA-X, DBA-Y, DBA-Z), además de funciones para obtener las aceleraciones estáticas de cada eje (columnas: Estatica-X, Estatica-Y, Estatica-Z) , la aceleración dinámica general del cuerpo (OBDA) y la aceleración dinámica vectorial (VeDBA).

También fueron usadas en el trabajo _Thanks to repetition, dustbathing detection can be automated combining accelerometry and wavelet analysis_ (ETH-23-0086) que se encuentra en proceso de revisión para ser publicado en la revista _Ethology. International journal of behavioural biology_, donde se utilizó principalmente la información obtenida del análisis wavelet (columnas: Pow-X, Pow-Y, Pow-Z) (explicado con mayor detalle en el [informe](https://github.com/rofonseca/Doctorado-Reunion_Anual/blob/main/Informe_CA_2023_FONSECA.pdf) de avance del segundo año de doctorado de la Lic. **Rocio Guadalupe Fonseca**).

Las databases originales aqui cargadas contienen la información organizada de la siguiente forma:
* Time: columna que contiene la información temporal en que fue medido cada dato.
* Axis-X, Axis-Y, Axis-Z: cada una de las columnas contiene la medición de aceleración en su correspondiente eje medida por el acelerómetro.
* DBA-X, DBA-Y, DBA-Z: Cada una de las columnas contiene la aceleración dinámica de cada eje siguiendo lo propuesto por (Collins et al., 2015).
* POW-X, POW-Y, POW-Z: Cada una de las columnas contiene la información obtenida del análisis wavelet propuesto por este equipo de trabajo ([informe](https://github.com/rofonseca/Doctorado-Reunion_Anual/blob/main/Informe_CA_2023_FONSECA.pdf)).
* Otros, Sacudida, Reproductivo, Higiene, Baño de arena: Cada una de las columnas contiene información de un tipo de comportamiento específico que fue medido en el experimento siguiendo lo propuesto por (Barberis et al., 2023).

  Con esta información y las funciones que estan en este reposotorio se puede agregar información a cada una de las bases de datos como la siguiente:
  * Time Video, Time Video 2: brindan información de la hora que se observa en el video con horas, minutos, segundos y fraciones de segundos o con horas, minutos y segundos segun sea la columna Time Video o Time Video 2.
  * Estatica-X, Estatica-Y, Estatica-Z: Cada una de las columnas contiene la información de la aceleración estática de cada eje.
  * ODBA, VeDBA:  Cada una de las columnas contiene la información de la aceleración dinámica general del cuerpo y la aceleración dinámica vectorial.
  * Otros comportamientos no medidos: En este caso la database tendrá una columna con el nombre del comportamiento como encabezado y toda la columna tendrá NaN's para indicar que el comportamiento no fue medido en el experimento.

Tambien serán aprovechadas en trabajo de la señorita **María Candelaria Bosch** para entrenar diferentes modelos de aprendizaje supervisado (próximamente link al repositorio).

En este repositorio han contribuido:
- Rocío Guadalupe Fonseca
- María Candelaria Bosch
- María Victoria De La Fuente
- Florencia Cecilia Spanevello

Referencias bibliográficas:
- ALCALA, R., CALIVA, J. M., GUZMAN, D. A., FLESIA, A. G., BARTUMEUS, F., MARIN, R. H., KEMBRO, J. M. 2019. Aggressive dominance can decrease behavioral complexity on subordinates through synchronization of locomotor activities. Communications in Biology 2,467.
- GUZMAN, D. A., FLESIA, A. G., AON, M. A., PELLEGRINI, S., MARIN, R. H. y KEMBRO, J. M. 2015. Coherent and synchronized ultradian rhythms in the locomotor activity of individual adult female Japanese quail. Poultry Science Association Meeting. Louisville, Kentucky.
- COLLINS P. M., GREEN J. A., WARWICK-EVANS V, DODD S., SHAW P. J., ARNOULD J. P., HALSEY L. G.(2015).Interpreting behaviors from accelerometry: a method combining
simplicity and objectivity. Ecol Evol. 2015 Oct 2;5(20):4642-54. doi: 10.1002/ece3.1660. PMID: 26668729; PMCID: PMC4670056.
- BARBERIS, L. SIMIAN, C., MARIN, R.H. et al. The relevance of a right scale for sampling when studying high-resolution behavioral dynamics. Sci Rep 13, 13291 (2023). https://doi.org/10.1038/s41598-023-39295-z
