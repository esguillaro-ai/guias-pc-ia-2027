# Guías PC e IA 2027

Sitio público: https://esguillaro-ai.github.io/guias-pc-ia-2027/

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El sitio: catálogo, fichas de cada propuesta y cronograma anual. |
| `guias.json` | Las 24 propuestas con sus secuencias, roles y etapas. |
| `cronograma.json` | El cronograma anual por grado. |
| `configurar.html` | Herramienta para preparar la edición desde la web (se usa una vez). |
| `edicion.json` | Llave de escritura cifrada con el usuario y la contraseña de edición. |

Quienes visitan el sitio no pueden cambiar nada. Hay dos formas de editar:

- **Desde la web:** al pie del catálogo, *Acceso para edición* → usuario y contraseña → en cada propuesta, *Editar secuencia*. Al guardar, la web se actualiza en 1 o 2 minutos.
- **Directamente en el repositorio**, como se explica más abajo.

## Preparar la edición desde la web (una sola vez)

1. En GitHub: tu foto → Settings → Developer settings → Personal access tokens → Fine-grained tokens → *Generate new token*. Repository access: *Only select repositories* → este repositorio. Permissions → *Contents: Read and write*. Elegí un vencimiento y copiá la llave.
2. Abrí `https://esguillaro-ai.github.io/guias-pc-ia-2027/configurar.html`, completá el repositorio, pegá la llave y elegí usuario y contraseña (12 caracteres o más).
3. Descargá `edicion.json` y subilo a este repositorio (*Add file → Upload files*).

La llave queda cifrada: sin el usuario y la contraseña no se puede usar. Cuando venza, repetí estos pasos. Para cambiar la contraseña, también. Para quitar la edición desde la web, borrá `edicion.json`.

## Cómo editar una secuencia

1. Abrí `guias.json` en el repositorio y tocá el lápiz (*Edit this file*).
2. Buscá la propuesta por su `"id"` (por ejemplo `"sobre-ruedas"`). Dentro de `"detalle"` → `"etapas"` está cada etapa con:
   - `titulo`, `concepto`, `sintesisAula`, `sintesisVC`
   - `aula` → `titulo`, `detalle`, `minimos`, `optimos`
   - `vc` → `titulo`, `desafio`, `momentos` (cada uno con `nombre`, `min`, `texto`)
   - `conjuntas`, `da`, `drNecesita` (decisiones del DA y del DR)
   - `registro`, `yapa`
   - `extraVC` (semanas extra de VC) y `opcional` (`true` si la etapa es opcional)
3. Guardá con *Commit changes*. La web se actualiza en 1 o 2 minutos.

Cuidá que el archivo siga siendo JSON válido: comillas dobles, comas entre elementos y sin coma después del último. Si algo se rompe, en la pestaña *History* del archivo se puede volver a la versión anterior.

## Cómo editar el cronograma

Abrí `cronograma.json`. Cada nivel tiene `filas` (los grados) y `segs` (los bloques). Cada bloque indica la fila (`r`), la columna de inicio (`c`, contando desde 0 = marzo semana 3), cuántas columnas ocupa (`s`), el tipo (`t`: `prop`, `rep` para 〃, `ext` para *, `pres`, `vac`, `bp`, `ba`, `pa`, `cierre`), el texto (`txt`) y el color (`rosa`, `lila`, `violeta`, `azul`).
