# Novantia — Página oficial

Landing hub de Novantia y landings dedicadas por servicio, para tráfico de TikTok y redes.

## Estructura

- `index.html` — landing principal (hero, beneficios, dolores comunes, servicios, cómo trabajamos, compromiso, contacto).
- `servicios/bots.html` — landing dedicada a creación de bots (WhatsApp, Telegram, web).
- `servicios/automatizaciones.html` — landing dedicada a automatización de procesos (n8n, Make, APIs).
- `servicios/sistemas.html` — landing dedicada a sistemas a medida (inventario, ventas, procesos).
- `assets/css/style.css` — estilos compartidos por las 4 páginas (paleta verde Novantia).
- `assets/img/` — logo y favicon en SVG.

## Desarrollo local

Sitio 100% estático, sin build. Para verlo localmente:

```bash
python3 -m http.server 8000
```

y abrir `http://localhost:8000`.

## Contacto

El WhatsApp de contacto (992 588 075) está enlazado en botones `wa.me` a lo largo de todas las páginas.

## Deploy en Fly.io

El sitio se sirve como estático con `nginx` dentro de un contenedor (`Dockerfile`). Desde tu máquina (no desde un sandbox sin salida a `api.fly.io`):

```bash
fly auth login
fly apps create novantia-web --org personal   # si el nombre ya existe, cambialo también en fly.toml
fly deploy
```

`fly.toml` ya está configurado (región `gru`, puerto 80, autostart/autostop de la máquina para no gastar de más). Cada deploy futuro es solo `fly deploy` de nuevo.
