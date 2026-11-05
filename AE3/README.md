# Actualización del Proyecto integrador: caracterización de precios de arriendo en Colombia

**Etapas:** EA2 (ideación, diseño y documentación) y EA3 (transformación y enriquecimiento).  
**Estudiante:** Duván Oswaldo Ramírez Duarte.  
**Fuente:** [aptologia/precios-arriendo-colombia](https://huggingface.co/datasets/aptologia/precios-arriendo-colombia)  
**Configuración:** `precios_arriendo_barrios` · **Split:** `train`.

## Pregunta de análisis

¿Cómo varía la mediana mensual del precio pedido de arriendo de apartamentos entre las ciudades y los barrios incluidos en el dataset, y qué diferencias descriptivas se observan entre los percentiles 25 y 75?

## Contenido del repositorio

```text
AE2/
  documento/
    Proyecto_Integrador_EA2_EA3_Arriendos_Colombia.docx
AE3/
  notebooks/
    AE3_Transformacion_Enriquecimiento_Arriendos.ipynb
  datos/
    (el notebook genera aquí dataset_arriendos_preparado.csv)
  resultados/
    resumen_dataframe_AE3.txt
    tabla_resultados_por_ciudad.csv
    tabla_resultados_por_barrio.csv
    tabla_dispersion_por_ciudad.csv
README.md
requirements.txt
```

## Ejecución

1. Abre el notebook de `AE3/notebooks/` en Google Colab o Jupyter.
2. Instala las dependencias de `requirements.txt` si el entorno no las tiene.
3. Ejecuta las celdas en orden. El notebook carga el dataset de Hugging Face, conserva el DataFrame original, transforma una copia, valida reglas de consistencia y calcula indicadores derivados.
4. En la sección de exportación se generan el dataset preparado y las tres tablas CSV en las carpetas `AE3/datos/` y `AE3/resultados/`. La celda posterior genera `resumen_dataframe_AE3.txt`.

## Transformaciones e indicadores

- Conversión de fecha y variables numéricas a tipos adecuados.
- Limpieza de espacios y normalización auxiliar de ciudad y barrio.
- Validación del orden `p25 <= mediana <= p75`, conteos no negativos y conteos de atributos que no excedan avisos.
- `rango_intercuartil = p75 - p25`.
- `rango_intercuartil_pct_mediana = (p75 - p25) / mediana * 100`.
- Participación de avisos con parqueadero y teléfono sobre el total de avisos.

## Resultados principales de la ejecución documentada

El DataFrame transformado contiene **1.460 filas y 16 columnas**, sin valores nulos reportados, sin duplicados exactos finales y sin registros que incumplan las reglas de consistencia verificadas. La mediana de la variable `mediana` entre registros barriales es **$2.500.000 COP/mes**; su promedio es **$3.084.562,64 COP/mes**. El rango intercuartílico derivado tiene mediana de **$944.000 COP**.

En el resumen por ciudad (mediana de las medianas barriales), Cartagena registra $3.500.000, Medellín $3.100.000 y Pereira $3.000.000. Consulta los CSV para el detalle completo.

## Interpretación y limitaciones

- Los registros son agregados por ciudad y barrio, no apartamentos individuales.
- Los valores son precios pedidos publicados y no necesariamente precios finales pactados.
- La cantidad de barrios cubiertos varía entre ciudades.
- La estadística por ciudad es la mediana de las medianas barriales; no es una mediana global de todos los apartamentos.
- El análisis es descriptivo y no permite establecer causalidad.

## Archivos de resultados

Los tres CSV y el TXT incluidos corresponden a los archivos generados/entregados para la ejecución revisada. El CSV `dataset_arriendos_preparado.csv` se produce al ejecutar el notebook; no se incluyó una copia independiente porque no fue adjuntada entre los archivos recibidos para esta revisión.

## Licencia y atribución

Consulta la ficha del dataset en Hugging Face para sus condiciones de uso y atribución: https://huggingface.co/datasets/aptologia/precios-arriendo-colombia
