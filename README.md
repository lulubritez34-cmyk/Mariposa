# El Tiempo, la Memoria y la Permanencia | Escenario multiagente

Un atardecer cálido en el Bañado La Estrella, con siluetas de palmeras caranday y lapachos, y tres humanos digitales que conversan:

- **Arthur Schopenhauer**: el tiempo lo desgasta todo; querer perdurar es vanidad.
- **Ares, el loro**: la memoria perdura por la tradición oral y la repetición.
- **Guazú, el aguará guazú**: el Bañado cambia; el tiempo es un ciclo físico de transformación.

Botón **Charla guiada**: los tres se turnan solos (9 turnos). Botón **Hablar** en cada uno: charlás vos con el micrófono.

## Publicarlo en GitHub Pages
1. Creá un repositorio público y subí **todo el contenido** de esta carpeta, con sus carpetas `personajes/` y `lib/` (**Add file → Upload files**, arrastrando las carpetas).
2. **Settings → Pages → Deploy from a branch → main → / (root) → Save**.
3. Abrí `https://TU_USUARIO.github.io/NOMBRE_DEL_REPO/` y permití el micrófono cuando lo pida.

No depende de ningún CDN: three.js y el SDK de ElevenLabs viajan en `lib/`. Solo la voz necesita internet.

## Un agente por personaje (pueden ser de cuentas distintas)
Los IDs están en `index.html`, bloque `PJ`. Para probar otros sin tocar el código: `?arthur=ID`, `?ares=ID`, `?guazu=ID`.

| Personaje | ID |
|---|---|
| Arthur | `agent_8701m4s376jmfq4tybga1q3e9ana` |
| Ares | `agent_2101m4f68aj1fh8ankzf7cwrh370` |
| Guazú | `agent_9901m5dr7r1yfarsygvhvfakh8wj` |

## Ajustes en ElevenLabs (en CADA agente, en su propia cuenta)
1. **Security → Authentication**: desactivada (agente público). Sin esto, la conexión falla.
2. **Security → Allowlist (dominios permitidos)**: vacía, o con `TU_USUARIO.github.io` (solo el dominio, sin ruta). Si la lista tiene otros dominios y falta este, el agente rechaza la conexión.
3. **Security → Overrides → First message**: activado. La página lo usa para que cada uno diga solo «Buenas.» al conectar y no su saludo largo. Si no lo activás, igual anda: el cartel avisa y cada uno dice su saludo completo.
4. **No hace falta** activar overrides de System prompt, Voice ni Language: el rol de cada uno en la charla se manda como mensaje de texto.
5. **Conversación**: duración máxima de la llamada de al menos 10 minutos. Dejá los eventos de cliente por defecto (audio, respuesta del agente, transcripción, interrupción); el movimiento de boca letra por letra usa la alineación de audio que manda el agente.
6. Cada conversación gasta créditos de la cuenta dueña de ese agente.

## Si algo falla
Sale un cartel rojo con el personaje, la etapa (figura 3D, micrófono, conexión del agente, fondo…) y el texto exacto del error. El botón **Copiar el detalle** lo copia para pegarlo.
