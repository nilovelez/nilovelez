# Comunidades

Un documento por comunidad local de WordPress con la que colabora Nilo, normalmente un grupo de meetup (WordPress Sevilla, WordPress Málaga, WordPress Aljarafe, Quedadas WordPress Online…). Una comunidad organiza reuniones periódicas y también eventos más grandes: la WordCamp Sevilla la organiza la comunidad de Sevilla, y la Moraga y la WordCamp Málaga 2026, la de Málaga.

Nombre: `comunidad-<comunidad>` (`comunidad-wordpress-sevilla`).

En la documentación, **comunidad** (o grupo de meetup) es la organización y **meetup** es cada reunión concreta, porque en la comunidad de WordPress se usa la misma palabra para las dos.

Las ponencias, las galerías y los eventos enlazan a su comunidad con el campo `comunidad`. Los eventos llevan la comunidad que los organiza, y las ponencias y galerías que tienen evento la heredan de él. Solo llevan `comunidad` propio cuando no tienen evento, como las charlas de una reunión periódica.

Campos (plantilla en `plantillas/plantilla-comunidad.md`):

- `titulo`: nombre de la comunidad.
- `pais`: código de país de dos letras. Vacío si es internacional.
- `web`: web oficial de la comunidad (su página de Meetup, la web de la WordCamp…).
- `imagen_destacada`, `articulo`, `revisada`: portada de la página de la comunidad en la web, la propia página, y casilla de revisión.

La WordCamp Europe y la WordCamp Asia se tratan como comunidades, aunque no sean un grupo local: reúnen a las personas que organizan cada edición, y sus ediciones son eventos con sus fotos y sus charlas.
