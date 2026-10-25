# CLAUDE.md

Guía para Claude Code (y para cualquier persona) que actualice este repositorio. **Cada cambio que se haga en el repositorio debe registrarse al final, en "Registro de cambios".**

## Qué es

Curso **Sensores Remotos** (Universidad Nacional de Colombia, sede Medellín, Prof. Edier Aristizábal). Un solo repositorio contiene tres productos:

| Producto | Fuente en `master` | URL publicada |
|---|---|---|
| Página del curso (Jekyll, tema minimal) | `index.md`, `_config.yml`, programa en PDF | https://edieraristizabal.github.io/Sensores-Remotos/ |
| Diapositivas (Reveal.js) | `html/01_SensoresRemoto.html` y sus recursos en `html/` | https://edieraristizabal.github.io/Sensores-Remotos/html/01_SensoresRemoto.html |
| Libro (Jupyter Book 1.x) | `libro/` | https://edieraristizabal.github.io/Sensores-Remotos/libro/ |

Remoto: https://github.com/edieraristizabal/Sensores-Remotos

## Resumen del contenido

En los últimos años, los satélites de observación de la Tierra han generado grandes cantidades de datos geoespaciales que están disponibles gratuitamente para la sociedad y los investigadores en Geociencias y otras ramas interesadas en la observación y monitoreo del planeta Tierra.  Este escenario plantea desafíos para las infraestructuras de datos espaciales a la hora de almacenar, procesar, diseminar y analizar adecuadamente estos grandes conjuntos de datos. Para satisfacer estas demandas, se han propuesto y desarrollado plataformas para la gestión y el análisis de grandes datos de observación de la Tierra.

El libro (Sensores remotos para geociencias) se creó en 2026 a partir de las presentaciones (`html/`, `CLASES_TEX/`, `Clases_PPTX/`) y de los libros guía (`LIBROS GUIA_sensores remotos/`, `LIBROS GUIA_fotointerpretacion/`). Tiene 14 capítulos en tres partes (fundamentos físicos; fotografía aérea y fotointerpretación; imágenes de satélite) más el apéndice `A_Practicas.md`, que enlaza los notebooks de `NOTEBOOKS/` (abren en Colab) y los talleres de `TALLERES/`. Cada capítulo es un notebook ejecutable que solo usa numpy, scipy, matplotlib y scikit-learn con datos sintéticos (sin descargas ni cuentas), y se publica con las salidas guardadas. Los `.ipynb` son la fuente: para cambiar un capítulo se edita el notebook y se vuelve a ejecutar localmente (`jupyter nbconvert --to notebook --execute --inplace libro/NN_*.ipynb`, por ejemplo con el entorno `geospatial` de miniconda) antes del commit, porque la Action no ejecuta. Referencias en `libro/references.bib` (citas con {cite}); `libro/requirements-notebooks.txt` lista las librerías de los capítulos.

Contenido del libro (orden de `libro/_toc.yml`; el título es el primer encabezado de cada archivo):

- `intro`: Sensores remotos para geociencias

**Fundamentos físicos**

- `01_Introduccion`: Introducción a los sensores remotos
- `02_Radiacion`: Radiación electromagnética
- `03_Interaccion`: Interacción con la atmósfera y con la superficie
- `04_Plataformas`: Plataformas, órbitas y sensores
- `05_Resolucion`: Resolución de los sensores

**Fotografía aérea y fotointerpretación**

- `06_FotografiaAerea`: Fotografía aérea y visión estereoscópica
- `07_Fotogrametria`: Fotogrametría: escala, desplazamiento del relieve y paralaje
- `08_Fotointerpretacion`: Criterios de fotointerpretación y lectura del relieve
- `09_Fotogeologia`: Fotogeomorfología y fotogeología

**Imágenes de satélite**

- `10_Preprocesamiento`: Preprocesamiento: correcciones geométricas y radiométricas
- `11_Realce`: Realce, índices y transformaciones
- `12_Clasificacion`: Clasificación de imágenes y evaluación de la exactitud
- `13_SensoresActivos`: Sensores activos: radar, InSAR y LiDAR
- `14_Plataformas_EO`: Plataformas de observación de la Tierra y cubos de datos

**Apéndices**

- `A_Practicas`: Prácticas y talleres del curso
- `bibliografia`: Bibliografía

## Ramas: dónde hacer pull y push

**Siempre se trabaja en `master`.** Ese es el único lugar donde se edita, se hace `git pull` y `git push`, tanto para cambios de la página como de las diapositivas o del libro.

**Nunca editar ni hacer push a `gh-pages` a mano.** Esa rama la genera el workflow `.github/workflows/deploy.yml` en cada push a `master`: construye Jekyll en `_site/`, construye el libro y lo copia en `_site/libro/`, y publica todo en `gh-pages` con `force_orphan` (cualquier cambio manual en `gh-pages` se pierde en el siguiente despliegue).

GitHub Pages sirve un solo sitio por repositorio; por eso la página y el libro se combinan en el Action. En **Settings → Pages** la fuente debe ser *Deploy from a branch*, rama `gh-pages`, carpeta `/ (root)`.

Flujo normal:

```bash
git pull origin master
# ... editar ...
# ... agregar una línea al Registro de cambios de este archivo ...
git add -A
git commit -m "Descripción del cambio"
git push origin master      # el Action publica en 2 a 5 minutos (pestaña Actions)
```

## Estructura

```
.github/
    workflows/
.gitignore
Guia_GEE.pdf
NOTEBOOKS/
Programa_SensoresRemoto.pdf
Programa_SensoresRemoto.tex
README.md
TALLERES/
    Imagenes/
    build/
_config.yml
_layouts/
    default.html
html/
    .github/
    01_SensoresRemoto.html
    02_Fotointerpretacion.html
index.md
libro/
```

Material fuente que **no** se sube (libros guía, presentaciones originales, documentos con derechos): está en `C:\Users\edier\Documents\CATEDRA\SENSORES REMOTOS`, fuera de este repositorio.

## Cómo actualizar

**Página del curso.** Editar `index.md`. Los enlaces internos deben ser relativos (`Programa.pdf`, `html/...`), nunca empezar por `/`, porque el sitio vive en `/Sensores-Remotos/`. El libro se enlaza como `https://edieraristizabal.github.io/Sensores-Remotos/libro/<capítulo>.html`. Si cambia la evaluación, actualizarla también en el programa (`.tex` + PDF) y en las diapositivas.

**Diapositivas.** Editar `html/01_SensoresRemoto.html` directamente (Reveal.js; ecuaciones con MathJax). Previsualizar con `python -m http.server` desde la raíz y abrir `http://localhost:8000/html/01_SensoresRemoto.html`.

**Libro.** Capítulos en MyST Markdown (`.md`) o notebooks (`.ipynb`) dentro de `libro/`; un capítulo nuevo debe agregarse a `libro/_toc.yml`; las citas `{cite:t}` / `{cite:p}` deben existir en el archivo `.bib` del libro.

- **El Action no ejecuta los notebooks** (`execute_notebooks: "off"`): publica las salidas guardadas en cada `.ipynb`. Si se cambia código, ejecutar el notebook localmente y guardarlo con sus salidas antes del commit.
- `libro/requirements.txt` contiene solo lo necesario para construir el libro; `libro/requirements-notebooks.txt` (si existe) lista las librerías para ejecutar los notebooks.
- Si git falla con `bad object refs/desktop.ini` o `failed to perform geometric repack`, es porque Windows/Google Drive creó archivos `desktop.ini` dentro de `.git/`: borrarlos con `find .git -name desktop.ini -delete` y repetir el comando.
- Compilar localmente: `C:\Users\edier\.jbenv\Scripts\jupyter-book.exe build libro` y abrir `libro/_build/html/index.html`.

## Presentaciones

Hay dos presentaciones Reveal.js en `html/`: `01_SensoresRemoto.html` (sensores remotos y procesamiento de imágenes) y `02_Fotointerpretacion.html` (fotointerpretación). Usan imágenes por URL externa (no hay carpeta de imágenes local).

## Preferencias del autor

- Proponer los cambios de contenido del curso y esperar aprobación antes de editarlos.
- Prosa en párrafos, español, sin rayas (em dash): usar comas o paréntesis.
- Las figuras nuevas se buscan primero en los tableros de Pinterest del autor.

## Pendientes conocidos

- Cambiar en Settings → Pages la fuente a la rama `gh-pages` (hasta entonces sigue publicando la rama `master` sin el libro).
- `NOTEBOOKS/TutorialBrowser (1).ipynb` parece un duplicado de `TutorialBrowser.ipynb`.
- En `index.md`, los enlaces de los tutoriales de CDSE (Request Builder y JupyterLab) apuntan a notebooks cruzados (`TutorialJupyter` y `TutorialBuilder`); revisar.

## Registro de cambios

Cada cambio al repositorio se anota aquí, el más reciente primero, con el formato `- **AAAA-MM-DD**: qué se cambió y por qué (archivos principales).` Esta sección es la memoria del curso entre sesiones: leerla antes de empezar a trabajar.

- **2026-10-25**: Revisión de figuras de la presentación en el navegador; se reemplazaron 99 imágenes rotas de html/01_SensoresRemoto.html (65) y html/02_Fotointerpretacion.html (34), casi todas figuras de ResearchGate que ya no permiten insertarse: 37 recuperadas del Internet Archive, 6 fotografías de Wikimedia Commons (cámara aérea, fotografías oblicuas baja y alta, fotografía vertical, estereoscopio de espejos, cuarto de Ames, fracción de nubes de MODIS), 34 figuras nuevas generadas con matplotlib, 6 miniaturas de Wikimedia con ancho no estándar corregidas, y 2 imágenes que Pinterest no acepta guardadas en el repositorio; las demás fijadas en el tablero remote-sensing de Pinterest. Las figuras generadas quedan también en `html/img/figuras/`; la presentación las enlaza desde `i.pinimg.com`.
- **2026-10-25**: `README.md` con la sección "Enlaces del curso" (página, presentación y libro publicados) y el enlace a la página personal https://edieraristizabal.github.io/.
- **2026-10-24**: Commit de respaldo de los cambios locales pendientes antes de unificar.
- **2026-10-24**: Interfaz en español: `_layouts/default.html` traducido, reemplaza el texto en inglés del tema minimal de Jekyll.
- **2026-10-24**: Revisión de idioma: traducidos al español los bloques en inglés de `html/01_SensoresRemoto.html` y `html/02_Fotointerpretacion.html` (patrones de drenaje, lectura de curvas de nivel, correcciones radiométricas, pies de figura) y unos 60 títulos de diapositivas en inglés; en `NOTEBOOKS/` se tradujeron las celdas de texto de `Mapping.ipynb` y `TutorialGEE.ipynb`, los encabezados de `CNN.ipynb` y los comentarios del código de ANN, CNN, DataPreparationMapping, DownloadImage, LandslideMapping, Mapping y TutorialGEE. Quedan en inglés los títulos de lecturas, el nombre LiDAR y los enlaces.
- **2026-10-24**: Libro nuevo en `libro/` (Jupyter Book 1.x, `language: es`, `execute_notebooks: off`): 14 capítulos ejecutables, apéndice de prácticas y bibliografía; ejecutado localmente sin errores ni advertencias y compilado sin warnings.
- **2026-10-24**: Unificación en un solo repositorio: `.github/workflows/deploy.yml` (Jekyll + Jupyter Book → `gh-pages`); `_config.yml` con `url`/`baseurl: /Sensores-Remotos` y exclusiones; en `index.md` enlaces relativos, enlace a la segunda presentación y sección del libro.
