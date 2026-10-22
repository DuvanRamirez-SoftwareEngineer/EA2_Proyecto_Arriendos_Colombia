# EA2 – Proyecto integrador: Ideación, diseño y documentación de la necesidad

## Descripción
Proyecto académico para reconocer y describir el dataset público **Precios de arriendo por barrio en Colombia**, publicado por Aptología en Hugging Face. La etapa inicial incluye la carga del dataset, una revisión descriptiva básica del DataFrame y la generación automática de un resumen `.txt`.

## Necesidad analítica propuesta
En un escenario hipotético, una persona que busca arrendar un apartamento o un equipo de orientación inmobiliaria necesita una referencia descriptiva de los precios pedidos por barrio y ciudad. El proyecto propone caracterizar y comparar las medianas de arriendo mensual y la dispersión entre los percentiles 25 y 75 de los barrios incluidos en la fotografía de datos.

**Pregunta de análisis:** ¿Cómo varía la mediana mensual del precio pedido de arriendo de apartamentos entre las ciudades y los barrios incluidos en el dataset, y qué diferencias descriptivas se observan entre los percentiles 25 y 75?

El análisis es descriptivo: no predice precios, no estima el precio final de un contrato ni establece causalidad.

## Dataset
- **Nombre:** Precios de arriendo por barrio en Colombia (Aptología).
- **Repositorio Hugging Face:** `aptologia/precios-arriendo-colombia`
- **Enlace:** https://huggingface.co/datasets/aptologia/precios-arriendo-colombia
- **Configuración/subset:** `precios_arriendo_barrios`
- **Split:** `train`
- **Tamaño publicado en la ficha consultada:** 1.460 filas.
- **Fecha de la fotografía indicada por la ficha:** 2026-10-05.
- **Licencia indicada:** CC BY 4.0. Se debe atribuir a Aptología.
- **Unidad de análisis:** registro agregado por ciudad y barrio para la fotografía indicada, no un apartamento individual.
- **Fuente y metodología declaradas:** Aptología indica que recopila avisos activos de portales e inmobiliarias; se trata de precios pedidos, no necesariamente de precios pactados. Solo incluye apartamentos y barrios que cumplen el umbral de avisos que describe la ficha.

La ficha del dataset debe revisarse de nuevo si el repositorio se actualiza, porque la cantidad de registros y la fecha de corte pueden cambiar.

## Estructura del proyecto
```text
EA2_Proyecto_Arriendos_Colombia/
├── README.md
├── requirements.txt
└── AE2/
    ├── documento/
    │   └── EA2_Necesidad_Diseno_Proyecto.docx
    ├── notebooks/
    │   └── EA2_Exploracion_Arriendos_Colombia.ipynb
    ├── resultados/
    │   └── resumen_dataframe.txt
    └── src/
```

## Ejecución en Google Colab
1. Sube o abre `AE2/notebooks/EA2_Exploracion_Arriendos_Colombia.ipynb` en Google Colab.
2. Ejecuta las celdas en orden, preferiblemente con **Entorno de ejecución → Ejecutar todas**.
3. El notebook intenta cargar el subset `precios_arriendo_barrios` del repositorio de Hugging Face. Si falla el cargador de `datasets`, usa como alternativa el CSV original alojado en el mismo repositorio de Hugging Face.
4. El notebook muestra registros, dimensiones, nombres de columnas, tipos de datos y valores nulos.
5. El notebook crea `AE2/resultados/resumen_dataframe.txt` y muestra su contenido. En Colab, la carpeta se crea dentro del entorno de ejecución.
6. Antes de entregar, descarga o copia el archivo TXT recién generado y publícalo en la carpeta `AE2/resultados/` del repositorio junto con el notebook y el documento Word.

## Dependencias
Instala las dependencias con:
```bash
pip install -r requirements.txt
```
En Google Colab también puedes ejecutar la celda de instalación del notebook.

## Archivos de entrega
- Documento Word con la necesidad, pregunta, objetivos, alcance, diccionario de variables y referencias.
- Notebook Jupyter/Google Colab con código y resultados visibles después de ejecutarlo.
- Resumen `.txt` generado automáticamente a partir del DataFrame.
- Este README y `requirements.txt`.

## Limitaciones
- La tabla contiene estadísticas agregadas por barrio y ciudad; no permite inferir el precio de un inmueble específico.
- Los valores son precios pedidos y no necesariamente precios finales de contratos firmados.
- La fotografía corresponde a una fecha concreta; no debe interpretarse como una serie temporal.
- Los barrios incluidos dependen de los criterios de cobertura y número de avisos de la fuente.
- Los nombres de barrios y su clasificación dependen de cómo aparecen en los avisos.
- El proyecto no afirma que el dataset sea sintético; la ficha lo presenta como datos agregados procedentes de avisos de arriendo recopilados por Aptología.
- Antes de publicar, vuelve a ejecutar el notebook y reemplaza el TXT inicial por el generado con los datos efectivamente cargados.

## Referencias
- Aptología. *Precios de arriendo por barrio en Colombia*. Hugging Face Datasets. https://huggingface.co/datasets/aptologia/precios-arriendo-colombia
- Aptología. *Datos abiertos del arriendo en Colombia*. https://www.aptologia.com/datos-abiertos
- Hugging Face. *Load a dataset*. https://huggingface.co/docs/datasets/loading
- pandas. *Intro to data structures*. https://pandas.pydata.org/docs/user_guide/dsintro.html

## Control de versiones
Se recomienda realizar commits descriptivos, por ejemplo:
- `docs: agregar documento de necesidad y diseño`
- `feat: agregar notebook de exploración del dataset`
- `feat: generar resumen descriptivo en txt`
- `docs: completar README y dependencias`

## Estudiante: Duván Oswaldo Ramírez Duarte