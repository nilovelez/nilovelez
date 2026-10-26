# Repositorio de marca personal de Nilo Vélez

Este repositorio es donde Nilo gestiona su marca personal: perfil de WordPress.org, README del perfil de GitHub, contenido y tema de su web, bios, currículum, charlas, proyectos y fotografía.

Su objetivo es la **consistencia entre todo lo que publica**. El repo es la fuente de la verdad de **dónde está cada cosa**: no lo guarda todo, sino la versión canónica de cada elemento o un resumen con referencias a dónde está el detalle. De ahí se derivan las versiones para cada canal (web, LinkedIn, perfil de WordPress.org, bio para una charla, artículo de lo hecho en el año…).

## Estado actual

La estructura de carpetas está creada, aún sin contenido. El contenido se procesa poco a poco, a partir de material que Nilo ya tiene, y cada plantilla y sus campos se definen al procesar el primer contenido de su tipo, no antes en abstracto. La lista de elementos, las decisiones tomadas y lo aparcado están en `elementos.md`. `rediseno-nilovelez.md` es el plan de rediseño de la web, un subproyecto que pasará a `web/rediseno.md`.

## Forma de trabajar

- **Se habla antes de tocar.** Mientras se discute algo, no se crean ni modifican archivos hasta que Nilo lo indique.
- **Una pregunta cada vez.** Nada de baterías de preguntas.
- **Lo aparcado se queda aparcado** hasta que Nilo lo retome. Se apunta en `elementos.md`.

## Privacidad y publicación

- Es el repo del perfil de GitHub (`nilovelez/nilovelez`), así que **todo lo que se publica es público**.
- Se trabaja en la copia local. **No se hace commit ni push sin que Nilo lo pida**: él decide qué se publica y cuándo.
- El contenido terminado se puede publicar, pero no todo lo que se habla ni todos los datos que Nilo pasa. Si algo es solo para la memoria del perfil, él lo dirá; en caso de duda, preguntar antes de dejarlo en un archivo del repo.
- Lo privado pero online (backlog de contenido pendiente…) vive fuera del repo, en servicios privados (Notion, Google Sheets). El repo solo dice dónde está.
- Audios y vídeos (podcasts, grabaciones de charlas, entrevistas) se guardan en el almacenamiento local de Nilo (NAS); el repo solo los referencia.

## Idioma

Todo en **español de España**, salvo el contenido con otro idioma original (artículos, entrevistas), que se guarda tal cual.

Tono de los textos de Nilo: primera persona, cercano, con algo de humor, sin exageraciones. Usa "moderador de traductores" en vez de "GTE".

## Formato

- **Un archivo Markdown por elemento**, con datos estructurados en la cabecera (frontmatter YAML) y texto libre debajo.
- **Un campo vacío significa pendiente.** No rellenar con suposiciones: si no se sabe un dato, se deja vacío.
- **Compatible con Obsidian**: el repo entero es la bóveda. Las carpetas que no son notas (código, scripts) se excluyen en `.obsidian/app.json` (`userIgnoreFilters`).
- **Enlaces internos con `[[ ]]`.** En la cabecera, entre comillas: `evento: "[[evento-wordcamp-madrid-2023]]"`.
- **Los enlaces van en un solo sentido**: la pieza apunta a su evento, y el evento no repite sus piezas, porque Obsidian las muestra como enlaces entrantes.

### Nombres de archivo

- Únicos en todo el repo, en minúsculas, sin tildes y con guiones.
- Con **prefijo de tipo**: `evento-`, `charla-`, `galeria-`, `proyecto-`, `etapa-`, `reconocimiento-`, `equipo-`, `entrevista-`, `articulo-`, `bio-`.
- Los archivos únicos (`cuentas.md`, `mapa.md`) no llevan prefijo.
- **Charlas**: slug a partir del título (`charla-esta-no-es-la-charla-de-seguridad`). Cada vez que se da es una entrada nueva; si el título se repite, sufijo con el año o el sitio. Si el evento no tiene ficha, `evento` vacío y el sitio como texto en `lugar`.
- Al crear una nota, usar la plantilla de su tipo en `plantillas/`, cuando exista.

## Estructura prevista

```
README.md                    ← README del perfil de GitHub
CLAUDE.md
identidad/   bio/, imagen/, cuentas.md
trayectoria/ etapas/, reconocimientos/
comunidad/   equipos/, eventos/, charlas/
obra/        proyectos/, galerias/, entrevistas/, articulos/
web/         tema/ (código, excluido en Obsidian), paginas/, mapa.md, rediseno.md
vistas/      tablas de Bases (.base) para seguimiento y consultas
plantillas/  una plantilla por tipo de nota
```

Cada carpeta tiene una nota índice con su mismo nombre (`charlas/charlas.md`) que explica qué va en ella y cómo se nombran sus notas; es la referencia de esa carpeta, y hay que mantenerla al día si cambia su uso. Así además git conserva las carpetas vacías. La estructura es un punto de partida y se ajusta según se mete contenido.

## Seguimiento de publicación

Publicar una pieza son tareas independientes que se desbloquean según llega cada cosa (por ejemplo, en una charla: diapositivas en Speaker Deck, vídeo de WordPress.tv copiado y subido a YouTube, artículo en la web). El seguimiento sale de los campos vacíos de cada nota y se consulta con las vistas de `vistas/`.

## Obsidian y git

- Nilo edita en Obsidian y hace commit y push a mano.
- **Antes de modificar archivos, mirar `git status`** para no pisar cambios de Nilo sin guardar.
- Obsidian reescribe archivos de `.obsidian/` al usarlo (zoom del grafo, ventanas). No revertir esos cambios.
