<div align="center">

![Investigación](https://img.shields.io/badge/INVESTIGACI%C3%93N-00695C?style=for-the-badge)

# Estructura poblacional del fletán negro en el Atlántico Norte

Modelos autorregresivos multivariantes en espacio de estados (MARSS) sobre campañas científicas para contrastar si los límites de gestión coinciden con la estructura de las poblaciones.

[![Artículo: Fisheries Management and Ecology (2023)](https://img.shields.io/badge/ART%C3%8DCULO-Fisheries_Management_and_Ecology_%282023%29-455A64?style=for-the-badge&logo=doi&logoColor=white)](https://doi.org/10.1111/fme.12639)

![R](https://img.shields.io/badge/R-276DC3?style=flat-square&logo=r&logoColor=white) ![MARSS](https://img.shields.io/badge/MARSS-276DC3?style=flat-square)

<img src="https://user-images.githubusercontent.com/93770563/153774866-491194e7-8b12-443a-b48c-64c402e4411b.png" alt="Mapa de las áreas de muestreo de las campañas de arrastre de fondo en el Atlántico Norte" width="100%" />

<sub>Áreas de muestreo de las campañas científicas.</sub>

</div>

---

## Descripción general

El fletán negro (*Reinhardtius hippoglossoides*) se gestiona en el Atlántico Norte como stocks separados. Conocer la estructura real de las poblaciones permite gestionarlas mejor.

Este repositorio contiene el código, los datos de las campañas y las figuras del artículo **Úbeda et al. (2023)**, del que soy primer autor: *Using multivariate autoregressive state-space models to examine stock structure of Greenland halibut in the North Atlantic*, *Fisheries Management and Ecology*, 30(5), 521–535. [DOI](https://doi.org/10.1111/fme.12639) · [copia pública en el repositorio de NOAA](https://repository.library.noaa.gov/view/noaa/51175).

## Contenido

**Series temporales** de campañas de arrastre de fondo (1996–2019):

| Stock | País | Campaña | Zona | Serie |
| :---: | :---: | :---: | :---: | :---: |
| Ártico Nororiental (NEA) | Noruega | Talud noruego | Subáreas ICES 1 y 2 | 1996–2019 |
| Nórdico Occidental (WN) | Islandia | Islandesa | Subáreas ICES 5, 6 y 12 | 1996–2019 |
| Nórdico Occidental (WN) | Groenlandia | Groenlandia oriental | Subdivisión ICES 14b | 1998–2017 |
| Noroeste Atlántico (NWA) | Groenlandia y Canadá | Groenlandia occidental y Canadá | NAFO 1CD + 0A-Sur | 1997–2019 |

**Hipótesis de estructura** (Z) comparadas, combinando las series de Groenlandia occidental y Canadá (WGR), Groenlandia oriental (EGR), Islandia (ICE) y el talud noruego (NEA):

| Nº | Escenario | Agrupación de las series |
| :---: | --- | --- |
| 1 | Una población | WGR-EGR-ICE-NEA |
| 2 | Delimitación actual | WGR · EGR-ICE · NEA |
| 3 | Tres poblaciones | WGR · EGR · ICE-NEA |
| 4 | Tres poblaciones | WGR-ICE · EGR · NEA |
| 5 | Dos poblaciones | WGR · EGR-ICE-NEA |
| 6 | Tres poblaciones | WGR · EGR-NEA · ICE |
| 7 | Dos poblaciones | WGR-ICE · EGR-NEA |
| 8 | Dos poblaciones | WGR-EGR · ICE-NEA |
| 9 | Cuatro poblaciones | WGR · EGR · ICE · NEA |

Las alternativas incluyen distintos niveles de complejidad y covariables para estudiar el efecto del clima (índice NAO) y de la pesca.

## Tecnologías y herramientas

| Ámbito | Herramientas |
| --- | --- |
| Modelos | R, paquete [MARSS](https://cran.r-project.org/package=MARSS) |
| Figuras | R (ggplot2); estratos de muestreo con RstoxStrata |

## Estructura del proyecto

```text
.
├── 1.Data/              # Series de las campañas y capas de los estratos de muestreo
├── 2.Scripts/           # MARSS model_run-script.R (ajuste) y MARSS_MS_Figures.R (figuras)
├── 3.Figures_Graphs /   # Hipótesis, covariables, diseños de muestreo y modelos mejor ajustados
├── 4.Outputs/           # Resultados de los modelos
├── 5.Papers/            # Artículo
└── 6.Literature/
```

## Instalación y uso

Con R y el paquete MARSS instalados:

```r
install.packages("MARSS")
source("2.Scripts/MARSS model_run-script.R")
source("2.Scripts/MARSS_MS_Figures.R")
```

## Resultados

- Los modelos mejor respaldados no agrupan Groenlandia oriental con Islandia, como se gestiona hoy, y apoyan una posible conexión entre Islandia y el talud noruego.
- Modelos mejor ajustados en [abundancia](3.Figures_Graphs%20/Best%20fit%20models/Best-Fit-Model_ABUNDANCE.png) y [biomasa](3.Figures_Graphs%20/Best%20fit%20models/Best-Fit-Model_BIOMASS.png).
- [Caso de estudio en el portfolio](https://juliouq.github.io/Portfolio-Web---JulioUQ/es/casos/fletan-negro/).

## Aspectos técnicos destacados

- Comparación formal de nueve hipótesis de estructura poblacional con modelos en espacio de estados.
- Integración de campañas de cuatro países con diseños de muestreo distintos.
- Trabajo en equipo de siete autores (Úbeda, Nogueira, Tolimieri, Vihtakari, Elvarsson, Treble y Boje), en el que fui primer autor y autor de correspondencia.

## Autor

**Julio Úbeda Quesada** · Data Scientist

[![Portfolio](https://img.shields.io/badge/Portfolio-0B2545?style=flat-square&logo=astro&logoColor=white)](https://juliouq.github.io/Portfolio-Web---JulioUQ/es/) [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square)](https://www.linkedin.com/in/juliouq/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/JulioUQ)
