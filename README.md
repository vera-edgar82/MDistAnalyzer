## MDistAnalyzer (Mismatch Distribution Analyzer)

MDistAnalyzer es un script escrito en lenguaje Python, utiliza secuencias IGHV en formato FASTA. Con ayuda del programa USEARCH genera alineamientos globales por pares de secuencias 
y elimina las comparaciones redundantes, cuantificando las diferencias (mismatch) de cada comparación y calcula las siguientes métricas: Distribución por intervalos de frecuencia relativa, la media, la asimetría, la varianza y el área bajo la curva con base a cortes de proporción de diferencias configurables por el investigador. Además, genera tablas en formato texto tabulado y gráficos para facilitar el análisis e interpretación de los resultados. El programa consta de tres funciones principales:


### Función (get_genes)

- [ ] 1. Esta función recibe como datos de entrada las secuencias IGHV en formato FASTA, obtiene los identificadores de cada secuencia y los almacena de manera temporal en una lista.

### Función (usearch)

- [ ] 2. Esta función recibe la lista de identificadores de cada secuencia y genera las combinaciones únicas por pares. Utiliza el programa USEARCH para obtener alineamientos globales con los siguientes parámetros:

usearch 
    -search_global FASTA_file 
    -db FASTA_file
    -blast6out test.aln 
    -fulldp 
    -strand plus 
    -id 0.4

Nota: Estos parámetros se pueden ajustar según el criterio de cada análisis.

El archivo de salida llamado "test.aln", contiene todos los alineamientos entre las secuencias del archivo FASTA. 

Finalmente, seleccionan los alineamientos de las comparaciones no redundantes (únicas).

### Función (relative_frequency)

- [ ] 3. Esta función obtiene la distribución de frecuencias con base a los intervalos definidos, los cuales son configurables por el investigador.

intervalos = 0, 0.05, 0.1, 0.15, 0.2, 0.25, 0.3, 0.35, 0.4, 0.45, 0.5, 0.55, 0.6, 0.65, 0.7, 0.75, 0.8, 0.85, 0.9, 0.95, 1.0