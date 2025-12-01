# Base de datos de referencia cloroplastidial para NAS – Plantas Neotropicales
Repositorio dedicado a la obtención, depuración y selección de Regiones Objetivo (ROIs) a partir de genomas cloroplastidiales pertenecientes a familias de plantas neotropicales, con el fin de generar archivos .bed y .fasta para su uso en Nanopore Adaptive Sampling (NAS).

## Objetivo del repositorio

- Proporcionar un pipeline reproducible para:

- Recuperar genomas cloroplastidiales representativos de familias de plantas neotropicales

- Realizar control de calidad eliminando regiones contaminantes o repetitivas

- Identificar ROIs conservadas e informativas entre taxones

- Exportar coordenadas .bed y secuencias .fasta listas para ejecución en NAS

## Flujo de trabajo general

1. Recuperación de genomas cloroplastidiales neotropicales

   ├─ Filtrado taxonómico neotropical (WCVP)

   └─ Integración con plastomas RefSeq (NCBI)

   └─ Selección final de plastomas 

3. Control de calidad y filtrado
   
   ├─ Detección de repetitivos / contaminantes
   
   └─ Enmascaramiento manual o automatizado

4. Selección de ROIs
   
   ├─ Alineamientos múltiples entre familias neotropicales
   
   ├─ Limpieza de posiciones poco informativas
   
   └─ Selección final de 5–15 ROIs por dataset

6. Exportación para NAS
   
   ├─ Coordenadas (.bed)
   
   └─ Secuencias completas (.fasta)


## Herramientas utilizadas

| Etapa                | Herramienta                     | Propósito                                               |
| -------------------- | ------------------------------- | ------------------------------------------------------- |
| Obtención de genomas | WCVP, RefSeq (NCBI)             | Búsqueda y descarga por familia neotropical             |
| Filtrado de regiones | BLASTn, RepeatMasker            | Limpieza, detección de contaminantes                    |
| Alineamientos        | Clustal Omega                   | Comparación entre taxones de la región                  |
| Depuración           | TrimAl, Gblocks                 | Eliminación de ruido y zonas ambiguas                   |
| Selección de ROIs    | BioPython                       | Identificación de fragmentos conservados e informativos |
| Exportación final    | Pipeline interno                | `.bed` + `.fasta` finales para NAS                      |

## Autoría

Stephany Collins Delgado
Base de datos creada para análisis de eDNA aerotransportado de flora neotropical mediante Nanopore Adaptive Sampling.
