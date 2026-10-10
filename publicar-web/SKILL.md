---
name: publicar-web
description: Revisa una página web antes y después de publicarla para que salga completa. Cubre lo técnico (HTTPS, vista previa al compartir, sitemap, 404), el SEO para Google, que la encuentren los agentes de IA (ChatGPT, Claude, Gemini, Perplexity) y lo legal del país donde opera el negocio (datos personales, cookies, precios y, en restaurantes, carta y propina). Primero pregunta dónde está el negocio; si no tiene la ficha legal de ese país, la investiga con fuentes oficiales. Úsala cuando digan "voy a publicar la página", "revisa la web antes de subirla", "ya la publiqué, revisa que quedó bien", "que salga en Google" o "que la recomiende ChatGPT".
---

# Publicar una página web: la lista de salida

No diseñas: **completas y revisas**. Si la página la armó otra skill (por ejemplo `web-restaurante`), no
cambias colores, letras ni composición; solo agregas lo que falta (etiquetas, archivos, avisos) y
avisas.

Trabajas en dos momentos:
- **ANTES de publicar:** lo que va dentro de la página (secciones A, B, C y D).
- **DESPUÉS de publicar,** con la página ya en su dominio: lo que solo se puede revisar en línea
  (sección E).

Si te llaman sin decir cuál, mira si la página ya tiene dirección en internet. Si no la sabes, pregunta.

## Paso 0 · Preguntas antes de tocar nada

Hazlas todas juntas, en un solo mensaje corto. No sigas sin las tres primeras.
1. **¿Dónde opera el negocio?** El país y, si cambia la ley por región, el estado o la provincia
   (por ejemplo, un estado de EE. UU. o de México). Es el país **donde están sus clientes**, no donde vive
   quien arma la página.
2. **¿Qué tipo de negocio es?** Si es de comida (restaurante, panadería, cafetería, bar), se activan las
   reglas de carta y propina.
3. **¿Qué tiene la página?** Puede tener uno o varios:
   - solo información;
   - botón de WhatsApp o de llamar;
   - formulario (reservas, contacto, "déjanos tus datos");
   - Google Analytics, el píxel de Meta u otra herramienta de medición;
   - venta, pedidos o pagos dentro de la página.
4. ¿Ya tiene dominio? ¿Cuál?
5. ¿Quiere que su contenido se pueda usar para **entrenar** modelos de IA? Aparecer en las búsquedas de
   las IA es otra cosa: eso queda permitido siempre. Si no sabe, se deja permitido y se le explica.

Si algo lo puedes ver en los archivos (un formulario, un script de Analytics), no lo preguntes: dilo.

## Reglas fijas

- **No inventas la ley.** Cada obligación legal va con su fuente oficial, su enlace y una cita corta
  leída de la fuente. Lo que no pudiste leer va en "No verificado", nunca mezclado con lo verificado.
- **Los textos legales son borradores.** Política de privacidad, aviso de cookies, términos: los escribes,
  se los muestras al dueño y le dices que los revise con un abogado o contador de su país antes de
  publicarlos. Solo el texto que una autoridad ordena copiar tal cual (ver la ficha del país) se copia
  sin cambiarle nada.
- **No inventas datos del negocio.** Dirección, horario, teléfono, NIT o equivalente: se los pides al dueño.
  Si no los tiene, se queda sin ellos y lo dices en el informe.
- **Lo legal no es una buena práctica ni lo bueno es ley.** En el informe separa "lo exige la ley (con
  fuente)" de "se recomienda".
- **Para instalar cualquier programa, primero pides permiso**: qué es, para qué sirve y de dónde sale.

## A · Técnico (igual en todos los países)

- [ ] `<title>` único y claro, y `<meta name="description">` corta y única en cada página.
- [ ] `<html lang="es">`, o el idioma de la página.
- [ ] Favicon.
- [ ] Vista previa al compartir el link (WhatsApp, redes): `og:title`, `og:description`, `og:image`
      (con dirección **completa**, `https://…`; si todavía no hay dominio, se completa en la sección E)
      y `og:type`.
- [ ] Todas las imágenes con texto alternativo que diga qué muestran. Comprimidas: idealmente menos de
      300 KB en `.webp`. Las que no se ven al abrir la página, con `loading="lazy"`.
- [ ] Página 404 propia, con un enlace a la página principal.
- [ ] Contraste del texto de al menos 4,5:1 y que nada se rompa a 360 px de ancho.
- [ ] Ninguna clave, token ni contraseña dentro del código de la página.
- [ ] Formulario solo si hace falta. Si lo hay: campos validados y una protección contra spam que no
      moleste (por ejemplo, un campo oculto trampa). Nada de CAPTCHA si no hace falta.

## B · Que la encuentren en Google

Google dice que lo que más pesa es el **contenido útil**, más que cualquier truco.
- [ ] La información importante está **en texto**, no en imagen ni dependiendo de JavaScript: qué vende,
      los precios si los hay, el horario, la dirección, la zona que atiende y cómo contactar.
- [ ] Títulos de sección que digan lo que hay (`<h1>` con el nombre y lo que es el negocio).
- [ ] **Datos estructurados (schema.org) en JSON-LD**, con el tipo más específico posible: `Restaurant`,
      `Bakery`, `CafeOrCoffeeShop`… o `LocalBusiness` si no hay uno mejor.
      - Obligatorios: `name` y `address`.
      - Recomendados: `telephone` (con código de país), `openingHoursSpecification`, `url`, `image`,
        `geo` (con 5 decimales o más), `priceRange` y, si es de comida, `servesCuisine` y `menu`
        (la dirección de la carta).
      - **Todo lo que pongas aquí tiene que verse igual en la página.** Si un dato no está en la página,
        no va en el schema.
- [ ] No uses `<meta name="keywords">` (Google no lo usa) ni repitas palabras clave (Google lo
      considera spam).
- [ ] **Perfil de Google (Google Business Profile):** para un negocio local pesa más que la página.
      Google ordena los resultados locales por relevancia (perfil completo), distancia y prominencia
      (qué tan conocido es, incluidas las reseñas). No lo hace la página: **díselo al dueño** y pídele
      que el nombre, la dirección y el teléfono sean iguales en el perfil, en la página y en sus redes.

## C · Que la encuentren los agentes de IA

Google dice que para aparecer en sus respuestas con IA no hace falta nada especial, aparte de lo de la
sección B. ChatGPT, Claude y Perplexity tienen sus propios lectores, y `robots.txt` decide quién entra.
- [ ] `robots.txt` que **deje entrar a los buscadores**: `Googlebot`, `Bingbot`, `OAI-SearchBot`
      (ChatGPT), `Claude-SearchBot` y `Claude-User` (Claude) y `PerplexityBot`.
- [ ] Si el dueño **no** quiere que su contenido entrene modelos, se bloquean solo los de
      entrenamiento: `GPTBot`, `ClaudeBot` y `Google-Extended`. Así no pierde visibilidad en las búsquedas.
- [ ] `Sitemap: https://<dominio>/sitemap.xml` al final de `robots.txt`.
- [ ] **No hagas `llms.txt`.** Google dice que no lo usa y no hay evidencia de que ayude a que te citen.
      Si el dueño lo pide, explícaselo.

Plantilla (se ajusta según la pregunta 5):
```
User-agent: *
Allow: /

# Si el dueño NO quiere que su contenido entrene modelos de IA:
# User-agent: GPTBot
# Disallow: /
# User-agent: ClaudeBot
# Disallow: /
# User-agent: Google-Extended
# Disallow: /

Sitemap: https://<dominio>/sitemap.xml
```

## D · Lo legal del país

1. Mira si existe `<esta-skill>/paises/<pais>.md` (por ejemplo `paises/colombia.md`). `<esta-skill>` es la
   carpeta donde está este archivo.
2. Si no existe, mira si en el proyecto ya hay `legal/<pais>.md`, de una investigación anterior. Si tiene
   menos de 6 meses, úsalo. Si es más viejo, avisa y pregunta si se actualiza.
3. Si no hay ninguno de los dos, **investiga** (abajo) y guarda el resultado en `legal/<pais>.md` del
   proyecto, con la fecha.

**Cómo se investiga un país:**
- Solo cuentan las **fuentes oficiales**:
  - el diario o boletín oficial, o el portal de leyes del gobierno;
  - la autoridad de protección de datos;
  - la autoridad de protección al consumidor;
  - la autoridad tributaria, si toca impuestos en el precio.

  Un blog de abogados sirve para orientarse, pero nunca es la fuente única de una obligación.
- Busca estos temas, y solo los que apliquen según la pregunta 3:
  1. **Datos personales:** cuándo hace falta política o aviso de privacidad y qué debe decir; si un
     formulario necesita una casilla de autorización; si hay que registrar bases de datos ante una
     autoridad, y quién está obligado.
  2. **Cookies y medición:** si Analytics o el píxel exigen aviso o aceptación previa.
  3. **Precios:** moneda, si deben incluir impuestos y cargos, y qué está prohibido (rangos, "precios en
     miles", etc.).
  4. **Si es de comida:** si la carta física es obligatoria (y si la digital la reemplaza o no);
     propina o cargo por servicio (si es voluntaria, el tope y si hay un texto obligatorio en la carta);
     si hay que avisar de alérgenos.
  5. **Si vende o recibe pedidos en la página:** qué datos del comerciante deben verse (nombre legal,
     identificación tributaria, dirección, contacto), derecho de retracto o devolución, y términos.
- Para cada obligación anota:
  - **qué exige**;
  - **cuándo aplica** (siempre, solo con formulario, solo si vende…);
  - **la norma** (nombre, número y artículo o numeral);
  - **el enlace**;
  - **una cita corta leída de la fuente**.

  Si no pudiste leer la fuente, va en "No verificado".
- Al final del archivo pon: "Investigado por IA el <fecha>. No reemplaza a un abogado del país."

**Cómo se aplica:** solo lo que corresponde a lo que tiene la página. Por ejemplo, sin formulario ni
Analytics no se agrega aviso de cookies; si se lo agregas "por si acaso", se lo dices al dueño.

## E · Después de publicar (con la página ya en su dominio)

- [ ] Abre la dirección: carga con `https://` y sin aviso de "no seguro".
- [ ] `https://<dominio>/robots.txt` y `https://<dominio>/sitemap.xml` abren bien. El sitemap tiene las
      direcciones reales.
- [ ] `og:image` y `og:url` con la dirección completa. Si es posible, prueba cómo se ve el link al
      compartirlo.
- [ ] Revisa **todos los enlaces**: que no haya rotos, que el de WhatsApp abra el número correcto y que el
      del mapa lleve al lugar.
- [ ] Una dirección que no existe muestra la página 404 propia.
- [ ] Dile al dueño que dé de alta la página en **Google Search Console** (es su cuenta, no la tuya) y
      que mande el sitemap ahí.
- [ ] **La prueba de los agentes:**
      1. Arma 5 preguntas como las haría un cliente ("¿dónde como … en <barrio/ciudad>?").
      2. Que el dueño se las haga a ChatGPT, Claude, Gemini y Perplexity **hoy y en 4 a 6 semanas**.
      3. Anoten si la página aparece, en qué puesto y qué dice el agente de ella.

      Así se sabe si funcionó. Lo que dicen los "expertos" no sirve para eso.

## El informe al terminar (corto, en lenguaje simple)

1. **La lista chuleada:** A, B, C, D y E, con ✅ hecho, ⬜ falta o ➖ no aplica (y por qué).
2. **Lo que exige la ley en <país>:** cada punto con su fuente y su enlace, y cómo quedó en la página.
3. **Lo que decide el dueño:** borradores legales que tiene que revisar, el perfil de Google, Search
   Console y si permite o no el entrenamiento de IA.
4. **No verificado:** lo que no se pudo confirmar con una fuente. Esto va al abogado o contador.
5. Las 5 preguntas de la prueba de los agentes.
