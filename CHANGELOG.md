# Novedades de Vecipp IA

Lo que trae cada versión de la CLI y del escritorio. Los instaladores están en
[Releases](https://github.com/Vecipp/Vecipp-IA-Releases/releases) y en [ia.vecipp.com/descargas](https://ia.vecipp.com/descargas).

## CLI

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
