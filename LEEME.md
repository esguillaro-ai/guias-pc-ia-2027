# Guías PC e IA 2027

Sitio público: https://esguillaro-ai.github.io/guias-pc-ia-2027/

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El sitio: catálogo, fichas de cada propuesta y cronograma anual. |
| `guias.json` | Las 24 propuestas con sus secuencias, roles y etapas. |
| `cronograma.json` | El cronograma anual por grado. |

El sitio es de solo lectura: quienes lo visitan no pueden cambiar nada. Los cambios se hacen editando estos archivos en el repositorio, y solo quien tiene permiso de escritura sobre el repositorio puede guardarlos.

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
