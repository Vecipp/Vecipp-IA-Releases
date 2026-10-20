# Novedades de Vecipp IA

Lo que trae cada versión de la CLI y del escritorio. Los instaladores están en
[Releases](https://github.com/Vecipp/Vecipp-IA-Releases/releases) y en [ia.vecipp.com/descargas](https://ia.vecipp.com/descargas).

## CLI

### CLI 1.0.20 — 2026-10-20
- **Nunca te quedas atrás**: cuando sale una versión nueva, Vecipp te lo dice en la esquina (`⬆ NEW UPDATE … · /update`) y la instala sola la próxima vez que lo abres, antes del chat, con su pantalla: la descarga con barra de progreso, la verificación, la instalación y qué trae de nuevo. Con `/update` (o un clic en el aviso) se instala ya. Si algo falla, abre la versión que tenías.
- **No pierde el hilo**: Vecipp guarda la conversación después de cada paso. Si se cierra en medio de una tarea, al abrirlo otra vez en la misma carpeta te dice que estaba trabajando y sigue desde donde iba, con todo lo que había hecho. Al interrumpirlo o escribirle mientras trabaja, tampoco pierde nada; y con los modelos del laboratorio, al retomar una conversación larga ya no se olvida de la tarea del principio.
- **Ya no se queda pegado esperando al modelo**: si el modelo deja de escribir 90 segundos aunque la conexión siga viva, Vecipp le vuelve a pedir lo mismo, con el mismo contexto, y te avisa; con cualquier modelo.
- **Auto mode que no pregunta de más**: los comandos que sólo miran (un `grep` con `|` en el patrón, un `echo` con `>` en el texto, `sed -n`, `pm2 logs`, `systemctl status`, `docker ps`, un `curl` que sólo consulta…) ya no piden permiso. Lo que de verdad cambia tu servidor sigue preguntando.
- **Una barra de abajo más delgada**: el cuadro de texto es más fino, a la derecha sólo dice `/ Commands`, y los artefactos, agentes y shells son iconos en la barra de estado (⧉ ♙ >_) que se abren con un clic, en vez de líneas debajo.
- **Imágenes con cualquier modelo**: si el modelo ve imágenes, recibe la imagen tal cual (Vecipp lo comprueba una sola vez con cada modelo y lo recuerda). Si no las ve, Vecipp te avisa y le pasa lo que leyó de la imagen con Python —el texto (también en español), los colores, las formas y los códigos QR—, y el modelo sabe que no es la imagen. La primera vez prepara ese lector (unos 2 minutos; necesita Python 3).
- **Fluida mientras escribe respuestas largas**: cuando el modelo escribe una respuesta larga con código y tablas, escribir o desplazarte responde al instante (antes una tecla podía tardar casi un segundo). Nada cambia de cómo se ve: los colores, las animaciones y el razonamiento siguen igual.
- **Ya no se congela de golpe**: detener un servidor de fondo, ver los procesos o los puertos, revisar los errores de TypeScript, mapear el proyecto o usar Python por primera vez ya no dejan la pantalla quieta unos segundos mientras trabajan.
- **Abre más rápido**: la conexión con Chrome se prepara después de mostrar la pantalla, y `/chrome` no se traba al abrirse.
- **Sesiones largas sin frenarse**: deshacer cambios, guardar la conversación y listar tus sesiones ya no se vuelven más lentos a medida que la sesión crece.
- **`@` al instante**: la lista de archivos del proyecto se prepara sola en segundo plano.
- **Pegar justo después de escribir**: las letras que escribes justo antes de pegar ya no se meten dentro de la ficha del pegado.
- **Un diseño nuevo, más limpio y ordenado**: la conversación se lee como una línea de tiempo. Cada paso es una fila con un punto —verde si salió bien, rojo si falló—, la acción, el archivo y sus cifras a la derecha (`+3 -1`); el código que cambia cuelga de una línea fina; las respuestas llevan un punto blanco y lo que pensó, uno gris. Cada turno cierra con una regla con su tiempo.
- **La línea de trabajo, como debe ser**: abajo, una sola línea con el icono de Vecipp que titila y el verbo en verde que brilla por momentos —«⌬ Forging… (23s · ↓ 673 tokens · thought for 2s)»—, sin el árbol de antes; tócala (o Alt+T) y ves su razonamiento en vivo.
- **Una portada nueva**: al abrir Vecipp ves un lobo dibujado en puntos sobre montañas, nubes y suelo, con el logo y el nombre de Vecipp en una esquina. Sin colores propios —toma el de tu terminal, clara u oscura— y más sencilla cuanto más pequeña es la ventana (en una muy pequeña, sólo el lobo). Se va con tu primer mensaje.
- **Barras más ordenadas**: arriba, tu proyecto y su rama con su nombre completo; abajo, la barra de estado en segmentos con un medidor de contexto. El logo ya no sale dos veces y los colores son más tranquilos.
- **Borrar dejando presionado funciona**: mantener Retroceso borra como debe; antes, en un equipo ocupado, no borraba y dejaba una franja negra al final de la caja.
- **La caja de texto de borde a borde**: la banda gris de abajo ya no tiene una muesca negra en el borde derecho.
- **Seleccionar con el mouse sin perder los colores**: lo que seleccionas se marca con un fondo, como en un editor; la caja, tus mensajes y los colores de los cambios ya no se ponen negros mientras arrastras.

### CLI 1.0.19 — 2026-10-19
- **Los modelos Gemini ya funcionan con todas las herramientas**: antes, una sola herramienta mal descrita hacía que Gemini rechazara cada paso en cuanto Vecipp le daba sus herramientas; ahora trabaja normal, y ve las imágenes que abre (capturas, fotos, diagramas).
- **Cambios en varios archivos de una sola vez**: un renombrado o un refactor va en un paso que apruebas una vez, y es todo o nada: si una parte no encaja, no se toca ningún archivo.
- **Prueba solo lo que cambió**: después de cada cambio corre los tests de ese archivo en segundos, en vez de todo el proyecto.
- **Deshace lo suyo**: si un enfoque salió mal, Vecipp puede deshacer sus propios cambios del turno y empezar limpio (tú sigues teniendo `/rewind` para turnos enteros).
- **Entiende tu TypeScript como el editor**: usa el TypeScript de tu proyecto para ver los errores de los archivos que tocó al instante, dónde se usa de verdad una función (sin confundirla con otra del mismo nombre) y cada lugar que cambia un renombrado.
- **Tus servidores, a otro nivel**: abre un túnel SSH a una base de datos que no es pública, deja un comando largo corriendo de fondo en el servidor y te dice cómo terminó, y despliega tu proyecto con su propio método (script deploy, deploy.sh, Fly, Vercel, Netlify, pm2) — **siempre preguntándote antes**.
- **Entiende mejor a cualquier modelo**: si un modelo manda mal los datos de una herramienta (un nombre cambiado, un número como texto, un archivo con saltos de línea mal escritos), Vecipp los corrige y sigue, en vez de fallar; y entiende los errores de Windows en español.
- **Servidores de desarrollo en Windows sin sorpresas**: arranca `npm` y `vite` supervisados y, al detenerlos, baja también lo que lanzaron (el puerto queda libre).
- **La pantalla y el teclado, bien en Windows**: hace clic donde ve aunque tengas la escala al 125 o 150 %, y escribe acentos, ñ y emoji.
- **SSH que explica**: si no conecta, dice por qué (alias que no existe, llave rechazada, servidor que no responde, llave del servidor cambiada) y qué hacer; acepta una llave o un puerto para una sola conexión.
- **Tu celular por Wi-Fi**: Vecipp puede emparejar y conectar un Android con «Depuración inalámbrica», esperar a que esté listo y reiniciarlo; mirar la pantalla, las apps o los registros ya no pide permiso.
- **Busca más rápido y lee archivos enormes**: la búsqueda en el código usa ripgrep (respeta tu `.gitignore`), lee un tramo de un archivo gigante sin cargarlo entero y, si un buscador web no responde, prueba otro.
- **Python con tu entorno**: usa el `.venv` del proyecto y, si falta un módulo, te da el `pip install` exacto (con el nombre real del paquete).
- **Subagentes con límite**: cada uno tiene un tiempo máximo y se reintenta una vez si se cae; corren de a tres como máximo.
- **Reacciona mejor cuando algo falla**: reconoce el tipo de error (un programa que falta, una ruta equivocada, un archivo bloqueado, permisos, un puerto ocupado, la red, una dependencia) y toma la salida que corresponde en vez de repetir. Si intenta otra vez exactamente lo que ya falló sin cambiar nada, se le avisa que cambie de enfoque (y tú lo ves).
- **Ediciones que aciertan**: si el texto a cambiar no está tal cual en el archivo, Vecipp ve las líneas reales más parecidas y la primera diferencia, y lo corrige a la primera; si la edición ya estaba hecha, se da cuenta.
- **Respeta los archivos de Windows**: al reescribir un archivo con finales de línea CRLF (y BOM) los conserva, así git no lo marca entero como cambiado.
- **Programa con sus herramientas a la mano**: el mapa del proyecto, buscar dónde se define y usa una función, los errores del compilador, el formateador, la revisión del cambio y el depurador ya están disponibles desde el primer mensaje.
- **Más cuidado con tus servidores y tu celular**: aunque tengas la aprobación automática, Vecipp te pregunta antes de un comando por SSH que cambie el servidor (los que sólo miran pasan solos), de escribir un archivo en el VPS, de detener o reiniciar un servicio, de desinstalar una app o borrar datos del celular, y de un `DELETE` o `UPDATE` sin `WHERE` en la base de datos. Lo que se escribe en una terminal interactiva también pide permiso.
- **Varias bases de datos a la vez, sin mezclarse**: si consultas una segunda base en la misma sesión, la consulta va a esa base (antes podía caer en la primera).
- **`verify` revisa todo en los monorepos**: en un proyecto con Turborepo corre `turbo run check build test`, sin saltarse la revisión de tipos.
- **Mucho más fluida mientras trabaja**: escribir, desplazarte o tocar algo mientras corre un comando o escribe código responde de 3 a 5 veces más rápido, y usa la mitad de procesador.
- **Sin falsas alarmas**: mientras un comando largo trabaja ya no dice «no response»; si el modelo de verdad tarda, lo dice en ámbar. Esperar un comando largo ya no se marca como fallo, y lo que sale mal va en ámbar, no en rojo.
- **El plan, una sola vez**: anclado encima mientras trabaja, sin repetirse en la conversación; y sólo para trabajos de verdad grandes.
- **Sin respuestas repetidas**: si Vecipp ya esperó a que un comando terminara, no vuelve a contártelo.
- **`/effort` ahora sí cambia algo con los modelos de Vecipp**: antes el nivel elegido no llegaba al servicio de Vecipp y siempre respondía en «medium»; ahora `low` contesta más corto y rápido y `high` piensa y escribe más.
- **Sin «tienes razón» a nadie**: si Vecipp sólo leyó y te explicó algo, ya no le pide pruebas de un trabajo que no hizo (antes a veces contestaba disculpándose por un mensaje que tú no escribiste). El chequeo sigue para cuando cambia archivos y dice que quedó listo.
- **Falla mucho menos al editar archivos**: antes, si el texto a cambiar no coincidía al carácter (un espacio o una sangría distinta) la edición fallaba y había que reintentar; ahora Vecipp tolera esas diferencias de espacios y acierta a la primera, sin tocar nada ambiguo.
- **Recuerda cómo pensó**: el razonamiento de todos los modelos (no sólo los de Anthropic) queda guardado en la sesión, para poder revisarlo y comparar.
- **`/effort` ahora con 5 niveles, como Claude**: `low · medium · high (por defecto) · xhigh · max`. El selector pinta cada nivel con un color que sube de frío a caliente (como el indicador de pensamiento), y ese mismo nivel gobierna el razonamiento de cualquier modelo que uses (también en Telegram, con botones).
- **Recuerda mejor al resumir una charla larga**: cuando el contexto se llena, Vecipp resume lo viejo de forma ordenada (objetivo, decisiones, estado, siguiente paso, archivos) y conserva los últimos turnos tal cual, para no perder el detalle reciente.

### CLI 1.0.18 — 2026-10-18
- **El plan, a la vista y sin estorbar**: mientras Vecipp trabaja, encima del verbo ves `▴ Plan 3/8 · la tarea en la que va`; un clic lo despliega. Las tareas se marcan cuando de verdad se terminan, y al acabar el plan se quita.
- **El cursor parpadea** en el cuadro de texto.
- **Lo que pensó, plegado**: al terminar, el razonamiento queda en una línea, `𓄀 Thought for 3s ▸`; un clic lo abre entero.
- **Alineado en cualquier terminal**: tu mensaje, la respuesta, lo que piensa, cada paso y los avisos empiezan en la misma columna, con el mismo espacio después de cada marca, en cualquier terminal (Vecipp mide cómo dibuja la tuya sus símbolos).
- **Ves lo que un comando cambió**: si Vecipp edita archivos con la shell (`sed -i`, un script), debajo del comando sale «Updated archivo +N -N» con el cambio, como en una edición.
- **Mira a tus agentes y shells trabajar**: bajo el prompt ves `⌬ 2 agents · ▸ 1 shell · ↓ to manage`. Con ↓, una shell te muestra su comando y su salida en vivo (x la detiene) y un agente abre su chat para que veas qué hace, paso a paso; lo que escribes sigue yendo a tu chat, Esc te devuelve y, cuando el agente termina, vuelves solo.
- **Vecipp no se olvida de lo que dejó corriendo**: si termina con una shell trabajando, cuando ella acaba Vecipp vuelve solo y te dice cómo le fue.
- **Trabaja con el método de Claude, con cualquier modelo**: lee todo lo que necesita de una vez, corre las pruebas antes de tocar nada, arregla todo y vuelve a probar, y comprueba que un test nuevo de verdad detecta el error. Y nunca toca carpetas fuera de tu proyecto.
- **Ves lo que hace mientras trabaja, como en Claude Code**: cada cambio a un archivo sale entero y en un solo bloque —lo que quitó en rojo, lo que puso en verde, con el número de cada línea—; un archivo nuevo, con sus primeras líneas (un clic lo muestra entero). Leer, buscar y ejecutar se juntan en una línea gris que un clic despliega con la salida de cada comando.
- **«Allowed by auto mode»** bajo los pasos que corrieron sin preguntarte, para que sepas por qué.
- **Tablas que se leen**: caben en tu terminal y el texto largo se parte dentro de su celda en vez de cortarse con «…». Los diagramas (`mermaid`) se dibujan con cajas y flechas, los árboles de carpetas con sus iconos y el código con colores.
- **Escribe mensajes largos tranquilo**: la franja de abajo crece y te muestra todo lo que escribes.
- **Entregas claras**: al terminar un trabajo, Vecipp te dice qué hizo, cómo lo comprobó, qué falta y, si trabajó por fases, en qué quedó cada una.
- **Aprobar es contestar una pregunta**: «¿Quieres hacer este cambio en a.txt?» con el cambio a la vista y tres respuestas — sí, sí a todas las ediciones de la sesión (shift+tab) o no y decirle qué hacer en su lugar. Igual para los comandos, las preguntas de Vecipp y el plan.
- **Pega sin miedo**: un texto largo entra como `[Pasted text #1 +40 lines]` y una captura (alt+v) como `[Image 1]`; Vecipp recibe todo completo.
- **Vuelve a donde estabas**: al salir, Vecipp te deja el comando `vecipp -s <id>` para retomar esa conversación.
- **Mira lo que piensa, en vivo**: toca la barra de «Thinking…» (o alt+t) y se abre hacia abajo con el razonamiento corriendo, en un gris claro que se lee bien, con cualquier modelo que lo comparta; si el modelo no lo comparte, te lo dice. «Thought for Ns» lo muestra entero.
- **Las herramientas en marcha con el logo**: los dos triángulos de Vecipp cambian de color mientras una herramienta trabaja, y lo que terminó bien lleva ✓.
- **Todo alineado**: las marcas en una columna, el texto en otra y los árboles colgando del texto, como en Claude Code. Un comando que corre se ve entero, con su tiempo y «ctrl+b to run in background».
- **Marcas propias, en texto**: 𓄃 abre lo que dice el agente, 𓄀 lo que piensa, ⌬ cierra cada turno, ❖ el recap, ▴ el plan, ⏻ los avisos y ⚠ los importantes. El recap sale al final de la conversación, como en Claude Code.
- **Mucho más fluida**: con conversaciones largas, escribir, hacer scroll, abrir el razonamiento o hacer clic mientras el agente trabaja responde al instante (de casi 1 s a unos 30 ms), sin cambiar nada de cómo se ve.
- **La barra con vida**: el verbo de la barra y «Thinking» llevan un color en movimiento; lo que hace en cada momento y «Thought for Ns» se marcan en azul.
- **Tus mensajes se distinguen**: van en una banda gris con → y la hora, como el mensaje fijado arriba, y crece con lo que escribes.
- **Una bienvenida al iniciar sesión**: tu logo entre triángulos, el tema del código con vista previa (Vecipp Dark, Monokai, GitHub Dark, Nord, Monochrome; luego `/theme`), las condiciones y la privacidad para leerlas y aceptarlas (`/terms`, `/privacy`) y si sincronizar tus sesiones.
- **Respuestas con un poco de color**: el código y las rutas en un azul suave, la negrita más clara y la cursiva en lo secundario.
- **Ves cómo trabaja, como en Claude Code**: la barra cambia de verbo en cada turno (Pondering…, Spelunking…) y debajo, en un árbol, las etapas de lo que va pensando y lo que hace en ese momento («Running a command on rylax», «Reading file»); el plan aparece debajo con sus pasos (✓ hechos, ◼ el actual). Los comandos se ven como `Running command · 3s…` con `$ comando` debajo, y cada edición dice «Added 2 lines, removed 1 line».
- **Responde antes**: cada mensaje le pesa al modelo una cuarta parte de lo que pesaba (carga sólo las herramientas que usa) y, si un modelo gratis se atasca, Vecipp pasa enseguida a otro y te avisa en vez de dejarte esperando minutos.

### CLI 1.0.17 — 2026-10-17
- **Ves cómo piensa Claude**: si usas tu propia clave de Anthropic, el modelo ahora razona antes de responder y lo ves mientras trabaja; `/effort` decide cuánto piensa.
- **La pantalla de siempre**: la CLI sigue con su interfaz clásica, rápida y ligera, con tus atajos, el ratón y el scroll de siempre.

### CLI 1.0.16 — 2026-10-13
- **Listas de modelos claras y separadas**: en **`/model`** salen **solo tus proveedores** (los que agregaste con tu API key, p. ej. NVIDIA o Hostinger, con todos sus modelos) y los oficiales de Vecipp. Como Vecipp **todavía no tiene modelos oficiales**, esa parte sale **vacía** (ya no aparecen modelos "Vecipp IA" que nunca aplicaste).
- **`/lab` muestra solo los cerebros del laboratorio** (Claude, Codex, Copilot, Antigravity, Qoder), agrupados por cerebro — **ya no mezcla tus proveedores** (NVIDIA/Hostinger). Esos van en `/model`. (Antes, por un error, `/lab` abría la lista de tus proveedores.)
- **Nombres de modelo legibles**: la lista muestra **"Kimi K3 (NVIDIA)"** en vez de "moonshotai/kimi-k3". El paréntesis es siempre **quién lo sirve** (tu proveedor), así sabes con cuál lo estás usando; si el mismo modelo lo sirven dos proveedores, salen las dos opciones.
- **Arreglado un duplicado**: un modelo ya no aparece dos veces en `/model` (pasaba cuando el que usabas estaba guardado con nombre corto y en la lista estaba con el nombre largo del proveedor).

### CLI 1.0.15 — 2026-10-13
- **`/model` más claro**: los modelos salen **agrupados por el proveedor que los sirve** (NVIDIA, OpenRouter…), con el que usas ahora de primero, cada uno como "modelo (Proveedor)". Ves de dónde viene cada modelo y ya no es una lista desordenada.
- **Más comandos de sesión** (como Claude): **`/rename`** cambia el nombre de la sesión actual, **`/fork`** la bifurca en una sesión nueva para explorar sin tocar la original, **`/copy`** copia al portapapeles la última respuesta de Vecipp, **`/status`** muestra de un vistazo tu cuenta, modelo, sesión, tokens, carpeta y sincronización, y **`/doctor`** comprueba que todo está listo (Node, cuenta, herramientas, GitHub, VPS) sin salir del chat.
- **`/btw`** (o `/side`): una pregunta rápida al margen — se responde con el contexto actual pero **no** se mete en la tarea, así no desvías lo que estás haciendo.
- **`/rewind` ahora retrocede también la conversación**: además de restaurar los archivos de un turno, hace que el modelo "olvide" desde ahí (como Claude), no solo deshace archivos.
- **`/editor`**: redacta tu mensaje en tu editor favorito (`$EDITOR`) y al cerrar vuelve al prompt para enviarlo — cómodo para mensajes largos.
- **`/feedback`**: mándale un error o idea al equipo de Vecipp sin salir del chat.
- **No te deja tirado si un modelo falla**: si el modelo que usas se cae, se cuelga o devuelve vacío a mitad de una tarea, Vecipp **salta solo a otro de tus modelos** (otro modelo del mismo proveedor, u otro proveedor que tengas) y te avisa claro (*"Model X failed — trying Y…"*). Si de verdad no queda ninguno, te lo dice (prueba `/model` o agrega un proveedor) en vez de quedarse mudo.
- **Nunca más "pegado esperando"**: si un proveedor abre la conexión pero no responde, Vecipp corta a los ~120 segundos con un mensaje claro en vez de quedarse colgado para siempre (los modelos que piensan mucho no se ven afectados: cuentan los "latidos" del proveedor).

### CLI 1.0.14 — 2026-10-13
- **Compartir una sesión** (`/share`, alias `/export`): guarda toda la conversación en un archivo Markdown (`vecipp-session-….md`) en tu carpeta, listo para enviar o pegar donde quieras. Si tienes `/sync` activo, te recuerda que también está en ia.vecipp.com/code para compartir por enlace.
- **No se llena el contexto sin avisar** (auto-compact, como Claude): cuando la conversación llega al ~85% de la ventana del modelo, el agente la resume **solo** y sigue trabajando, avisándote. Todo queda guardado (`/resume` para el historial completo). Puedes apagarlo con `VECIPP_NO_AUTOCOMPACT=1`.
- **Usa tus skills por su cuenta**: ahora el agente **ve la lista de tus skills** (de `.vecipp/skills/`) y carga la que encaja con la tarea sin que se lo pidas —antes solo las usaba si iba a buscarlas a propósito.
- **Tablero en vivo del workflow**: cuando lanzas una tarea grande con varios subagentes (`workflow`), ves el tablero actualizarse en vivo —qué subtareas corren en paralelo, cuáles están hechas, bloqueadas o fallando— en vez de esperar en silencio.
- **Borrar una sesión** (`/delete <id>`): elimina una sesión guardada de tu computador y de tu cuenta. Pide confirmación: `/delete <id>` te dice qué borraría y `/delete <id> yes` lo hace. Los ids salen en `/history`.

### CLI 1.0.13 — 2026-10-13
- **`vecipp doctor`**: comprueba que todo está listo (Node, tu cuenta/proveedor, git/python/adb, GitHub, VPS…) y te dice qué falta. Ideal para preparar el equipo o un CI.
- **Autocompletado del shell**: `vecipp completion bash` (o zsh/fish/powershell) imprime el script para completar los comandos con Tab.
- **Tope de trabajo en scripts**: `vecipp -p "tarea" --max-turns 30` para que en CI no se pase de cierto número de pasos.
- **Vecipp en tu CI (GitHub Action)**: una acción lista para revisar PRs o arreglar builds con el agente (ver `apps/cli/ci/`).
- **Crea documentos de Office**: el agente genera **Word (.docx)** y **Excel (.xlsx)** de verdad (informes, tablas), sin instalar nada.
- **Edita notebooks de Jupyter** (.ipynb): agregar, cambiar o borrar celdas.
- **`/cost` ahora muestra el costo en dinero**: cuánto costó la sesión por modelo (estimado) — lo que usas con tu propia clave sale como gratis, y los modelos que paga Vecipp muestran su costo.

### CLI 1.0.12 — 2026-10-13
- **Errores de tipos al instante** (`diagnostics`): corre el chequeo del proyecto (TypeScript, Go, Rust, Python) y te lista los errores con `archivo:línea:columna` — para cazar lo que se rompió tras editar, con precisión.
- **Ir a definición y referencias** (`symbol`): dale el nombre de una función/clase y te dice dónde está definida y cuántas veces y en qué archivos se usa — como un IDE, sin abrir nada.
- **Desarrollo por especificación** (`/spec <qué construir>`): el agente arma **requisitos → diseño → tareas**, pidiéndote aprobación entre cada fase, y luego implementa paso a paso. Para funciones grandes bien planeadas.

### CLI 1.0.11 — 2026-10-13
- **Contexto siempre a la vista** (como Claude): en la barra de estado ves `ctx N%` **todo el tiempo** —cuánto de la ventana de contexto llevas usado— y cambia a color de aviso cuando se llena (y te sugiere `/compact`). Y con **`/context`** abres el panel detallado: una barra con cuánto usa el prompt del sistema, las herramientas y la conversación, y lo que queda libre. La ventana es **por modelo** (Claude ~200k, GPT ~128k, Gemini ~1M). Para **evitar consumo excesivo**.
- **No se rinde** (como Claude): el agente **sondea tu entorno** (`env_probe`: ¿admin?, ¿pantalla?, qué shells/gestores/herramientas hay) para elegir una estrategia que funcione; cuando algo falla, **clasifica el error y prueba otra vía** (2-3 alternativas, sin repetir en bucle); y si de verdad se bloquea (contraseña, UAC, algo físico) te pide un `!comando` exacto y sigue.
- **Recuerda lo que funciona en tu PC** (`remember`): guarda aprendizajes de este equipo («aquí no está inxi, usa systeminfo») y los tiene en cuenta en sesiones futuras para no re-probar lo que falla.
- **Revisa tus cambios** (`review`): reúne el diff (sin commitear / vs una rama / un commit), marca cambios grandes y **escanea secretos**, y revisa el código.
- **Mapa del repo** (`repo_map`): entiende un proyecto rápido — cada archivo con sus funciones/clases/exports — sin leerlo entero.
- **`.vecippignore`**: lista archivos que el agente **no debe leer** (secretos, ruido) y las búsquedas los saltan — menos consumo y más privacidad.
- **`format`**: formatea tu código con prettier/biome/ruff/gofmt/rustfmt (detecta el que tengas).
- **Comandos nuevos**: **`/search`** (busca en tus sesiones guardadas), **`/handoff`** (nota para continuar en una sesión nueva sin perder el hilo), **`/simplify`** (simplifica tus cambios con seguridad), **`/undo`** (deshace cambios, alias de `/rewind`).

### CLI 1.0.10 — 2026-10-13
- **Control total de tu PC** (nuevas herramientas): el agente ahora puede...
  - **Ver la salud del equipo** de un vistazo: SO, CPU y carga, RAM, cada disco (libre/usado) y los programas más pesados.
  - **Liberar espacio de forma segura**: te muestra qué se puede borrar con su tamaño (cachés, temporales, papelera) y **solo borra lo que apruebes** — nunca tus documentos.
  - **Manejar tus aplicaciones**: listar, buscar, **instalar**, **desinstalar**, **actualizar** y abrir apps (con winget), pidiéndote permiso para lo que cambia el sistema.
  - **Servicios y arranque**: ver servicios y lo que arranca con Windows, y arrancar/parar/reiniciar un servicio.
  - **Diagnosticar fallos**: revisa el registro del sistema por errores recientes, **apagados inesperados** y dispositivos con problema.
  - **Red**: ping, resolver un dominio a IP, ver si un puerto está abierto y tus adaptadores de red.
  - **Chequeo completo del PC** en una sola orden (como un «doctor»): salud + diagnóstico + cuánto puedes liberar.
  - **Controlar cualquier app por accesibilidad**: encuentra los botones **por su nombre** y los pulsa/escribe/lee, apuntando a la ventana correcta (más preciso y seguro que mover el ratón a ciegas).
- **Trabaja aún más como Claude**: reproduce el fallo antes de arreglarlo y, cuando edita para arreglar algo que fallaba, vuelve a correrlo para confirmar que quedó bien.

### CLI 1.0.9 — 2026-10-13
- **Controla cualquier app de tu computador** (`computer`): el agente ve la pantalla y usa el mouse y el teclado como una persona —abrir programas, hacer clic, escribir, atajos— en cualquier aplicación del escritorio o del sistema, no solo el navegador. (Siempre te pide permiso: maneja toda la máquina.)
- **Controla tu Android** (`adb`): con un teléfono o emulador conectado, el agente lista dispositivos, ve el estado, corre comandos, saca logcat, toma capturas, toca y escribe en la pantalla, instala apps y mueve archivos.
- **Escáner de seguridad** (`security_scan`): revisa tu proyecto por **secretos filtrados** (claves de API, tokens, contraseñas —sin instalar nada, y nunca muestra el secreto completo) y por **dependencias vulnerables** (`npm audit`), ordenado por gravedad.
- **Trabaja más como Claude**: el agente ahora **conoce su entorno** y elige la herramienta correcta (en Windows usa PowerShell o Git Bash según toque; para el VPS usa sus herramientas, no SSH a mano), y **reproduce el fallo antes de arreglarlo** (corre el test y lo ve fallar) en vez de adivinar. Probado midiendo su comportamiento contra Claude con el mismo modelo.

### CLI 1.0.8 — 2026-10-12
- **Observabilidad**: el agente puede medir si un servicio web está arriba y su latencia (`http_probe`) y analizar logs para ver la tasa de errores y los errores más repetidos agrupados.
- **Inspectores del VPS**: el agente revisa servicios, red y firewall, certificados TLS (y su caducidad), tareas cron, logs y uso de disco del servidor, cada uno con una orden.
- **Trabaja a full en tu VPS**: además de ejecutar comandos, el agente lee, edita y escribe archivos del servidor directamente, y te da un diagnóstico completo del VPS (SO, disco, memoria, servicios caídos, puertos, errores, pm2/docker) con una sola orden.
- **Modo sin interfaz (`vecipp -p`)**: corre una tarea y te da la respuesta sin abrir la interfaz —ideal para scripts y automatización—; con `--json` da un resultado estructurado.
- **Cobertura de pruebas**: el agente puede medir qué parte del código cubren las pruebas y qué archivos quedan sin probar.
- **Deshacer cambios (`/rewind`)**: si el agente tocó archivos y quieres volver atrás, `/rewind` lista los puntos y `/rewind <turno>` restaura los archivos a como estaban antes de ese turno.
- **Depurador de verdad (Node)**: el agente puede poner breakpoints y ver las variables y la pila en el punto exacto del fallo (o cuando algo lanza una excepción), en vez de adivinar o llenar de prints.
- **Skills**: guarda instrucciones para una tarea (pasos de despliegue, checklist de revisión…) en `.vecipp/skills/` y el agente las carga cuando encajan; `/skills` las lista.
- **Conecta herramientas de terceros (MCP)**: configura servidores MCP en `.vecipp/mcp.json` y el agente usa sus herramientas como propias; `/mcp` las lista. Abre cientos de integraciones.
- **Metas, repetir y agendar tareas**: `/goal` fija un objetivo que el agente recuerda cada turno; `/loop` repite una tarea hasta terminarla o pararla; `/schedule` programa tareas («en 30m…», «cada 1h…») que corren cuando el agente está libre.
- **Conecta GitHub** (como Claude): con `/github` enlazas tu cuenta mediante la CLI `gh`, y el agente puede crear/clonar repos, abrir pull requests e issues y usar la API de GitHub. (Borrar un repo o forzar un push te lo confirma antes.)
- **Instala y actualiza Vecipp for Chrome por ti** (gratis, sin la tienda): `/chrome` deja la extensión en una carpeta de Vecipp que cargas una vez; cuando sale una versión nueva, el panel muestra «Update now» y con un clic queda al día (ya no tienes que bajar el .zip ni buscar nada).
- **Tu navegador, como una persona** (con Vecipp for Chrome 1.0.3): clics y teclado de verdad, arrastrar, pasar el ratón, subir archivos, JavaScript y toda la consola y la red; mientras trabaja ves en Chrome su puntero, un panel con lo que hace y lo que piensa, y el grupo de pestañas pasa de «◐ Vecipp» a «✓ Vecipp».
- **El agente ve**: cuando lee una imagen o toma una captura del navegador, la mira de verdad (en los modelos que ven imágenes; los demás reciben un aviso).
- **Ve tu máquina**: qué programas corren, cuánta memoria usan, qué programa ocupa un puerto o si está libre, y puede detener uno (siempre te pregunta, y nunca toca el sistema).
- **Te avisa lo que pasa de fondo**: si un servidor que dejó corriendo se cae o una tarea termina, lo ves en la conversación y el agente se entera. `/tasks` lista lo que corre y lo detiene.
- **Un diseño más serio**: colores neutros, casi sin verde, sin negritas; un encabezado pequeño a la izquierda con el logo entero, el modelo, tu cuenta y **la carpeta donde estás trabajando**, que ya no cambia de tamaño al escribir.
- **Cada comando dice qué hace**: «Run the tests», y debajo el comando; mientras corre ves cuánto lleva y cuántas líneas ha escrito.
- **`ctrl+b` manda a segundo plano** un comando que tarda; y si llega a su tiempo límite ya no se pierde: sigue corriendo de fondo y el agente lo consulta.
- **Comandos que solo miran** (`ls`, `git status`, `cat`…) ya no piden permiso, y el modo plan puede usarlos para investigar.
- **Sugerencia del siguiente mensaje**: al terminar una respuesta aparece en gris lo que probablemente quieres pedir; `tab` lo toma (`/suggestions off` la apaga).
- **Tus prompts por proyecto**: ↑ recorre los de esta carpeta, y si borraste lo que escribías con `ctrl+c`, ↑ te lo devuelve.
- **Recap solo cuando sirve**: al volver tras unos minutos fuera, en sesiones de 3 o más turnos.
- **Agentes a la vista**: mientras trabajan, un árbol con lo que hace cada uno; abajo una fila por agente con su tiempo y sus tokens; al terminar, «Agent "Security" finished · 2m 49s».
- **Tus prompts a mano**: ↑ recorre los que ya enviaste (también en sesiones anteriores de esa carpeta) y ↓ te devuelve lo que estabas escribiendo.
- **El trabajo en una frase**, en vivo: «Read 3 files, made 1 edit +43, running npm test»; un clic la despliega.
- **Rutas clicables**: un clic en un archivo que menciona el agente lo abre en VS Code en esa línea.
- La pestaña de la terminal dice **Vecipp CLI** y el tema de la sesión, con un círculo que gira mientras trabaja. `?` muestra los atajos.
- **Cuatro modos con shift+tab**: normal, **✎ edits** (acepta solo las ediciones de archivos), **# root** (todo) y **◷ plan**: el agente solo lee e investiga, te presenta un plan y tú decides si lo ejecuta (aceptando ediciones o preguntando en cada cambio) o si sigue planeando.
- **Preguntas y permisos en tarjetas claras**: opciones numeradas con lo que significa cada una, el cambio que se va a hacer a la vista y, en las preguntas, la opción de escribir tu propia respuesta.
- **Al subir en la conversación** tu último mensaje queda fijo arriba y «Jump to bottom (ctrl+End)» te devuelve abajo.
- Debajo de la barra ves, cuando los hay, los **artefactos** creados, los **agentes** trabajando y las **shells** abiertas.
- **Ves al agente trabajar**: cada paso en una línea de tiempo; el que está corriendo se abre solo y muestra en vivo lo que hace (la salida del comando, el código que va escribiendo en verde y lo que quita en rojo) y se cierra al terminar. Un clic en cualquier paso lo vuelve a abrir.
- **Al terminar** dice cuánto tardó y cuántos pasos hizo (`✓ done in 13s · 7 steps`), y deja en la conversación `◆ Worked for 13s · 7 steps · ↓ 320 tokens · done 11:05`. La línea de trabajo queda fija abajo, con los tokens que van ↑ y vuelven ↓.
- **Abre al instante**: de unos 2 segundos a medio segundo.
- **Transparencia con desenfoque** y el tamaño de letra de tu terminal tal cual (Vecipp no lo cambia; `/appearance` lo ofrece si lo quieres).
- **Abajo, todo a la vista y ordenado**: modelo, proveedor, contexto, tokens y hora en la línea del prompt; el estado y un consejo en la barra.
- **El trabajo del agente, ordenado**: lo que hace entre dos respuestas se agrupa en un bloque (`Running · 8s · 6 tools` mientras trabaja, `Ran 6 tools · 1 failed` al terminar) con ✓ y ✗ por herramienta. Un clic lo despliega o lo pliega, y un clic en una línea muestra lo que hizo o lo que pensó.
- **Los pasos en una línea**: `Step 1/3 · …` en vez de la lista entera; `ctrl+t` la muestra completa.
- **Barra de estado nueva**, por segmentos y al estilo de Kali: estado y modo a la izquierda, modelo, contexto, tokens y hora a la derecha, sin colores de fondo.
- **`/appearance` con barras**: mueve la transparencia, el desenfoque y el **tamaño de letra** (para que quepa más en pantalla) con ← → y míralo cambiar en vivo; `enter` lo guarda y `esc` lo deja como estaba.

### CLI 1.0.7 — 2026-10-12
- **Pantallas nuevas**: `/model`, `/provider`, `/effort`, `/appearance`, la paleta, las sesiones y el rol del agente se ven en un mismo marco ordenado, con el detalle de cada opción.
- **`/chrome` te guía**: una lista en vivo de lo que falta (conector registrado, extensión instalada y conectada, sesión iniciada) con el paso exacto para cada cosa; `o` abre la página de descarga, `l` inicia sesión, `r` reintenta.
- **¿Lo enviaste sin querer?** `ctrl+c` antes de que llegue la respuesta lo cancela y te deja el mensaje en el cuadro para corregirlo; el agente no hace nada.
- **Copiar y pegar como en cualquier programa**: `ctrl+c` copia lo que seleccionaste con el ratón, `ctrl+v` pega (también `ctrl+shift+v` y clic derecho). Para salir con `ctrl+c` hay que pulsarlo dos veces.
- **`/model` ya no gasta nada al abrirse**: antes probaba 10 modelos con llamadas reales (en proveedores de pago eso costaba créditos). Ahora solo se comprueba el que eliges, y solo en proveedores gratis.

### CLI 1.0.6 — 2026-10-12
- **La línea de trabajo dice la verdad**: qué está haciendo de verdad (`Reading app.js`, `Running npm test`, `Thinking`, `Calling Chrome · clicking…`), el tiempo y los tokens reales. Se pone **amarilla** si el modelo deja de responder unos segundos y **roja** si se trabó.
- **`/effort low | medium | high`**: cuánto razonan los modelos que piensan antes de responder (se ve en la barra y en la línea de trabajo).
- **`/cost` y `/stats`**: los tokens de esta conversación y el consumo de este PC (hoy, 7 y 30 días, por modelo), con los créditos que cobra el proveedor. Todo queda en tu PC (`~/.vecipp/usage.jsonl`).
- El agente **cuenta lo que va haciendo** en una frase antes de cada grupo de acciones, en vez de trabajar callado.
- Aprobación compacta en una línea (`Yes · Always · No`, con ← →, y / a / n). La interfaz queda toda en inglés; la IA te sigue hablando en tu idioma.

### CLI 1.0.5 — 2026-10-12
- **Interfaz más limpia**: el banner queda arriba y el prompt abajo, con el espacio libre en medio; tus mensajes quedan como una sola línea `└─$ …` (el encabezado `┌──(vecipp㉿…)` ya no se repite); menos colores: verde para los marcos, blanco para el texto y gris para lo demás.
- **Más transparencia**: arranca con un 25 %. Si ya la cambiaste con `/appearance`, se respeta tu elección.
- **Cada vez que abres la CLI, conversación nueva** (como Claude). Para retomar la última de esa carpeta: `vecipp --continue` (o `-c`); `/resume` elige cualquiera.
- **Hostinger AI Router**: nuevo proveedor con Claude, GPT, Gemini, Grok y Kimi en una sola clave de créditos (`/provider`).

### CLI 1.0.4 — 2026-10-12
- **Interfaz nueva, estilo Kali**: pantalla completa con el prompt `┌──(vecipp㉿proyecto)-[~/ruta]` / `└─$` fijo abajo, marcas `[+] [-] [*] [!]` en cada acción, banner nuevo y enlaces azules. Sin parpadeos: al agrandar o achicar la ventana se redibuja de un golpe y todo se acomoda al ancho. Al salir, la conversación queda en tu terminal.
- **Terminal translúcida**: arranca con un 15 % de transparencia y `/appearance` la cambia en vivo (o la quita y deja tu terminal como estaba). Windows Terminal, GNOME Terminal (Ubuntu), QTerminal y Xfce (Kali).
- **Modo root**: `shift+tab` pasa de normal → root (aprobación automática: el prompt se pone rojo con `#`) → plan (pregunta todo).
- **Escribe mientras trabaja**: Enter con el agente ocupado le agrega tu mensaje a lo que está haciendo, sin interrumpirlo. Esc interrumpe.
- **Ratón de verdad**: la rueda desplaza la conversación (se queda quieta si estás leyendo arriba y sigue lo nuevo si estás abajo), arrastrar selecciona y copia (también por SSH), clic derecho pega, clic en un cambio abre su diff en un panel a la derecha, clic en un enlace lo abre, clic en el prompt mueve el cursor.
- **Atajos**: `ctrl+p` paleta de comandos, `ctrl+r` buscar en tus mensajes, `ctrl+o` enlaces, `ctrl+f` último cambio, `ctrl+t` tareas, `ctrl+y` copia la última respuesta, `?` todos los atajos. Consejos rotativos bajo el prompt.
- **Prompt completo**: flechas, Inicio/Fin, por palabras con `ctrl+←/→`, `\` + Enter para otra línea, pegar varias líneas; `@archivo` menciona un archivo (tab completa) y `!comando` lo corres tú y el agente ve la salida.
- **Freno de seguridad**: aunque tengas la aprobación automática, el agente pregunta siempre antes de un comando destructivo (borrar carpetas, `git reset --hard`, `git push --force`…) o de escribir fuera de la carpeta del proyecto.
- **Cada carpeta, su conversación**: al abrir la CLI en otra carpeta empieza limpia; en la tuya retoma la tuya.
- El agente ahora **lee PDF y notebooks** de Jupyter, **busca en la web**, lee una página respondiendo solo lo que pregunta, usa **PowerShell** además de Bash, **espera** a que un servidor esté listo sin consultar en bucle y busca en el código con más precisión (por tipo de archivo, con líneas de contexto, solo nombres o conteos).
- **Subagente general**: puede editar y correr comandos, pidiéndote permiso igual que el agente principal.
- `vecipp --chrome` activa Vecipp for Chrome **una sola vez**: desde ahí cada inicio se conecta solo a la extensión (`--no-chrome` lo apaga).

### CLI 1.0.3 — 2026-10-11
- **Vecipp for Chrome**: el agente puede usar tu propio Chrome (pestañas, leer páginas, clic, escribir, capturas, errores de consola y peticiones de red), siempre pidiendo permiso antes de actuar. `/chrome` lo conecta y `/chrome login` inicia sesión en la extensión desde la terminal.
- **Reglas del proyecto (VECIPP.md)**: el agente sigue tus reglas como obligatorias, en varios niveles (las tuyas para todos los proyectos, las del proyecto, las de cada subcarpeta). `/init` las escribe y `# regla` agrega una.
- **Pregunta de confianza** la primera vez que abres una carpeta; si dices que sí, se crea `.vecipp/` con sus ajustes.
- **Permisos que no se saltan**: en `.vecipp/settings.json` prohíbes acciones (por ejemplo `git push` o editar el `.env`) y Vecipp las bloquea antes de ejecutar.
- Comandos y subagentes propios en `.vecipp/commands` y `.vecipp/agents`; `/memory`, `/permissions` y `/commands` muestran lo que aplica.

### CLI 1.0.2 — 2026-10-11
- `vecipp --help` muestra dónde ver las novedades y bajar los instaladores: el repo público [Vecipp-IA-Releases](https://github.com/Vecipp/Vecipp-IA-Releases).

### CLI 1.0.1 — 2026-10-11
- **Artefactos al instante**: cuando el agente crea un documento, una página o un diseño, se sube a tu cuenta y se abre solo en tu navegador, ya renderizado, en `ia.vecipp.com/artifacts`.
- `/artifacts` muestra el enlace de cada uno; `/artifacts open off` apaga la apertura automática.
- Artefactos más profesionales: el agente sigue una guía de diseño (paleta, tipografía, modo oscuro, responsive, contenido real).

### CLI 1.0.0 — 2026-10-11
- Primera versión pública: se instala con una línea en Windows, macOS, Linux o un VPS.
- Proveedor **Vecipp IA**: usa los modelos con tu cuenta de Vecipp, sin API key.
- `/uso` y la barra de estado muestran tu uso de la sesión de 5 horas y de la semana, el mismo de la web y el escritorio.
- Tus sesiones se guardan en tu cuenta y se ven en ia.vecipp.com › Código (`/sync on|off`).
- Los artefactos que creas suben solos a ia.vecipp.com › Artefactos.

## Escritorio

### Escritorio 1.0.12 — 2026-10-20
- **Nunca te quedas atrás**: cuando sale una versión nueva, la ventana lo dice arriba a la derecha (`⬆ NEW UPDATE`) con lo que trae; «Update now» la descarga con su barra de progreso, la verifica, la instala y Vecipp se vuelve a abrir solo. Si no la tocas, se instala sola la próxima vez que abres Vecipp, antes del chat.
- **Imágenes con cualquier modelo**: si el modelo ve imágenes, recibe la imagen tal cual (Vecipp lo comprueba una sola vez con cada modelo y lo recuerda). Si no las ve, Vecipp te avisa y le pasa lo que leyó de la imagen con Python —el texto (también en español), los colores, las formas y los códigos QR—, y el modelo sabe que no es la imagen. La primera vez prepara ese lector (unos 2 minutos; necesita Python 3).
- **Ya no se congela de golpe**: detener un servidor de fondo, ver los procesos o los puertos, mapear el proyecto o usar Python por primera vez ya no dejan la ventana quieta unos segundos mientras trabajan.
- **Sesiones largas sin frenarse**: deshacer cambios, guardar la conversación y listar tus sesiones ya no se vuelven más lentos a medida que la sesión crece.

### Escritorio 1.0.11 — 2026-10-19
- **Los modelos Gemini ya funcionan con todas las herramientas**: antes, una sola herramienta mal descrita hacía que Gemini rechazara cada paso en cuanto Vecipp le daba sus herramientas; ahora trabaja normal, y ve las imágenes que abre (capturas, fotos, diagramas).
- **Cambios en varios archivos de una sola vez**: un renombrado o un refactor va en un paso que apruebas una vez, y es todo o nada: si una parte no encaja, no se toca ningún archivo.
- **Prueba solo lo que cambió**: después de cada cambio corre los tests de ese archivo en segundos, en vez de todo el proyecto.
- **Deshace lo suyo**: si un enfoque salió mal, Vecipp puede deshacer sus propios cambios del turno y empezar limpio (tú sigues teniendo `/rewind` para turnos enteros).
- **Entiende tu TypeScript como el editor**: usa el TypeScript de tu proyecto para ver los errores de los archivos que tocó al instante, dónde se usa de verdad una función (sin confundirla con otra del mismo nombre) y cada lugar que cambia un renombrado.
- **Tus servidores, a otro nivel**: abre un túnel SSH a una base de datos que no es pública, deja un comando largo corriendo de fondo en el servidor y te dice cómo terminó, y despliega tu proyecto con su propio método (script deploy, deploy.sh, Fly, Vercel, Netlify, pm2) — **siempre preguntándote antes**.
- **Entiende mejor a cualquier modelo**: si un modelo manda mal los datos de una herramienta (un nombre cambiado, un número como texto, un archivo con saltos de línea mal escritos), Vecipp los corrige y sigue, en vez de fallar; y entiende los errores de Windows en español.
- **Servidores de desarrollo en Windows sin sorpresas**: arranca `npm` y `vite` supervisados y, al detenerlos, baja también lo que lanzaron (el puerto queda libre).
- **La pantalla y el teclado, bien en Windows**: hace clic donde ve aunque tengas la escala al 125 o 150 %, y escribe acentos, ñ y emoji.
- **SSH que explica**: si no conecta, dice por qué (alias que no existe, llave rechazada, servidor que no responde, llave del servidor cambiada) y qué hacer; acepta una llave o un puerto para una sola conexión.
- **Tu celular por Wi-Fi**: Vecipp puede emparejar y conectar un Android con «Depuración inalámbrica», esperar a que esté listo y reiniciarlo; mirar la pantalla, las apps o los registros ya no pide permiso.
- **Busca más rápido y lee archivos enormes**: la búsqueda en el código usa ripgrep (respeta tu `.gitignore`), lee un tramo de un archivo gigante sin cargarlo entero y, si un buscador web no responde, prueba otro.
- **Python con tu entorno**: usa el `.venv` del proyecto y, si falta un módulo, te da el `pip install` exacto (con el nombre real del paquete).
- **Subagentes con límite**: cada uno tiene un tiempo máximo y se reintenta una vez si se cae; corren de a tres como máximo.
- **Reacciona mejor cuando algo falla**: reconoce el tipo de error (un programa que falta, una ruta equivocada, un archivo bloqueado, permisos, un puerto ocupado, la red, una dependencia) y toma la salida que corresponde en vez de repetir. Si intenta otra vez exactamente lo que ya falló sin cambiar nada, se le avisa que cambie de enfoque (y tú lo ves).
- **Ediciones que aciertan**: si el texto a cambiar no está tal cual en el archivo, Vecipp ve las líneas reales más parecidas y la primera diferencia, y lo corrige a la primera; si la edición ya estaba hecha, se da cuenta.
- **Respeta los archivos de Windows**: al reescribir un archivo con finales de línea CRLF (y BOM) los conserva, así git no lo marca entero como cambiado.
- **Programa con sus herramientas a la mano**: el mapa del proyecto, buscar dónde se define y usa una función, los errores del compilador, el formateador, la revisión del cambio y el depurador ya están disponibles desde el primer mensaje.
- **Más cuidado con tus servidores y tu celular**: aunque tengas la aprobación automática, Vecipp te pregunta antes de un comando por SSH que cambie el servidor (los que sólo miran pasan solos), de escribir un archivo en el VPS, de detener o reiniciar un servicio, de desinstalar una app o borrar datos del celular, y de un `DELETE` o `UPDATE` sin `WHERE` en la base de datos. Lo que se escribe en una terminal interactiva también pide permiso.
- **Varias bases de datos a la vez, sin mezclarse**: si consultas una segunda base en la misma sesión, la consulta va a esa base (antes podía caer en la primera).
- **`verify` revisa todo en los monorepos**: en un proyecto con Turborepo corre `turbo run check build test`, sin saltarse la revisión de tipos.
- **El esfuerzo ahora sí cambia algo con los modelos de Vecipp**: antes el nivel elegido no llegaba al servicio de Vecipp y siempre respondía en «medium»; ahora «low» contesta más corto y rápido y «high» piensa y escribe más.

### Escritorio 1.0.10 — 2026-10-14
- **No te deja tirado si un modelo falla**: si el modelo que usas se cae, se cuelga o devuelve vacío a mitad de una tarea, Vecipp **salta solo a otro de tus modelos** y te avisa; si de verdad no queda ninguno, te lo dice en vez de quedarse mudo.
- **Nunca más "pegado esperando"**: si un proveedor abre la conexión pero no responde, Vecipp corta a los ~120 segundos con un mensaje claro en vez de colgarse (los modelos que piensan mucho no se ven afectados).

### Escritorio 1.0.9 — 2026-10-13
- **No se llena el contexto sin avisar** (auto-compact, como Claude): cuando la conversación llega al ~85% de la ventana del modelo, el agente la resume **solo** y sigue, avisándote. Todo queda guardado. Se apaga con `VECIPP_NO_AUTOCOMPACT=1`.
- **Usa tus skills por su cuenta**: el agente ahora **ve la lista de tus skills** (de `.vecipp/skills/`) y carga la que encaja con la tarea sin que se lo pidas.
- **Más seguro**: el freno contra comandos destructivos ahora también caza las formas largas (`rm --recursive`, `rm --force`) y `find … -delete`, así que en modo automático nunca borran sin preguntar.

### Escritorio 1.0.8 — 2026-10-13
- **Crea documentos de Office**: Word (.docx) y Excel (.xlsx) de verdad (informes, tablas), sin instalar nada; y **edita notebooks** de Jupyter.
- **Errores de tipos e ir a definición** (`diagnostics`, `symbol`): caza lo que rompiste con precisión y encuentra dónde se define/usa una función.
- **Desarrollo por especificación** (`/spec`): requisitos → diseño → tareas con tu aprobación.
- **Control total del móvil** por ADB (leer/tocar cualquier app, listar/abrir/cerrar/desinstalar).
- **`/cost` muestra el costo en dinero** de la sesión (estimado); lo tuyo con clave propia sale como gratis.

### Escritorio 1.0.7 — 2026-10-13
- **Errores de tipos al instante** (`diagnostics`): corre el chequeo del proyecto (TypeScript, Go, Rust, Python) y lista los errores con archivo:línea:columna.
- **Ir a definición y referencias** (`symbol`): dónde está definida una función/clase y dónde se usa, sin abrir archivos.
- **Desarrollo por especificación** (`/spec`): requisitos → diseño → tareas con tu aprobación entre fases, y luego implementa.
- **Control total del móvil** por ADB: leer la pantalla de cualquier app (incluido Telegram), listar/abrir/cerrar/desinstalar apps, Home/Atrás/Recientes, tocar y escribir.

### Escritorio 1.0.6 — 2026-10-13
- **Contexto siempre a la vista** (como Claude): ves `ctx N%` todo el tiempo —cuánto de la ventana de contexto llevas— y con `/context` abres el panel detallado (system prompt / herramientas / conversación / libre). La ventana es por modelo. Para evitar consumo excesivo.
- **No se rinde**: sondea tu entorno (`env_probe`), prueba 2-3 alternativas cuando algo falla (sin bucles) y, si se bloquea de verdad, te pide un `!comando` exacto. Y **recuerda lo que funciona en tu PC** (`remember`).
- **Calidad**: `review` (revisa cambios + secretos), `format` (prettier/biome/ruff/gofmt/rustfmt), `repo_map` (mapa del proyecto), y los comandos `/simplify`, `/search`, `/handoff`, `/undo`.
- **`.vecippignore`**: archivos que el agente no debe leer (secretos, ruido).

### Escritorio 1.0.5 — 2026-10-13
- **Control total de tu PC**: ver la salud del equipo (CPU/RAM/discos/procesos), **liberar espacio de forma segura** (muestra qué y borra solo lo que apruebes), **manejar aplicaciones** (instalar/desinstalar/actualizar/abrir), servicios y arranque, **diagnosticar fallos** (errores, apagados inesperados, dispositivos con problema), red (ping/dns/puertos) y un **chequeo completo** en una orden.
- **Controlar cualquier app por accesibilidad**: encuentra los botones por su nombre y los pulsa/escribe/lee, apuntando a la ventana correcta.
- **Trabaja aún más como Claude**: reproduce el fallo antes de arreglarlo y vuelve a correrlo para confirmar.

### Escritorio 1.0.4 — 2026-10-13
- **Controla cualquier app de tu computador**: el agente ve la pantalla y usa mouse y teclado como una persona en cualquier programa del escritorio o del sistema (siempre te pide permiso).
- **Controla tu Android**: con un teléfono o emulador conectado, lista dispositivos, corre comandos, saca logcat, toma capturas, toca/escribe en la pantalla, instala apps y mueve archivos.
- **Escáner de seguridad**: revisa tu proyecto por secretos filtrados (claves, tokens, contraseñas —sin mostrar el secreto completo) y por dependencias vulnerables.
- **Trabaja más como Claude**: conoce su entorno y elige la herramienta correcta, y reproduce el fallo antes de arreglarlo (lo corre y lo ve fallar) en vez de adivinar.
- **Freno de seguridad**: aunque tengas la aprobación automática, el agente pregunta siempre antes de un comando destructivo (borrar carpetas, `git reset --hard`, `git push --force`…) o de escribir fuera de la carpeta del proyecto.
- El agente ahora **lee PDF y notebooks** de Jupyter, **busca en la web**, lee una página respondiendo solo lo que pregunta, usa **PowerShell** además de Bash, **espera** a que un servidor esté listo sin consultar en bucle y busca en el código con más precisión (por tipo de archivo, con líneas de contexto, solo nombres o conteos).
- **Subagente general**: puede editar y correr comandos, pidiéndote permiso igual que el agente principal.

### Escritorio 1.0.3 — 2026-10-11
- **Vecipp for Chrome**: el agente puede usar tu propio Chrome con la extensión instalada (pide permiso antes de hacer clic, escribir o navegar).
- **Reglas del proyecto (VECIPP.md) y `.vecipp/settings.json`**: el agente sigue las reglas del proyecto y los permisos prohibidos se bloquean antes de ejecutar.
- **Pregunta de confianza** al abrir una carpeta nueva; si dices que sí, se crea `.vecipp/`.

### Escritorio 1.0.2 — 2026-10-11
- **Ajustes › Acerca de Vecipp IA**: enlaces a las novedades y versiones en GitHub y a ia.vecipp.com/descargas.

### Escritorio 1.0.1 — 2026-10-11
- **Artefactos al instante**: lo que el agente crea (documentos, páginas, diseños) se guarda en tu cuenta y se abre solo en tu navegador, en `ia.vecipp.com/artifacts`.
- Artefactos más profesionales: el agente sigue una guía de diseño (paleta, tipografía, modo oscuro, responsive, contenido real).

### Escritorio 1.0.0 — 2026-10-11
- Primera versión para Windows (beta): el agente de Vecipp con ventana propia, sobre las carpetas de tu PC.
- Proveedor **Vecipp IA** con tu cuenta, y el panel de uso con la sesión de 5 horas y la semana.
- Tus sesiones se guardan en tu cuenta y se ven en ia.vecipp.com › Código.
