# Rediseño de nilovelez.com — traspaso a Claude Code

Este documento resume todas las decisiones tomadas en la fase de planificación (estructura, contenido y modelo de contenidos) para continuar el trabajo en Claude Code. Lo que está marcado como **Decidido** no hay que volver a plantearlo; lo marcado como **Pendiente** está por hacer o por confirmar.

## Contexto

- Web personal de Nilo Vélez: quién es, qué hace y qué quiere compartir. No se centra en un solo tema.
- WordPress con un **tema a medida de bloques (full site editing)**. Sin custom post types.
- Idioma: español de España. Tono: primera persona, cercano, con algo de humor ("culo inquieto", "cacharreo"), sin exageraciones.
- Nilo usa "moderador de traductores" en vez de "GTE": es lo que entiende cualquiera. No sustituirlo por jerga interna.
- La web actual bloquea el acceso automatizado (robots), así que el análisis se hizo con lo indexado en buscadores.

## Menú (Decidido)

```
Logo/nombre → portada
WordPress · Ponencias · Fotografía · Proyectos · Herramientas · Blog
```

- No hay página "Sobre mí": la portada hace ese papel.
- Contacto y redes van en el pie.
- Las cometas no tienen sección: van en sus propias webs (kiteplans.org, vientocero.com) y se mencionan en la portada y el pie.

## Modelo de contenidos (Decidido)

- **Cada sección es una categoría de entradas** (blog, ponencias, fotografía, proyectos). Ejemplo: `/ponencias/` es el archivo de la categoría.
- **Las etiquetas son transversales**: "accesibilidad" puede relacionar una ponencia con una entrada del blog.
- **Una sola categoría por entrada**; lo transversal va por etiquetas.
- **Proyectos también son entradas** (categoría `proyectos`), no páginas, para que usen etiquetas. La fecha de publicación solo sirve para ordenar; no se muestra.
- **Herramientas son páginas** (utilidades pintadas con shortcode de plugins propios).
- **Plantillas asignadas a mano** por entrada. Ej.: las ponencias usan "Entrada con video", que no muestra la imagen destacada para que el vídeo sea lo primero.
- **Patrones sincronizados con anulaciones (pattern overrides)** para la ficha de proyecto y sus botones: diseño común, textos y URLs editables por instancia.
- Listados por sección con el **bloque de consulta filtrado por categoría**.
- Feed general mezclado: aceptado. Cada categoría tiene su feed (`/ponencias/feed/`).

## Portada (Decidido)

Es el "Sobre mí". Un bloque por sección, con 2–3 frases, un elemento vivo (consulta) y un enlace. **El blog no aparece en la portada.**

1. **Presentación**: webs desde 1998, comunidad WordPress desde 2011, colaborador patrocinado por Hostinger. (Pendiente: una línea de trayectoria profesional; LinkedIn no se pudo leer.)
2. **WordPress**: traducción, Photo Directory, WordPress.tv y eventos, en versión corta.
3. **Ponencias**: frase de trayectoria + la próxima o última charla.
4. **Fotografía**: la última sesión.
5. **Proyectos**: 3–4 tarjetas destacadas.
6. **Herramientas**: las dos utilidades, una línea cada una.
7. **Cierre personal**: fotos, vídeo, cacharreo (impresión 3D, carpintería) y cometas, con enlace a la Kite Plan Base.

### Borrador de textos (aprobado en tono)

> Hola, soy Nilo Vélez. Hago páginas web desde 1998 y desde 2011 colaboro con la comunidad de WordPress, que con los años ha pasado de afición a ocupar buena parte de mi semana.
>
> Hoy soy colaborador patrocinado por Hostinger: me pagan por hacer que WordPress funcione mejor desde dentro. Trabajo sobre todo en traducción, fotografía, WordPress.tv y comunidad.

> **Lo que hago en WordPress**
> - Soy moderador de los traductores de WordPress al español de España: cada día reviso y traduzco WordPress, temas y plugins, y he contribuido a más de 3.500 proyectos.
> - Soy team rep del Photo Directory, el banco de fotos libres de WordPress.org, donde he publicado más de 850 fotos.
> - Formo parte del equipo de WordPress.tv.
> - Organizo eventos: WordCamp Sevilla, WordPress Day Sevilla y el equipo de fotografía de la WordCamp Europe, entre otros. En muchos más hago de voluntario, fotógrafo o mentor.

> **Cuando no estoy con WordPress**
> Sigo siendo un culo inquieto: hago fotos, edito vídeo y cacharreo con lo que pillo, desde la impresión 3D a la carpintería. Desde finales de los 90 mantengo la Kite Plan Base, el mayor archivo de planos de cometas del mundo.

## Sección WordPress (Decidido)

Estructura:

1. **Introducción**: por qué contribuye y cuánto (30 h/semana: 20 patrocinadas por Hostinger, 10 propias).
2. **Un bloque por equipo**, misma forma (qué es el equipo, qué hace él, una cifra, enlaces cruzados):
   - Traducción (Polyglots) → herramienta de estadísticas + charla sobre traducciones.
   - Photo Directory → su perfil del directorio + sección Fotografía.
   - WordPress.tv → herramienta del Excel + tutoriales en WordPress.tv.
   - Comunidad → 3–4 eventos destacados; el resto lo cubre el timeline.
3. **Llamada a colaborar**: "si quieres empezar a contribuir y no sabes por dónde, escríbeme" (es mentor de Credits y de eventos).
4. **Entrevistas**: bloque "Me han entrevistado" con resumen propio + cita corta + enlace al original. No copiar los artículos.
   - Hostinger: https://www.hostinger.com/blog/nilo-velez
   - Yoast Care Fund: https://yoast.com/community/care-fund/recipients/nilo-velez/
   - Podcast La taza de Amadeu (Sirvelia): https://sirvelia.mumbler.io/c/la-taza-de-nilo-velez
5. **Datos vivos**: plugin **Contributor Résumé** (https://wordpress.org/plugins/contributor-resume/).

### Contributor Résumé

- Un bloque con hasta 18 secciones activables y reordenables **por bloque**: se pueden poner varios bloques en la página, cada uno junto al texto de su equipo (traducciones junto a Polyglots, fotos junto a Photo Directory, eventos y versiones al final, cabecera con insignias y dedicación arriba).
- Los **eventos salen del timeline de actividad del perfil**, no del campo "Origin Story". El Origin Story se muestra como texto aparte.
- Todo cacheado en local; la página pública no hace peticiones externas.
- Estilo: plantillas sobrescribibles en `tema/contributor-resume/` y variables CSS `--cvr-`.
- WP-CLI: `wp cresume refresh`, `wp cresume status`, `wp cresume clear-cache`.
- **Pendiente**: probarlo en el sitio de prueba. Se espera que los eventos anteriores a ~2017 (WordCamp Sevilla 2011–2013, 2016) no salgan en el timeline.

### Origin Story (Pendiente de redactar)

Reescribir el campo del perfil de WordPress.org (https://profiles.wordpress.org/nilovelez/) como **texto narrativo**, no como lista cronológica. Debe contar lo que el timeline no recoge: descubre WordPress en 2005; lo usa años en un subdominio "hackeándolo"; 2011 voluntario en WordCamp Sevilla y primera charla «Cómo cargarse WordPress»; 2012 «WordPress y QRs en el MundoReal™»; voluntario en 2013 y 2016; paso a organizador. Decidir idioma (el perfil es para público internacional).

## Ponencias (Decidido)

- Ficha por charla: título, evento, fecha, tipo (charla, taller, flash talk, apertura), resumen, vídeo de WordPress.tv incrustado, diapositivas, enlaces relacionados.
- Archivo: próxima charla destacada arriba y el resto por año.
- URLs actuales (`/ponencias/...`) se mantienen: sin redirecciones.
- **Pendiente**: completar vídeo y diapositivas donde falten. Añadir «Aunque lo compres, no es tuyo: licencias y propiedad en la era de las suscripciones» (WordCamp Valencia, 31/10/2026).
- CTA contextual: "Escríbeme si quieres que hable en tu evento".

## Fotografía (Decidido)

- **Sesiones**: no se alojan galerías. Cada sesión es una ficha ligera con portada alojada en la web, título, fecha, lugar/evento, su papel ("fotos mías" / "fotógrafo junto a otros") y botón al álbum ("Ver en Google Photos" / "Ver en Flickr").
  - Sesiones propias → Google Photos. WordCamps → cuentas de Flickr de la comunidad.
  - Filtrable entre eventos y sesiones propias.
  - Recomendación: guardar 3–5 fotos en local en sesiones importantes por si el álbum externo se rompe.
- **Portfolio**: 15–25 fotos alojadas en la web.
- Migración: las entradas de `/foto-video/` pasan a fichas de sesión, con redirección.
- CTA opcional: "¿Necesitas fotos para tu evento?".

## Proyectos (Decidido)

- Lista lo que ha hecho o está haciendo, **en español y en su voz**. El repo y la web de cada proyecto (normalmente en inglés) explican el producto; su web explica por qué lo hizo. No duplicar.
- Ficha: imagen, nombre + una línea, estado (activo / en desarrollo / archivado), texto en primera persona (de dónde salió, qué problema resuelve, para quién), enlaces, contenido relacionado (charlas, entradas).
- **Regla de enlaces**: enlazar a lo que no caduca (web y repo), nunca a instaladores versionados ni a la Store.
  - Enlace principal con el nombre del proyecto, para cualquiera: "Web de PDF Diva".
  - Secundarios describen qué hay detrás, no la plataforma: "Código en GitHub" (no "GitHub"); en plugins, "Descargar en el directorio de WordPress".
  - Marcar los enlaces a páginas en inglés: "Web de PDF Diva (en inglés)".
- Cifras del API de wordpress.org: extra opcional para plugins, no parte de la plantilla.
- Proyectos: PDF Diva, Machete, Intentionally Blank (tema, 10.000+ instalaciones; hoy no aparece en la web), Quevedo, System Fonts, repos destacados, Kite Plan Base como tarjeta con enlace externo.
- CTA opcional: desarrollo a medida o formación.

### Borrador PDF Diva

> **PDF Diva**
> Un visor de PDF con vista del orador, para presentar un PDF como si fuera un PowerPoint.
>
> Si has pasado tiempo en la cabina de un evento, conoces la escena: cinco minutos antes de la charla, el ponente te da un pendrive y te dice «mi presentación está en PDF». Los visores de PDF tienen pantalla completa, pero no vista del orador. O el ponente presenta a ciegas, girándose para leer sus diapositivas, o duplicas pantallas y el público ve las barras del visor. *[Anécdota propia: el evento en el que dijo «esto tiene que tener solución».]*
>
> Así que hice PDF Diva. Abres el PDF, pulsas «Presentar» y la diapositiva va al proyector mientras el ponente ve en su pantalla la actual, la siguiente y un cronómetro. Usa las mismas teclas que PowerPoint, así que funciona con cualquier pasador, y pone la pantalla en negro con la B. Si se suelta un cable en mitad de la charla, la presentación sigue.
>
> Es gratuita y de código abierto, no pide cuenta ni conexión y no cambia tu visor de PDF predeterminado. Funciona en Windows, Mac y Linux.
>
> [Web de PDF Diva (en inglés)](https://pdfdiva.nilovelez.com/) · [Código en GitHub](https://github.com/nilovelez/pdf-diva/)

## Herramientas (Decidido)

- Páginas con el shortcode de cada plugin propio, una breve explicación de uso y enlace al plugin en Proyectos (y viceversa: "pruébalo aquí").
- Estadísticas de traducción y generador de Excel para WordPress.tv.
- Redirección: `/wptv` → `/herramientas/wptv/`.

## Blog (Decidido)

- **Atemporal y sin fechas, a propósito.** No proponer mostrar fechas ni avisos de antigüedad.
- No va en la portada; sí en el menú.
- Revisión entrada por entrada con criterio editorial (no automatizable: "estoy trabajando en" es temporal sin contener ninguna palabra clave):
  - **Se quedan**: las que no caducan (equivalencia APS-C/Full-Frame, carrito de Amazon…).
  - **Se reescriben**: útiles pero ancladas a un momento ("hoy ha publicado…"). Si depende de una versión, decirlo en el texto ("funciona con WordPress 6.x").
  - **Se van con redirección**: las que solo tienen sentido en su fecha (Paperman y los Oscar, comparativa de nubes con Skydrive).
  - **Se eliminan**: contenido ajeno (repost de Ben Cherry, *JavaScript Module Pattern*).
- Reducir categorías a 4–5 claras.

## CTAs contextuales (Decidido)

Patrón sincronizado con anulaciones (misma caja, texto y enlace por sección). La oferta aparece donde tiene sentido, nunca como "busco trabajo" genérico.

- Ponencias: "Escríbeme si quieres que hable en tu evento".
- Traducción: "Estoy disponible para traducir temas y plugins". (Pendiente: valorar subpágina `/wordpress/traducciones/`.)
- Fotografía y Proyectos: opcionales.

## Plugin de funcionalidades (Pendiente: escribirlo)

Plugin propio sin datos propios (desactivarlo no rompe nada). Añade una **checklist en el panel previo a publicar** del editor de bloques.

- Debe ser JavaScript en el editor (`PluginPrePublishPanel`, avisos con `core/notices`; opcional `lockPostSaving`). Un aviso PHP con `save_post` + `admin_notices` no se ve en el editor de bloques.
- Reglas:
  1. Aviso si la plantilla no es la correcta para la categoría.
  2. Aviso si falta imagen destacada donde se exige.
  3. Aviso si la entrada tiene más de una categoría (regla general).
- **No** incluir detección de referencias temporales.
- Configuración como mapa por categoría en PHP, pasado al script del editor:

```php
$reglas = [
    'ponencias'  => [ 'plantilla' => 'entrada-con-video', 'imagen' => false ],
    'proyectos'  => [ 'plantilla' => 'proyecto',          'imagen' => true  ],
    'fotografia' => [ 'plantilla' => null,                'imagen' => true  ],
];
```

- **Pendiente**: Nilo debe dar los slugs reales de categorías y plantillas.

## Redirecciones (Pendiente: inventario)

- `/wptv` → `/herramientas/wptv/`
- Entradas de `/foto-video/` → nuevas fichas de sesión.
- Entradas del blog retiradas → destino a decidir en la revisión.

## Otros detalles técnicos detectados

- Datos estructurados: el autor figura como "@NiloVelez" en vez de su nombre.
- `sameAs` solo incluye Instagram, X y YouTube; añadir GitHub, WordPress.org, WordPress.tv, Mastodon (@nilo@wptoots.social), LinkedIn.
- Títulos genéricos del tema ("Archivo de Blog").
- Cifras cambiantes (instalaciones de Machete: 7.000+ en la web, 6.000+ en wordpress.org): mejor no escribirlas a mano.

## Datos de referencia (a fecha de octubre de 2026)

- Webs desde 1998; WordPress desde 2005 (primera versión 1.5); comunidad desde 2011.
- Colaborador patrocinado por Hostinger (Five for the Future): 20 h/semana + 10 propias.
- Equipos: Polyglots, Photos (team rep), TV, Community. Editor general es_ES; traducciones en ~3.600 proyectos.
- ~860 fotos en el Photo Directory.
- Créditos en WordPress 5.5, 6.3, 6.4, 6.5 y 6.6.
- Plugins: Machete (6.000+), Quevedo, System Fonts, APS-C Crop, Machete Social Share Block. Tema: Intentionally Blank (10.000+).
- Organizador: WordCamp Sevilla, WordPress Day Sevilla, WordCamp Europe.
- Enlaces: https://profiles.wordpress.org/nilovelez/ · https://github.com/nilovelez · https://wordpress.tv/speakers/nilo-velez/ · https://www.linkedin.com/in/nilovelez · https://www.kiteplans.org/ · https://www.vientocero.com/

## Siguientes pasos sugeridos

1. Probar Contributor Résumé en el sitio de prueba.
2. Pasar los slugs de categorías y plantillas y escribir el plugin de checklist.
3. Redactar los textos de cada bloque de la portada y de los equipos de WordPress.
4. Redactar el Origin Story narrativo.
5. Inventario del blog y de `/foto-video/` y lista de redirecciones.
6. Fichas de Proyectos y páginas de Herramientas.
