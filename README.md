# HbA1c y riesgo de diabetes: análisis exploratorio de datos NHANES

Análisis exploratorio y de modelado sobre la relación entre la hemoglobina
glicosilada (HbA1c) y variables antropométricas, clínicas y
sociodemográficas, usando datos públicos de la encuesta NHANES (National
Health and Nutrition Examination Survey, EE. UU.).

## Objetivo

Explorar qué variables se asocian con el control glucémico y el diagnóstico
de diabetes o prediabetes, evaluando en particular si medidas
antropométricas como el IMC o la circunferencia de cintura actúan como
posibles predictores, y si existen diferencias según sexo, edad o nivel
socioeconómico.

## Datos

- **Fuente:** [NHANES glycohemoglobin data](https://hbiostat.org/data),
  redistribuido por el Department of Biostatistics de Vanderbilt University
  ([biostat.app.vumc.org/wiki/bin/view/Main/DataSets](https://biostat.app.vumc.org/wiki/bin/view/Main/DataSets)).
  Datos públicos, anonimizados y de libre acceso.
- **Tamaño:** 6795 observaciones, 20 variables (demográficas,
  antropométricas, bioquímicas y de diagnóstico de diabetes).
- El archivo `data/nhgh.tsv` no se incluye en este repositorio por tamaño;
  descárgalo desde la fuente citada y colócalo en `data/` antes de ejecutar
  el análisis.

## Metodología

1. Prospección y preparación de los datos (missing values, tipado de
   variables).
2. Análisis exploratorio descriptivo y gráfico.
3. Inferencia estadística y simulación.
4. Modelos de regresión (lineal y logística) para identificar variables
   asociadas al diagnóstico de diabetes/prediabetes.
5. Visualización de resultados.

## Resultados principales

- La circunferencia de brazo y cintura, el pliegue subescapular, la edad y
  el nitrógeno ureico en sangre muestran una asociación positiva con el
  diagnóstico de diabetes/prediabetes.
- La obesidad se asocia claramente con una mayor prevalencia de diabetes.
- El nivel de ingresos no muestra una asociación clara con el control
  glucémico.
- Limitaciones: al ser un estudio transversal, no permite establecer
  relaciones causales; sería necesario un modelo multivariante ajustado por
  factores de confusión.

## Cómo ejecutarlo

```r
# Paquetes necesarios
install.packages(c("readr", "ggplot2", "dplyr"))

# Colocar nhgh.tsv en data/ y luego:
rmarkdown::render("analysis.Rmd")
```

También puedes ver el análisis ya ejecutado, sin necesidad de instalar R,
abriendo `analysis.html` (descárgalo y ábrelo en el navegador; GitHub no
renderiza HTML directamente).

## Autoría

Trabajo realizado en colaboración con Sofía Silva Carbajales, como parte
del Máster en Bioinformática y Bioestadística (UOC–Universidad de
Barcelona).

## Tecnologías

R · tidyverse (readr, dplyr, ggplot2) · R Markdown
