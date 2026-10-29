# Galerías

Fichas de galería con portada y enlaces a los álbumes externos (Flickr, Google Photos): el oficial o compartido, y el de las fotos de Nilo, que deja claro qué es suyo y qué es compartido. No se alojan las fotos. Si sale de un evento, enlaza a su ficha.

Nombre: `galeria-<slug>`. Si sale de un evento, el slug es el de su ficha sin el prefijo (`galeria-wordcamp-portugal-2026`).

Campos (plantilla en `plantillas/plantilla-galeria.md`):

- `titulo`: nombre del álbum, que suele ser el del evento.
- `evento`: enlace a la ficha del evento, si existe. Si no, el sitio va como texto en `lugar`.
- `fecha`: la del evento o, si no hay ficha, la de las fotos.
- `album_oficial`: enlace al álbum oficial o compartido del evento (por ahora, Flickr), con las fotos de todos los fotógrafos.
- `album_propio`: enlace al álbum con las fotos de Nilo. Ninguno de los dos enlaces es obligatorio: a menudo solo hay el oficial. Otros álbumes (viaje, evento paralelo…) van como enlaces sueltos en el texto de la ficha.
- `portada`: imagen de portada para la entrada de la web.
- `articulo`: entrada de la web sobre la galería.
- `revisada`: marcada cuando la entrada de la web tiene la descripción al día (no la antigua). Una cosa es que esté publicada (`articulo` relleno) y otra que esté revisada.

El evento de una galería lleva el papel `fotógrafo` en `papeles`. Los eventos con ese papel y sin galería enlazada son los que faltan por publicar.

Importadas del listado de álbumes de Flickr de Nilo el 28/10/2026.
