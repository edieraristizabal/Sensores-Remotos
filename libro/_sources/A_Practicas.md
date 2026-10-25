# Prácticas y talleres del curso

Los capítulos del libro usan datos sintéticos para que todo se pueda ejecutar sin cuentas ni descargas. Las prácticas del curso trabajan con imágenes reales y están en la carpeta [`NOTEBOOKS`](https://github.com/edieraristizabal/Sensores-Remotos/tree/master/NOTEBOOKS) del repositorio. Varias requieren una cuenta gratuita en Google Earth Engine o en el Copernicus Data Space Ecosystem y se ejecutan mejor en Google Colab; el enlace de cada una abre el notebook directamente allí.

## Plataformas de observación de la Tierra

Complementan el capítulo {doc}`14_Plataformas_EO`.

- [Tutorial de Google Earth Engine](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/TutorialGEE.ipynb): autenticación, visualización de imágenes y mapas interactivos, compuestos sin nubes, NDVI y exportación de resultados. Se acompaña de la [guía de GEE](https://edieraristizabal.github.io/Sensores-Remotos/Guia_GEE.pdf).
- [Copernicus Browser](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/TutorialBrowser.ipynb): búsqueda, visualización y descarga de imágenes Sentinel en el navegador de Copernicus.
- [Request Builder de Sentinel Hub](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/TutorialBuilder.ipynb): construcción de peticiones a la API de procesamiento.
- [JupyterLab conectándose a openEO](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/TutorialJupyter.ipynb): cubos de datos de Sentinel-2 con openEO en el JupyterLab de CDSE.
- [Copernicus Data Space Ecosystem](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/CDSE.ipynb): acceso a los datos de CDSE desde Python.
- [Descarga de imágenes](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/DownloadImage.ipynb): selección de píxeles sin nubes en un cubo de datos y descarga del compuesto.

## Índices, umbrales y clasificación

Complementan los capítulos {doc}`11_Realce` y {doc}`12_Clasificacion`.

- [Umbrales interactivos](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/ThresholdPlayground.ipynb): exploración de umbrales sobre índices espectrales.
- [Tutorial de clasificación](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/TutorialClasificacion.ipynb): pasos para clasificar una imagen de satélite.
- [Red neuronal artificial (ANN)](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/ANN.ipynb): clasificación por píxel con una red densa.
- [Red neuronal convolucional (CNN)](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/CNN.ipynb): segmentación de imágenes con una U-Net.

## Cartografía de movimientos en masa

- [Preparación de datos](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/DataPreparationMapping.ipynb): corte de imágenes y máscaras en parches para entrenar modelos.
- [Cartografía de deslizamientos con aprendizaje profundo](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/Mapping.ipynb): entrenamiento y evaluación de una U-Net con imágenes Sentinel-2.
- [Inventario de deslizamientos con openEO](https://colab.research.google.com/github/edieraristizabal/Sensores-Remotos/blob/master/NOTEBOOKS/LandslideMapping.ipynb): compuestos antes y después de un evento, diferencia de NDVI y descarga del DEM para el posprocesamiento.

## Talleres

Los talleres evaluables del curso, en PDF, están en la carpeta [`TALLERES`](https://github.com/edieraristizabal/Sensores-Remotos/tree/master/TALLERES):

| Taller | Capítulos relacionados |
|---|---|
| [Fotogrametría](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Fotogrametria.pdf) y [cálculos fotogramétricos](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Calculo.pdf) | {doc}`06_FotografiaAerea`, {doc}`07_Fotogrametria` |
| [Anaglifos](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Anaglifos.pdf) | {doc}`06_FotografiaAerea` |
| [Fotointerpretación](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Fotointerpretacion.pdf), [criterios](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Criterios.pdf), [geomorfológica](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_FotointerpretacionGeomor.pdf) y [geológica](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_FotointerpretacionGeologica.pdf) | {doc}`08_Fotointerpretacion`, {doc}`09_Fotogeologia` |
| [Programas espaciales](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_ProgramasEspaciales.pdf) y [descarga de imágenes](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Descarga.pdf) | {doc}`04_Plataformas`, {doc}`10_Preprocesamiento` |
| [Índices](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Indices.pdf) y [tratamiento de imágenes](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Tratamiento.pdf) | {doc}`11_Realce` |
| [Clasificación](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Clasificacion.pdf) y [posprocesamiento](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_PostProcesamiento.pdf) | {doc}`12_Clasificacion` |
| [Imágenes de radar](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_Radar.pdf) | {doc}`13_SensoresActivos` |
| [Trabajo final y guía de campo](https://edieraristizabal.github.io/Sensores-Remotos/TALLERES/Taller_TrabajoFinal.pdf) | {doc}`09_Fotogeologia` |
