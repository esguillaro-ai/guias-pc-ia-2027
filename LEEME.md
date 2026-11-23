# Guías PC e IA 2027 — sitio para GitHub Pages

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El sitio: catálogo, fichas, cronograma anual y editor. |
| `guias.json` | Las 24 propuestas con sus secuencias. Las ediciones se guardan acá. |
| `cronograma.json` | El cronograma anual por grado. |
| `configurar.html` | Herramienta para generar `edicion.json`. Se usa una vez (y cuando vence la llave). |
| `edicion.json` | Lo generás vos con `configurar.html`. Contiene la llave de escritura **cifrada**. |

## Puesta en marcha

1. **Crear el repositorio** en GitHub y subir `index.html`, `guias.json`, `cronograma.json` y `configurar.html` a la raíz.
2. **Activar GitHub Pages:** *Settings → Pages → Build and deployment → Deploy from a branch*, rama `main`, carpeta `/ (root)`.
3. **Crear la llave de escritura** (token fine-grained):
   *Settings de tu cuenta → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token*.
   - **Repository access:** *Only select repositories* → solo este repositorio.
   - **Permissions → Repository permissions → Contents:** *Read and write*. Nada más.
   - **Expiration:** la que prefieras (por ejemplo, un año).
4. **Generar `edicion.json`:** abrí `configurar.html` (en el sitio publicado o en tu computadora), completá repositorio, rama, la llave, y el usuario y la contraseña de edición. Tocá *Generar* y descargá el archivo.
5. **Subir `edicion.json`** a la raíz del repositorio. Si querés, borrá `configurar.html` del repositorio (podés conservar una copia local).

## Cómo se edita

- Al pie del catálogo aparece **Acceso para edición**. Con el usuario y la contraseña correctos, cada propuesta muestra **Editar secuencia**.
- Al guardar, el sitio hace un *commit* en `guias.json`. La web pública muestra el cambio en 1 o 2 minutos.
- **Restaurar la versión de la guía** vuelve a lo extraído de los PDF (la versión original queda siempre guardada en el archivo).
- El acceso dura mientras la pestaña esté abierta. Para salir: *Acceso para edición → Salir*.

## Seguridad, en corto

- En el repositorio no queda escrito ni el usuario ni la contraseña; solo la llave cifrada con ellos (AES-256 con PBKDF2, 600.000 iteraciones).
- Sin usuario y contraseña, nadie puede guardar cambios, aunque lea todo el código.
- Usá una contraseña larga que no uses en otro lado. Quien copie `edicion.json` podría intentar adivinarla sin límite de intentos; una contraseña larga lo hace impráctico.
- Si la contraseña se filtra: revocá la llave en GitHub y generá un `edicion.json` nuevo con otra contraseña.
- Cuando la llave vence, el editor avisa al guardar. Repetí los pasos 3 a 5.
