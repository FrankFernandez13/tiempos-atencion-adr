# Cómo modificar el tablero web

Publicado en: https://frankfernandez13.github.io/tiempos-atencion-adr/

## Qué hay en la carpeta

| Archivo | Para qué sirve |
|---|---|
| `index.html` | Toda la página: estilos, textos, pestañas, filtros, cálculos y gráficos. Es el único archivo que normalmente hay que tocar. |
| `datos/*.json` | Los datos agregados (sin pacientes). **No los modifiquen**: salen del análisis y cuadran con el documento. |
| `logo.png` | Logo de Rehabilitación. |

## Cómo verlo en su computadora

El `index.html` no abre bien con doble clic, porque necesita leer la carpeta `datos`. Hay que abrirlo con un servidor local:

1. Abran una terminal **dentro de esta carpeta**.
2. Escriban: `python -m http.server 8000`
3. Abran en el navegador: http://localhost:8000

Cada vez que guarden un cambio en `index.html`, recarguen la página con **Ctrl + F5**.

## Dónde está cada cosa dentro de `index.html`

Usen **Ctrl + F** con estas palabras:

| Quiero cambiar… | Busquen |
|---|---|
| Colores (petróleo, naranja, fondo) | `--pet:` (al inicio, en `<style>`) |
| Título y subtítulo de la cabecera | `<h1>` |
| Nombres de las pestañas | `class="pest"` |
| Contenido de cada pestaña | `id="panorama"`, `id="tiempos"`, `id="diayhora"`, `id="cuellos"`, `id="inasistencia"` |
| Títulos y notas de los gráficos | `<h2>` y `class="nota"` dentro de cada pestaña |
| Tarjetas (KPI) | `class="tarjeta kpi"` |
| Cómo se calcula cada cifra | `dash.calc(` (por ejemplo `dash.calc('sel'` calcula las tarjetas) |
| Cómo se dibuja cada gráfico | `dash.draw('g-` seguido del nombre (por ejemplo `dash.draw('g-estado'`) |
| El cuadro que aparece al pasar el mouse | `A.tip =` y los estilos `.tip` |

## Reglas para no romper nada

- **No cambien las fórmulas de las cifras** (inasistencia, mediana, percentil 90, cuellos de botella) sin hablarlo con Frank: deben coincidir con el trabajo de grado.
- Si cambian un texto que nombra una cifra, verifiquen que la cifra siga siendo la del documento.
- Hagan una copia del `index.html` antes de empezar.
- Cuando terminen, **envíen su `index.html` a Frank** para que él lo integre y lo publique. No suban cambios directo al repositorio sin coordinar, porque Frank regenera la página desde su versión y se perderían.
