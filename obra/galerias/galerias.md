# Galerías

Fichas de galería: cada una describe un álbum externo (Flickr, Google Photos) y lo enlaza. No se alojan las fotos. Una galería es de un evento, igual que una ponencia: **la reseña del evento en la web (portada, texto, enlaces a las galerías) es de la ficha del evento** (`articulo`, `imagen_destacada`, `revisada`), no de la galería. Un evento puede tener varias galerías o ninguna.

Nombre: `galeria-<slug>`. Si sale de un evento, el slug es el de su ficha sin el prefijo (`galeria-wordcamp-portugal-2026`). Cuando un evento tiene o va a tener varias galerías, cada una lleva un sufijo que las distinga (`galeria-wordcamp-europe-2022-viernes-noche`, `galeria-wordcamp-europe-2022-fiestas`).

Campos (plantilla en `plantillas/plantilla-galeria.md`):

- `titulo`: nombre del álbum, que suele ser el del evento.
- `evento`: enlace a la ficha del evento, si existe. Si no, el sitio va como texto en `lugar`.
- `fecha`: la del evento o, si no hay ficha, la de las fotos.
- `album_oficial`: enlace al álbum oficial o compartido del evento (por ahora, Flickr), con las fotos de todos los fotógrafos.
- `album_propio`: enlace al álbum con las fotos de Nilo. Ninguno de los dos enlaces es obligatorio: a menudo solo hay el oficial. Otros álbumes (viaje, evento paralelo…) van como enlaces sueltos en el texto de la ficha.
- `portada`: imagen de portada de la galería.

El texto de la ficha es una descripción corta, solo para tener localizada la galería (por ejemplo, «fotos del viernes noche, compartidas por todo el equipo de fotógrafos»).

El evento de una galería lleva el papel `fotógrafo` en `papeles`. Los eventos con ese papel y sin `articulo` son los que faltan por publicar en la web, y los que tienen `articulo` y no `revisada` conservan la descripción antigua.

Importadas del listado de álbumes de Flickr de Nilo el 28/10/2026.
