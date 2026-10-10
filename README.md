# 🚀 publicar-web · la lista de salida de una página web

Skill para [Claude Code](https://claude.com/claude-code) que revisa una página web **antes y después
de publicarla**, para que no salga a medias:

- **Técnico:** HTTPS, cómo se ve el link al compartirlo, favicon, sitemap, página 404, imágenes livianas.
- **Google:** lo que Google dice que sirve (y lo que no), datos del negocio para Google y el perfil de
  Google.
- **Agentes de IA:** que ChatGPT, Claude, Gemini y Perplexity puedan leer la página y recomendarla.
- **Lo legal de tu país:** datos personales, cookies, precios y, si es un negocio de comida, la carta y la
  propina.

**Primero te pregunta dónde opera tu negocio.** Las leyes cambian de país a país. Si la skill no tiene
la ficha de tu país, la investiga en fuentes oficiales, te muestra cada obligación con su enlace y separa
lo que no pudo confirmar. **No reemplaza a un abogado:** los textos legales salen como borrador para que
los revises.

> **English:** Pre- and post-launch checklist skill for Claude Code: technical basics, Google SEO,
> visibility in AI assistants (robots.txt for search bots), and the legal requirements of the country
> where the business operates, researched from official sources. Instructions are in Spanish.

## Instalarla

Abre Claude Code en la carpeta de tu proyecto y pídeselo:

```
Instala la skill de este repositorio:
https://github.com/andresarcila600/publicar-web

Copia la carpeta publicar-web del repositorio a .claude/skills/ de esta carpeta,
sin cambiarle nada.
```

A mano: botón verde **Code** → **Download ZIP**, descomprime y copia la carpeta `publicar-web` dentro de
`.claude/skills/` de tu proyecto (o de `~/.claude/skills/` para tenerla en todos).

## Usarla

- Antes de subir la página: *"voy a publicar la página, revísala con publicar-web"*.
- Ya publicada: *"ya la publiqué en https://…, revisa que quedó bien"*.

Va bien con [`web-restaurante`](https://github.com/andresarcila600/ia-restaurantes), que hace el diseño.
`publicar-web` no toca el diseño.

## Qué trae

Solo instrucciones de texto. No trae programas ni scripts, y pide permiso antes de instalar cualquier
cosa.

## Licencia

MIT ([LICENSE](LICENSE)). Hecha por Andrés Arcila.
