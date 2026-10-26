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

Todo en **español de España**, salvo el contenido con otro idioma original (artículos, entrevistas), que se guarda tal cual, y la carpeta `guppy/`, que va en inglés.

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

Nilo trabaja desde varios equipos: Claude corre en Marcianito, un equipo de casa, y Nilo puede clonar el repo en otros (el portátil), editar en Obsidian, incluso sin conexión, y hacer push. Para que las versiones no se crucen:

- **Al empezar una sesión o cuando Nilo avise de cambios, `git pull`** antes de tocar nada. Mirar también `git status` para no pisar cambios sin guardar.
- **Revisar los cambios de Nilo** con `git diff` sobre la versión anterior: formatos de los campos, fechas, erratas, enlaces `[[ ]]` rotos, nombres de archivo que no sigan la convención. Si algo no cuadra, preguntar; las correcciones se proponen, no se aplican sin más.
- **No dejar trabajo a medias sin commit** al terminar una sesión, para que no se cruce con lo que Nilo edite en otro equipo. Si hay cambios pendientes, avisar a Nilo antes de terminar.
- Commit y push solo cuando Nilo lo pida (ver «Privacidad y publicación»).
- Obsidian reescribe archivos de `.obsidian/` al usarlo (zoom del grafo, ventanas). No revertir esos cambios. `workspace.json` está ignorado en git.

## Project status (Guppy)

This project publishes its status to Guppy, Nilo's project manager (https://github.com/manuelstone/guppy). Everything Guppy-related lives in `guppy/`, written in English:

- `guppy/STATUS.md`: extended status and work log, for agents working on this project. It is never synced anywhere.
- `guppy/STATUS.json`: public summary, following the status contract (https://github.com/manuelstone/guppy/blob/main/docs/status-contract.md). `.github/workflows/guppy-sync.yml` copies it to Guppy every time it changes on the default branch, and from there it goes to a public website. Never put private information, credentials or secrets in it.

At the end of every work session on the project, even if `status` stays the same:

1. Update the Status section of `guppy/STATUS.md` and add a brief entry at the top of its Log.
2. Update `guppy/STATUS.json`: change `status` if it changed, rewrite `status_text` so it says where the project stands now, and always take new `last_update` and `last_update_unix`. They record when the status was last reported, not when `status` last changed: an `active` project gets new dates after every session. Take both dates from a single timestamp: `ts=$(date +%s); date -d "@$ts" '+%Y-%m-%d %H:%M:%S %z'; echo "$ts"` (GNU date; the contract has the macOS and PowerShell versions).
3. Commit both files with the rest of the session's changes and push to the default branch.

Statuses: `active` (being worked on), `blocked` (waiting for something outside the project), `inactive` (stopped by choice), `planned` (decided, not started), `archived` (closed).

`status_text`: one or two sentences, under 200 characters, plain text. Say where the project stands and what comes next; if blocked, start with what it is waiting for and from whom. Self-contained: no relative dates, name versions and third parties. Rewrite it in full each time; the history goes in the Log.

When Nilo asks to change this project's data in Guppy (its icon, title, description or status), edit `guppy/STATUS.json` following the contract, commit and push to the default branch: the sync publishes it. A change of only the icon, title or description does not touch the dates. `icon` is any public URL, ideally a square 128×128 PNG. Never edit the Guppy repo for this.

Do not use CHANGELOG.md for this: it is for users. Do not edit `guppy-sync.yml`. If the Guppy sync action fails, read its log in the Actions tab and tell Nilo.
