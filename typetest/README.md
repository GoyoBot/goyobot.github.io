# Google Analytics

- Loguéate en GA: <https://analytics.google.com>
- Registra tu sitio (lo llama propiedad): `http(s)://sub.dominio.com`
- En las preferencias de tu propiedad, localiza el **"ID de seguimiento"** (ej: UA-xxxxxxxxx-x)
- Insértalo en `index.html`: 

        ga('create', 'UA-xxxxxxxxx-x', 'auto');

- Una vez publicado este cambio, empezarás a recibir los datos
- La página está configurada con Eventos. Los puedes ver en:
    - **A TIEMPO REAL > Eventos** (últimos 30 min)
    - El resto los tienes en **COMPORTAMIENTO > Eventos** (todos, pero se actualiza cada 24-48 horas)
- Puedes exportar los datos a *CSV*.


# Clicky

Clicky te muestra todos los datos siempre a tiempo real.

- Loguéate: <https://clicky.com>
- Crea un sitio nuevo: `http(s)://sub.dominio.com`
- Entra en el **Sitio > Preferences > Tracking code**.
- Añádelo en `index.html` justo antes de cerrar el `</body>` (puedes quitar la primera línea que sólo incluye un enlace `<a>`). Ej:

        <script src="//static.getclicky.com/js" type="text/javascript"></script>
        <script type="text/javascript">try{ clicky.init(101100273); }catch(e){}</script>
        <noscript><p><img alt="Clicky" width="1" height="1" src="//in.getclicky.com/101100273ns.gif" /></p></noscript>

- Encontrarás los datos dentro del sitio en **Visitors > Action log**.
- Puedes exportar los datos a *CSV*.
