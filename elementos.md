# Elementos del repositorio de marca personal

Borrador de trabajo (local, sin publicar). Lista de lo que hay que guardar y mantener, antes de decidir estructura y formato.

## Principio

El repositorio es la fuente de la verdad de **dónde está cada cosa**. No tiene por qué guardarlo todo: para cada elemento contiene la versión canónica o un resumen con referencias a dónde está el detalle. De ahí se derivan las versiones para cada canal.

Todo lo que se publique en GitHub es público. Se trabaja en local y Nilo decide qué se publica y cuándo.

## Identidad

1. **Bio**: una general con todo y versiones preparadas por uso (ponencias, redes, profesional/LinkedIn, perfil de WordPress.org). Si cambia la general, hay que revisar las derivadas.
2. **Cuentas y perfiles**: lista de referencia con todas las cuentas y su URL. De ahí tiran la web, el README y los datos estructurados.
3. **Imagen de marca**: foto de perfil, avatar, logo… versionados en el repo, con dónde está cada uno en uso.

## Trayectoria

4. **Currículum**: línea temporal de etapas con principio y fin, que pueden solaparse. Cada etapa lleva un tipo (profesional, comunidad…) para filtrar según el destino.
5. **Reconocimientos y certificaciones**: créditos en versiones de WordPress, insignias, Yoast Care Fund, Five for the Future…

## Comunidad WordPress

6. **Equipos**: un documento por equipo con el rol, los logros y datos destacados que se actualizan (con fecha de revisión).
7. **Registro de eventos**: completo, tipo changelog. Cada evento recoge los papeles desempeñados (organizador, voluntario, fotógrafo, ponente, mentor) y cada papel apunta a su pieza (ponencia, galería). Alimenta el perfil de WordPress.org: último año en detalle, resumen de los anteriores y remisión a la web.
8. **Ponencias**: una entrada cada vez que se da (cambian las diapositivas, el lugar y la grabación), enlazada a su evento.

Ejemplo:

```
WordCamp Madrid 2023
├─ voluntario de fotografía → galería
└─ ponente → «Esta no es la charla de seguridad que quieres oír» → detalles, diapositivas, vídeo
```

## Obra

9. **Proyectos**: todo, no solo software, con fechas. Tres tipos:
   - Desarrollo: plugins, temas, apps. Explicación y enlaces (web y repo).
   - Webs: detalles y dirección. Activa → dirección enlazada; cerrada → dirección como texto, sin enlace.
   - Sueltos: proyectos que simplemente se cuentan.
10. **Fotografía**: fichas de galería con portada y enlace al álbum externo (Google Photos, Flickr). Se indica si es propia (único fotógrafo) o compartida (con otros fotógrafos).
11. **Entrevistas**: fecha, título, enlace original y texto completo como archivo. Audios y vídeos se guardan en local; el repo solo los referencia. En la web solo va un resumen con enlace al original.
12. **Artículos**: solo inventario de lo publicado y dónde.

## Seguimiento

13. **Publicación**: tareas independientes con dependencias, que se desbloquean según llega cada cosa. Debe responder qué está hecho, qué falta y qué se puede hacer ya. Ejemplo de una charla:

```
charla dada ──► ficha (fecha, evento, título) + imagen destacada
           └──► diapositivas ──► Speaker Deck (URL)
vídeo en WordPress.tv ──► copia en el NAS ──► YouTube (descripción de WordPress.tv + enlace a Speaker Deck)
imagen + YouTube + Speaker Deck ──► artículo en la web
```

14. **Backlog de contenido** (artículos, podcast, vídeos pendientes): fuera del repo, en un servicio online privado (Notion, Google Sheets…). El repo solo indica dónde está.

## Web personal

15. Sección propia:
    - El tema de bloques.
    - El contenido que solo vive en la web (por ejemplo, las páginas de herramientas, que pueden tener además su ficha en Proyectos).
    - Un mapa de qué partes de la web tiran de qué datos.

El plan de rediseño (`rediseno-nilovelez.md`) es un subproyecto de esta sección.

## Canales de salida

- Web personal.
- README del perfil de GitHub (la raíz de este repo).
- Perfil de WordPress.org.
- LinkedIn y similares.
- Bios para terceros (charlas, eventos).

### Difusión en redes con Buffer

Último paso de publicar una pieza: dejarla programada en Buffer (Bluesky, LinkedIn y X) y que la cola la dosifique. En vez de fijar cuándo sale cada cosa, se define un ritmo (un par de huecos a la semana por canal) y se van echando publicaciones; si un día salen 5 o 6 de golpe, se reparten durante el mes en lugar de salir todas hoy.

- **Flujo previsto:** Nilo avisa de que una pieza está lista, y Claude propone el texto (título como base y un gancho) y lo programa con la imagen destacada y la URL de la pieza. El texto se enseña a Nilo antes de programar. Más adelante puede ser una skill («ya está lista, mándala a Buffer»).
- **Mismo contenido en las tres redes**, con una publicación por canal.
- **Formato base:** imagen adjunta, texto y URL en el texto. La alternativa es una tarjeta de enlace (la vista previa de la web), pero no se puede combinar con imagen adjunta y X no admite tarjeta configurable. Queda abierto según cómo trate cada red el alcance; solo cambiaría el paso que construye la publicación.
- **Por defecto**, una publicación sin fecha va a la cola y toma el siguiente hueco del horario del canal. También existen «siguiente hueco» (adelantándose a la cola) y «publicar ya».
- **Plan gratuito de Buffer:** 3 canales (los tres en uso), 10 publicaciones programadas **por canal**, 1 hilo programado a la vez, 100 ideas y 1 clave de API. Suficiente para este uso.
- **Pendiente:** ajustar los horarios de cada canal (ahora X solo tiene el lunes a las 11:14).
- Los borradores de redes y la cola viven en Buffer, no en el repo.

## Decisiones de formato y estructura

- **Un archivo Markdown por elemento**, con datos estructurados en la cabecera (frontmatter YAML) y texto libre debajo. Un campo vacío indica algo pendiente.
- **Compatible con Obsidian, y el repo entero es la bóveda.** El README del perfil es una nota más. Las carpetas que no son notas (código del tema, scripts) se excluyen en `.obsidian/app.json` (`userIgnoreFilters`).
- **Enlaces internos con `[[ ]]`**, y en la cabecera entre comillas: `evento: "[[evento-wordcamp-madrid-2023]]"`. Así cuentan en el grafo y en los enlaces entrantes. Inconveniente aceptado: GitHub los muestra como texto plano.
- **El enlace va en un solo sentido**: la pieza apunta al evento, y el evento no repite sus piezas, que aparecen en sus enlaces entrantes.
- **Nombres de archivo únicos en todo el repo, con prefijo de tipo**: `evento-`, `ponencia-`, `galeria-`, `proyecto-`, `etapa-`, `reconocimiento-`, `equipo-`, `entrevista-`, `articulo-`, `bio-`. Los archivos únicos (`cuentas.md`, `mapa.md`) no llevan prefijo.
- **Las ponencias tienen slug propio a partir del título** (`ponencia-esta-no-es-la-charla-de-seguridad`). Si el título se repite, se añade un sufijo con el año o el sitio. El evento es opcional: si no tiene ficha, se deja vacío `evento` y se escribe el sitio como texto en `lugar`.
- **El seguimiento de publicación** no tiene carpeta: sale de los campos vacíos y se consulta con vistas de Bases (`vistas/*.base`).
- **Plantillas por tipo** en `plantillas/`: sirven para el plugin de plantillas de Obsidian y como referencia de campos para los agentes.
- **Commit y push a mano.** Obsidian solo edita archivos; Nilo decide qué se publica.

Árbol de carpetas (punto de partida, se ajusta al meter contenido):

```
README.md                    ← README del perfil de GitHub
CLAUDE.md                    ← convenciones del repo para agentes

identidad/
  bio/                       bio-general, bio-ponencias, bio-redes, bio-profesional, bio-wordpress-org
  imagen/                    fotos, avatar, logo + una nota con dónde se usa cada una
  cuentas.md                 lista de referencia de cuentas y URLs

trayectoria/
  etapas/                    etapa-…
  reconocimientos/           reconocimiento-…

comunidad/
  equipos/                   equipo-polyglots, equipo-photos, equipo-tv, equipo-community
  eventos/                   evento-…
  ponencias/                 ponencia-…

obra/
  proyectos/                 proyecto-…
  galerias/                  galeria-…
  entrevistas/               entrevista-…
  articulos/                 articulo-…

web/
  tema/                      código del tema (excluida en Obsidian)
  paginas/                   contenido que solo vive en la web (herramientas…)
  mapa.md                    qué partes de la web tiran de qué datos
  rediseno.md                el plan actual

vistas/                      tablas de Bases y nota con dónde está el backlog privado
plantillas/                  una plantilla por tipo de nota
```

## Aparcado

- Si el repo sustituye al Excel de seguimiento de ponencias o se alimenta de él.
- Guía de estilo con la voz de Nilo (tono, términos como "moderador de traductores" en vez de "GTE").
- Dónde encaja lo que ofrece (hablar en eventos, traducción, fotografía, desarrollo).
- Qué más contenido vive solo en la web, aparte de las herramientas.
- Qué parte de `.obsidian/` se versiona (colores, plugins, exclusiones) y cuál se ignora (estado de ventanas, zoom del grafo).
- Los campos concretos de cada tipo de nota (se definen al crear las plantillas).
