(https://github.com/vera-edgar82/MDistAnalyzer/blob/main/tables/logo.png)


## MDistAnalyzer (Mismatch Distribution Analyzer)

MDistAnalyzer es un script escrito en lenguaje Python, utiliza secuencias IGHV en formato FASTA. Con ayuda del programa USEARCH genera alineamientos globales por pares de secuencias 
y elimina las comparaciones redundantes, cuantificando las diferencias (mismatch) de cada comparación y calcula las siguientes métricas: Distribución por intervalos de frecuencia relativa, la media, la asimetría, la varianza y el área bajo la curva con base a cortes de proporción de diferencias configurables por el investigador. Además, genera tablas en formato texto tabulado y gráficos para facilitar el análisis e interpretación de los resultados. El programa consta de tres funciones principales:


### Función (get_genes)

- [ ] 1. Recibe como datos de entrada las secuencias IGHV en formato FASTA, obtiene los identificadores de cada secuencia y los almacena de manera temporal en una lista.

### Función (usearch)

- [ ] 2. A través de la lista de identificadores de cada secuencia genera las combinaciones únicas por pares y utiliza el programa USEARCH para obtener alineamientos globales con los siguientes parámetros:

usearch

- [ ] search_global FASTA_file
- [ ] db FASTA_file
- [ ] blast6out test.aln 
- [ ] fulldp
- [ ] strand plus 
- [ ] id 0.4

Nota: Estos parámetros se pueden ajustar según el criterio de cada análisis.

El archivo de salida llamado "test.aln", contiene todos los alineamientos entre las secuencias del archivo FASTA. 

Finalmente, seleccionan los alineamientos de las comparaciones no redundantes (únicas).

### Función (relative_frequency)

- [ ] 3. Esta función obtiene la distribución de frecuencias con base a los intervalos definidos, los cuales son configurables por el investigador.

intervalos = 0, 0.05, 0.1, 0.15, 0.2, 0.25, 0.3, 0.35, 0.4, 0.45, 0.5, 0.55, 0.6, 0.65, 0.7, 0.75, 0.8, 0.85, 0.9, 0.95, 1.0

### Instalación y ejecución de MDistAnalyzer

- [ ] 1. Descargar el archivo genes.yml ubicado en el directorio conda_pkg, para crear un nuevo ambiente dentro de tu entorno conda, ejecutar la siguiente instrucción:

- [ ] conda env create -f genes.yml

- [ ] 2. Descargar el directorio Project que contiene los siguientes archivos:

- [ ] MDistAnalizer.ipynb
- [ ] Archivos de entrada en formato FASTA
- [ ] genome_list.txt, en este archivo se hace referencia los nombres de los archivos FASTA
- [ ] Descarga USEARCH del siguiente sitio web: https://www.drive5.com/usearch/download.html, posteriormente incorporarlo al directorio Project.

- [ ] 3. Para la ejecución del script MDistAnalizer.ipynb, es posible realizarlo a través de Visual Studio Code o Jupyter Notebook. Deberás tener activo el ambiente genes (paso 1), para que se encuentre disponible el kernel y todas las librerías y dependencias para su ejecución. El programa se ejecuta con la tecla RUN y de manera automatizada genera las tablas de texto en formato tabular y gráficos.
