# Galerías

Fichas de galería con portada y enlace al álbum externo (Google Photos, Flickr). No se alojan las fotos. Cada ficha indica si es propia (Nilo es el único fotógrafo) o compartida (con otros fotógrafos). Si sale de un evento, enlaza a su ficha.

Nombre: `galeria-<slug>`. Si sale de un evento, el slug es el de su ficha sin el prefijo (`galeria-wordcamp-portugal-2026`).

Campos (plantilla en `plantillas/plantilla-galeria.md`):

- `titulo`: nombre del álbum, que suele ser el del evento.
- `evento`: enlace a la ficha del evento, si existe. Si no, el sitio va como texto en `lugar`.
- `fecha`: la del evento o, si no hay ficha, la de las fotos.
- `album`: enlace al álbum externo (por ahora, Flickr).
- `autoria`: `propia` (Nilo es el único fotógrafo) o `compartida`. Vacío, pendiente.
- `portada`: imagen de portada para la entrada de la web.
- `articulo`: entrada de la web sobre la galería.

El evento de una galería lleva el papel `fotógrafo` en `papeles`. Los eventos con ese papel y sin galería enlazada son los que faltan por publicar.

Importadas del listado de álbumes de Flickr de Nilo el 28/10/2026.
