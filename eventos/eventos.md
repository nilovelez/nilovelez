# Eventos

Registro completo, tipo changelog, de los eventos en los que ha participado Nilo, con sus papeles (organizador, voluntario, fotógrafo, ponente, mentor). Las ponencias y galerías enlazan a su evento desde la cabecera.

Alimenta el perfil de WordPress.org: último año en detalle, resumen de los anteriores y remisión a la web.

Nombre: `evento-<slug>`, con el slug de la URL del evento en thewp.world cuando exista (`evento-wordcamp-granada-2018`).

Campos (plantilla en `plantillas/plantilla-evento.md`):

- `categoria`: `WordCamp`, `Evento WordPress`, `Meetup` o `Evento externo` (ver «Categorías»). Vacío, pendiente.
- `comunidad`: enlace a la comunidad local que organiza el evento (`wordpress/comunidades/`), o vacío si no hay ninguna (eventos externos, eventos internacionales sin comunidad local). La heredan sus ponencias y galerías.
- `fecha`, `fecha_fin`: inicio y fin.
- `pais`: código de país de dos letras (`ES`, `PT`; `EU` para la WordCamp Europe 2021, online).
- `online`: casilla.
- `papeles`: lista con `asistente`, `ponente`, `voluntario`, `organizador`, `líder de mesa`, `fotógrafo`, `mentor`… Los papeles son genéricos; el detalle (co-líder, de qué mesa: traducciones, fotos, TV…) va en el texto de la nota del evento.
- `web`: web oficial del evento.
- `thewpworld`: página del evento en thewp.world.
- `imagen_destacada`: portada de la reseña del evento en la web (la foto de familia, por ejemplo).
- `articulo`: reseña del evento en la web (la entrada de foto y vídeo), con su papel y su punto de vista. Enlaza a las galerías y a las ponencias del evento.
- `revisada`: casilla. La reseña está al día, no con la descripción antigua.

Importados el 26/10/2026 de la sección «Let's meet in person» del perfil de Nilo en [thewp.world](https://thewp.world/presser/nilo-velez/), que él rellena a mano. En el origen, un evento sin iconos significa que solo asistió.

## Categorías

Cada evento lleva una de estas cuatro categorías. La que decide es **quién lo organiza y qué marca puede usar**, no el formato (un evento WordPress puede ser presencial, online, un concurso o un día de contribución).

- **WordCamp:** evento organizado como WordCamp, con el nombre, la marca y el derecho a usarla. Tiene su web en `*.wordcamp.org`.
- **Evento WordPress:** evento oficial de WordPress que no es una WordCamp. Al ser oficial, puede usar la marca WordPress. Pueden tener formatos distintos: los WordPress Day (Málaga, Sevilla…), el WordPress Day for AI de Faro, el Summer Photo Contest…
- **Meetup:** evento que organizan directamente los grupos de meetup de WordPress, desde una quedada o una charla normal hasta eventos más grandes (la moraga de Málaga, por ejemplo).
- **Evento externo:** evento organizado por fuera de la comunidad oficial, por una empresa, un ayuntamiento u otra entidad, esté relacionado o no con WordPress (la mayoría de los que frecuenta Nilo lo están). No es oficial, así que no puede usar la marca WordPress, y de ahí nombres como «WP Day» o «WP en la nube». Ejemplos: Mobile Week Alcalá, WP en la nube, WP Agency Forum.

Para decidir: ¿lo organiza la comunidad de WordPress? Si es una WordCamp, es WordCamp; si es oficial pero no WordCamp, Evento WordPress; si lo organiza un grupo de meetup, Meetup. Si lo organiza alguien de fuera, Evento externo.
