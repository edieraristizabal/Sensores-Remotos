# Sensores remotos para geociencias

Este libro acompaña el curso de Sensores Remotos de la Facultad de Minas de la Universidad Nacional de Colombia, sede Medellín. Está escrito para estudiantes de geología e ingeniería geológica y sigue el mismo orden del curso: primero los fundamentos físicos de la teledetección, después la fotografía aérea y la fotointerpretación geológica y geomorfológica, y al final el procesamiento de imágenes de satélite, los sensores activos y las plataformas de observación de la Tierra en la nube.

Cada capítulo es un notebook de Jupyter ejecutable. El texto explica los conceptos y las celdas de código, escritas en Python con `numpy`, `scipy`, `matplotlib` y `scikit-learn`, los ponen a prueba con datos sintéticos que no requieren descargas ni cuentas en ningún servicio. Así cada figura se puede reproducir y modificar: cambiar la altura de vuelo y ver cómo varía la escala de una foto, mover un umbral y ver cómo cambia una clasificación, o deformar un terreno y ver el interferograma que produciría. Para abrir un capítulo como notebook se usa el botón de descarga o el de Colab de la barra superior.

El libro no reemplaza los textos guía del curso. Los capítulos remiten a ellos para ampliar cada tema, en especial a {cite}`chuvieco2008`, {cite}`lillesand2015`, {cite}`campbell2011`, {cite}`tempfli2009` y {cite}`ccrs` para la teledetección, y a {cite}`ray1960`, {cite}`gutierrez` y {cite}`pacheco2006` para la fotogrametría y la fotogeología. Las prácticas con Google Earth Engine, Copernicus y openEO, y los talleres del curso, se listan en el apéndice {doc}`A_Practicas`.

## Cómo está organizado

La primera parte, Fundamentos físicos, recorre la historia de la disciplina, la radiación electromagnética, su interacción con la atmósfera y con la superficie, las plataformas y órbitas de los satélites y las cuatro resoluciones de un sensor.

La segunda parte, Fotografía aérea y fotointerpretación, trata la visión estereoscópica, la geometría de la fotografía vertical (escala, desplazamiento del relieve y paralaje), los criterios de fotointerpretación y su aplicación a la fotogeomorfología y la fotogeología.

La tercera parte, Imágenes de satélite, cubre el preprocesamiento (correcciones geométricas y radiométricas), el realce, los índices y las transformaciones, la clasificación y la evaluación de su exactitud, los sensores activos (radar, InSAR y LiDAR) y las plataformas de observación de la Tierra basadas en cubos de datos.

## Recursos del curso

- [Página del curso](https://edieraristizabal.github.io/Sensores-Remotos/)
- [Diapositivas: sensores remotos](https://edieraristizabal.github.io/Sensores-Remotos/html/01_SensoresRemoto.html)
- [Diapositivas: fotointerpretación](https://edieraristizabal.github.io/Sensores-Remotos/html/02_Fotointerpretacion.html)
- [Programa del curso](https://edieraristizabal.github.io/Sensores-Remotos/Programa_SensoresRemoto.pdf)

```{tableofcontents}
```
