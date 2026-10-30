# Novedades de Vecipp IA

Lo que trae cada versión de la CLI y del escritorio. Los instaladores están en
[Releases](https://github.com/Vecipp/Vecipp-IA-Releases/releases) y en [ia.vecipp.com/descargas](https://ia.vecipp.com/descargas).

## CLI

### CLI 1.0.27 — 2026-10-30
- **Sin sustos por comandos que sólo leen**: el aviso «comando destructivo: apaga o reinicia la computadora» sale sólo cuando el comando de verdad apaga o reinicia (también en un servidor), no porque un mensaje o una ruta digan «reboot»; y revisar `crontab -l`, `fail2ban-client status`, `ufw status` o `apt list` en un servidor ya no pide permiso.
- **Termina cuando terminó, y sigue cuando dijo que seguía**: si el agente cierra ofreciéndote un siguiente paso («si quieres, el siguiente paso sería…») ya no se le obliga a seguir (antes podía repetir el resumen dos o tres veces); y si dice «sigo añadiendo…» o «continúo con…» y se detiene sin hacerlo, se le pide que lo haga.
- **Respuestas largas sin trabarse**: mientras llega una respuesta grande (un artefacto, un archivo entero), la pantalla sigue fluida; antes se iba poniendo lenta a medida que la respuesta crecía.
- **Cada bloque en su corchete**: cada herramienta que ya pasó y el razonamiento que abres van dentro de un corchete de líneas finas pegado al recuadro, sobre un gris más oscuro, y lo que trabaja en vivo siempre se ve en árbol: un paso con su comando o lo que está leyendo, y varios a la vez con una rama cada uno.
- **Más compacto, el mismo espacio entre todo**: una sola línea entre cada paso, el razonamiento, la respuesta y lo que está trabajando — la del corchete, o una en blanco —, siempre igual. Tus mensajes y el cuadro donde escribes también van en su corchete, pegado al recuadro sin tocarlo.
- **Rojo y verde vivos en los cambios**: cuando el agente edita un archivo, lo que quita se ve en rojo vivo y lo que agrega en verde vivo, como en Claude Code.
- **Más colores de verdad en lo que imprimen las herramientas**: los + verdes y los - rojos de `git diff --stat`, el historial de `git log` con sus ramas, las pruebas (PASS, FAIL, ✓, ✗), los logs con sus niveles (INFO, WARN, ERROR, DEBUG), los de nginx y journalctl, docker, y los archivos como los pinta Linux (carpetas, ejecutables, comprimidos, imágenes).
- **El agente no pierde de vista lo que manda al fondo**: si una tarea deja comandos corriendo en segundo plano (los suyos o los que mandas con Ctrl+B), antes de terminar dice qué hace con cada uno: lo espera, lo revisa y lo detiene si se colgó, o te dice que queda corriendo a propósito. Nunca repite el mismo comando mientras corre, y si uno se queda callado mucho tiempo, se entera. «Detén todo» ahora detiene también los comandos, no sólo los agentes.
- **Agentes según el trabajo**: el agente empieza mirando él mismo y suma ayudantes sólo cuando la tarea lo pide (normalmente uno o dos, más en algo grande o si se lo pides), cada uno con un título que dice qué hace. En la barra, «1 shell ↓» y «♙ 2 agents ↓»: la flecha abre lo que corre a tu lado.
- **Claude por la API de Anthropic, completo**: ves lo que Claude razona, tu esfuerzo (/effort) llega de verdad, y ve las imágenes que le pegas.
- **Una portada nueva, como una tarjeta**: la carpeta y la versión arriba, tu cuenta y los atajos abajo, y en medio el logo con «VECIPP» en grande, tu mapa de actividad —una columna por semana, un cuadrito por día, más verde cuanto más trabajaste— y tus cifras: tokens, días activos, mejor racha y sesiones. Y la pestaña de la terminal ya no lleva el ✳ verde.
- **El cuadro de texto, como el de Claude Code**: una línea fina arriba y otra abajo de lado a lado, sin franja gris ni la línea verde; la barra de abajo alineada con lo que escribes, y tus mensajes enviados sin corchete.
- **«Thought for» exacto**: dice cuánto pensó con su precisión real —«420ms», «6.5s», «1m 5s»—, y la barra de abajo cuenta en vivo mientras piensa y luego dice lo mismo que la última fila del chat.

### CLI 1.0.26 — 2026-10-28
- **Una barra a cada lado**: cada herramienta que ya pasó y el razonamiento que abres van entre dos barras verticales, a la izquierda y a la derecha, para que cada bloque se lea aparte.
- **«Thought for» con el tiempo real**: lo que queda en el chat dice cuánto pensó de verdad el modelo (antes, con algunos modelos, siempre decía 1s aunque hubiera pensado 10).
- **La compactación automática, en su punto y por conversación**: el porcentaje de contexto usa la ventana real de cada modelo (DeepSeek V4 tiene un millón de tokens, no 128 000), la compactación ocurre al llegar al 30 % de verdad y ya no se repite en bucle, y cada conversación lleva su propio contexto.
- **Colores de verdad en cada herramienta**: lo que lee el agente sale con los colores de su lenguaje (como en tu editor), y la salida de un comando o de tu servidor por ssh, con colores como en una terminal: carpetas en azul, ejecutables en verde, errores en rojo, avisos en amarillo, el disco casi lleno en rojo, `active (running)` en verde, los logs de pm2 con su app, y las IP, enlaces y horas. Si el programa trae sus propios colores, se ven los suyos. El modelo sigue recibiendo texto limpio: no gasta más.
- **Argumentos mal escritos, reparados**: si el modelo escribe un comando con una barra invertida que el formato no admite (por ejemplo `\$` en un comando de shell), Vecipp lo arregla y la herramienta corre igual, en lugar de fallar.

### CLI 1.0.25 — 2026-10-28
- **Las herramientas de Claude Code, con sus nombres**: el agente trabaja con las mismas herramientas que Claude Code —`Read`, `Write`, `Edit`, `Glob`, `Grep`, `Bash`, `Agent`, `TaskStop`, `LSP`…—. Son la mitad que antes (73 en vez de 146) y la lista de herramientas que va en cada pedido al modelo pesa casi la mitad (unos 4 900 tokens en vez de 9 000): en dos tareas reales medidas, gastó entre un 21 % y un 47 % menos de tokens, con el mismo resultado. Tus reglas de permisos, hooks y agentes con los nombres de antes se actualizan solos.
- **Comandos en segundo plano, como Claude Code**: un servidor o una compilación larga sale como `● Bash(npm run dev)` / `⎿ Running in the background`; el agente sigue trabajando y, cuando el comando termina, se entera solo y lee lo que imprimió (queda todo en un archivo).
- **Tus servidores por `ssh`, sin contraseña**: al guardar un servidor que entra con contraseña, Vecipp instala allá una llave de tu cuenta y crea su alias; desde entonces el agente entra con `ssh <nombre>`, como Claude Code. La llave es de tu cuenta de Vecipp, no se comparte con otras cuentas del mismo computador.
- **Lo que aprende de tu PC, a la vista**: lo que el agente descubre de tu computador («aquí winget necesita --disable-interactivity») queda en un archivo de tu cuenta (`machine-memory.md`) que puedes leer y corregir.
- **Revisar código**: pídele «revisa mis cambios» y carga la skill `code-review` (busca secretos filtrados y defectos reales, y comprueba cada hallazgo antes de decírtelo).
- **Más rápido en tu máquina**: el agente sabe en qué computador trabaja (núcleos y memoria) y hace a la vez tantas cosas como aguante: en un PC de 4 núcleos, hasta 8 lecturas y comandos que solo miran (`git status`, `ls`, `rg`…) al mismo tiempo, en vez de uno por uno. Los builds, las pruebas y los servidores los manda al fondo y sigue trabajando, pero sigue esperando su resultado antes de decirte que pasaron.
- **`Ctrl+B` ahora sí acelera el trabajo**: el comando que corre pasa a segundo plano y el agente **no lo espera**: sigue en el acto con lo que no necesita ese resultado («Thinking…»). Cuando el comando termina, se entera solo y lo usa. Antes el comando se iba al fondo, pero el agente se quedaba esperándolo igual. El paso dice lo que el agente le puso al comando y «· in the background» (por ejemplo, «Long build · in the background»), y el aviso del final ya no trae marcas raras (`VCWD`).

### CLI 1.0.24 — 2026-10-27
- **Lo que pegas, en verde, y tu mensaje muestra lo que lleva dentro**: las fichas `[Image 1]` y `[Pasted text #1 +40 lines]` del cuadro de texto salen en verde, y al enviar tu mensaje ya no lleva la ficha: se ve **todo el texto pegado** (texto plano, sin markdown) y, si pegaste o arrastraste una imagen, **su ruta**. Una captura del portapapeles no tiene ruta y sigue como `[Image 1]`.
- **La carpeta y la rama, como en la portada**: arriba se lee `Desktop/Vecipp-IA  ⎇ claude/telegram-bloque1`, con el `⎇` y la rama en su gris, en vez de un punto y la rama perdida entre el texto. Así sabes de un vistazo en qué rama estás trabajando.

### CLI 1.0.23 — 2026-10-27
- **Ya no se detiene a los 80 pasos**: una tarea larga sigue hasta terminar, como en Claude Code, sin el «Step limit reached (80)» que te obligaba a escribir «continúa». Queda un freno muy alto (400) por si un modelo se queda dando vueltas. Los agentes de fondo siguen con su límite de 80.
- **«Thought for» abajo cuadra con el chat**: el total de la línea de trabajo es la suma de los `∴ Thought for Ns` que van quedando. Antes contaba como «pensando» el tiempo que el modelo pasaba escribiendo un archivo después de razonar, y llegaba a 200 s con filas de 1 a 3 s.
- **Los shells, en palabras**: la barra de abajo dice «1 shell» o «2 shells», en vez de `>_ 1`. Un clic encima sigue abriéndolos.

### CLI 1.0.22 — 2026-10-27
- **Lee lo que escribió mientras te pregunta**: cuando Vecipp te hace una pregunta (o te pide permiso), la rueda del ratón sobre la conversación la sube y baja para que leas todo antes de contestar; sobre las opciones sigue cambiando la opción. Fuera de la pantalla completa funciona el desplazamiento normal de tu terminal. Y el aviso «Jump to bottom» ya se ve encima de la pregunta.
- **El razonamiento plegado, más limpio**: la fila queda `∴ Thought for 3s`, sin «(click to show thinking)»; un clic la sigue abriendo y cerrando.
- **Ves la herramienta mientras el modelo la escribe, también con Claude**: cuando el modelo prepara un archivo o un comando largo, ves la llamada creciendo en vivo (`Write(src/app.js)` con lo que va escribiendo) y la línea de trabajo ya no se pone amarilla con «waiting for the model» mientras escribe. Antes, con un archivo largo, Vecipp creía que el modelo se había colgado y a los 90 segundos le volvía a pedir lo mismo desde el principio.
- **Detener los agentes, de verdad**: si le dices a Vecipp «detén los agentes», los detiene (uno por nombre o todos) y te dice cuáles paró y cuáles ya habían terminado; antes les mandaba un mensaje y seguían corriendo. Dentro de un agente, **Esc lo detiene** (otro Esc te devuelve a la conversación), y en la conversación, con agentes trabajando, la primera Esc o Ctrl+C para el turno y te avisa `2 AGENTS STILL WORKING · ESC AGAIN STOPS THEM`: la segunda, en 2 segundos, los detiene a todos.
- **Menos preguntas en tu servidor**: en modo automático Vecipp ya no te pide permiso por cada comando que cambia algo en tu VPS; en modo normal pregunta una vez por servidor (`Yes, and don't ask again for this server this session`). Lo riesgoso de verdad —un `rm -rf`, un `git reset --hard`, un `DELETE` sin `WHERE`— pregunta **una sola vez por tipo**, también en automático, y si dices que sí para la sesión no vuelve a preguntar por eso. Los agentes de fondo usan los mismos permisos que ya diste.
- **Cada paso dice lo que hace, con sus palabras**: como en Claude Code, el agente escribe un titular corto para cada acción (`● Check whether the shop app is running`, `● Show the last three commits`) y ves lo que de verdad está haciendo, no el nombre interno de la herramienta. Si el modelo no lo escribe, cada herramienta y cada acción tienen su frase (`● Reading the web app log`, `● Opening vecipp.com`, `● Tapping the screen`); se acabó el «Using web_app run…». El resumen gris también lo dice con palabras («Worked on the web app 2 times»).
- **Escríbele mientras trabaja, como en Claude Code**: lo que mandas mientras Vecipp trabaja queda **en gris, debajo de lo que está haciendo** (puedes mandar varios, uno tras otro); en cuanto lo toma —con el resultado del paso en curso— pasa a la conversación y sigue con eso en cuenta. Si te arrepientes, **↑** con el cuadro vacío te lo devuelve para editarlo.
- **Lo que despliegas, sobre gris**: al abrir con un clic una línea como «Read 3 files», un «∴ Thought» o una consulta web, se pinta sobre un recuadro gris oscuro a todo el ancho, como en Claude Code.
- **Tips cortos en las tareas largas**: si una tarea pasa de 30 segundos, bajo la línea de trabajo sale un consejo (`⎿ Tip: Use /clear to start fresh…`), uno por tarea.
- **Las herramientas empaquetadas en un solo bloque, como Claude Code**: mientras Vecipp lee, busca o corre comandos, ves **un solo bloque** que va cambiando con lo que hace en ese momento —`● Reading src/cart.js` con `⎿ src/cart.js` debajo, luego `● Searching for TODO` / `⎿ "TODO"`, y un comando con la descripción que le dio el modelo (`● Running project test suite · 3s` / `⎿ $ npm test (3s · 5 lines)`)— y que **no desaparece entre una herramienta y otra**, así siempre sabes que algo está trabajando. Cuando termina ese tramo se pliega a una línea gris con todo lo que hizo (`Searched for 3 patterns, read 2 files, ran 2 shell commands`, los números en negrita); un clic la despliega con cada paso y su resultado. Ninguna herramienta abre ya una fila propia que aparece un instante y se va.
- **El chat alineado como Claude Code y a todo el ancho**: todo —respuestas, herramientas, el árbol de archivos, el resumen, las tareas, **tus mensajes, la ruta de arriba, la línea de trabajo y la barra de estado**— empieza justo en el borde izquierdo (el `●` en la primera columna, como Claude) y llega hasta el borde derecho, sin quedar metido al centro ni dejar aire a los lados. Y los **textos largos ya no se cortan con «…»**: saltan a la siguiente línea para que no pierdas nada. El nombre de la sesión ya no va sobre el cuadro de texto: va en la **pestaña de la terminal**.
- **El texto se dibuja fluido mientras trabaja**: cuando Vecipp va escribiendo la respuesta o mostrando lo que hace, ahora se dibuja al doble de velocidad (≈25 cuadros por segundo en vez de ≈11), sin tirones ni pausas. No gasta más: los iconos que giran siguen igual y en reposo no dibuja nada.
- **Los paneles como Claude Code**: `/model`, `/effort`, `/resume`, `/status`, `/help`, `/permissions` y los demás se abren abajo con el mismo orden, márgenes y colores de Claude Code: la fila elegida en azul, lo que estás usando en verde con ✔, el ratón en gris claro, un buscador redondeado. `/status`, `/config` y `/usage` son un solo panel con pestañas (←/→).
- **El esfuerzo, más bonito**: `/effort` es un riel con ▲ entre «Faster» y «Smarter» —con las flechas o con un clic— y cada nivel tiene su efecto: xhigh brilla en violeta y max es un arcoíris que se mueve. En `/model` lo cambias ahí mismo con ←/→.
- **Tu historial, ordenado**: `/resume` muestra cada conversación en dos filas (el título y «hace cuánto · mensajes · tamaño»), los artefactos que hizo, un buscador, Espacio para ver lo que dice antes de entrar y Ctrl+A para ver las de todos tus proyectos. Ahora es la **única** forma de ver y seguir tus conversaciones: quitamos `/history` y `/sessions`.
- **`/compact <lo que importa>`**: al compactar una conversación larga puedes decir qué conservar con todo el detalle (por ejemplo `/compact las decisiones de la API`); el resto se resume más breve. Sin texto, compacta como siempre.
- **El explorador de archivos, como tu historial**: ya no es una barra lateral, sino un panel que se abre abajo (igual que `/resume`): el árbol de la carpeta con un buscador, ↑↓ para moverte, →/Enter para abrir una carpeta y Enter para ver un archivo dentro del mismo panel. Lo abres con `Ctrl+B` (sin nada corriendo) o con `/files`.
- **El contexto, más claro en la barra**: en vez de una barra de bloques, ahora ves un medidor que se llena con el porcentaje (`◔ 12%`), en verde, ámbar o rojo, y te dice `/compact` cuando conviene; un clic abre `/context`. Mientras el agente trabaja, el medidor brilla suavemente. Empieza casi vacío en cada conversación nueva.
- **`/context` como en Claude**: ahora abre un panel con una **cuadrícula de colores** que muestra cuánto ocupan el prompt del sistema (azul), las herramientas (cian) y tu conversación (verde), y cuánto queda libre; con la leyenda y los datos de la sesión. Y queda claro: al ~85% **la conversación se compacta sola**, no tienes que hacer nada (`/compact` solo lo adelanta).
- **La barra de abajo, con más vida**: mientras Vecipp trabaja, el estado gira y **brilla en verde** con un verbo del turno (`◐ Forging…`, `◓ Weaving…`), y la línea de trabajo de arriba (`✻ Forging…`) respira igual; en reposo dice **`✓ Ready to build`**. Los avisos tras un turno dejan el MAYÚSCULAS y salen elegantes (`✓ Done`, `✗ Error`). Y la ventana de **`/help`** ahora agrupa los comandos por tema (sesión, contexto, herramientas, apariencia, cuenta…) para encontrarlos rápido.
- **Artefactos más elaborados, como Claude**: cuando le pides un artefacto (una página, una app, un panel, un diagrama, un documento), Vecipp carga por su cuenta una **skill de diseño** (verás `● Skill(artifact-design)`) con el mismo contrato que usa Claude —HTML autocontenido, React y librerías por CDN, sistema de color con modo oscuro, gráficas accesibles (`dataviz`) y diagramas (`artifact-diagramming`), contenido real— para que el resultado salga al nivel de los de claude.ai. Puedes poner tu propia versión en `.vecipp/skills/artifact-design.md`.
- **Nada que se abra y se cierre**: un comando que corre se ve en el bloque de su grupo (lo que hace, el tiempo desde los 2 segundos, el comando debajo y, si tarda más de 3 segundos, `(ctrl+b to run in background)`); antes aparecía un bloque que se cerraba de golpe.
- **Lo importante en azul**: rutas, comandos, URLs y `código` en las respuestas salen en el azul de Claude Code.
- **`/export` y `/copy 2`**: guarda o copia la conversación entera; copia la penúltima respuesta.
- **Los tokens de cada tarea empiezan en 0**: la línea de trabajo cuenta sólo lo que el modelo escribe en la tarea que está haciendo, como Claude Code (antes mostraba el tamaño de toda la conversación al empezar).
- **El menú de comandos como Claude Code**: al escribir `/` se abre encima del cuadro y crece hacia arriba; con ↑↓ eliges (la fila en azul), Enter ejecuta el elegido, el ratón resalta en gris claro y un clic lo toma. Las letras que coinciden van en negrita, y se encuentra por cualquier palabra del nombre (`/notes` encuentra `/release-notes`).
- **El chat se dibuja más como Claude Code**: cada bloque lleva su línea en blanco (un «Read 3 files» ya no queda pegado a lo de abajo), un comando que arrancas de fondo se ve como «Running npm test in background» y su permiso es el de un comando normal, con «Yes, and don't ask again for: npm test *». Lo que pegas de una sola línea (hasta 800 caracteres) se ve entero en vez de «[Pasted text #1]».
- **Los límites por minuto se esperan de verdad**: si el proveedor dice «reintenta en 1 segundo» una y otra vez, Vecipp ya no se rinde a los 9 segundos: espera cada vez un poco más (hasta unos 3 minutos). Lo ves en una sola línea bajo la de trabajo que cuenta los segundos —`API Error (429) · Retrying in 8 seconds… (attempt 2/9)`— y, si al final no se pudo, el error dice qué límite fue, con las palabras del proveedor.
- **Pasos más claros**: un grupo de pasos dice cuáles fueron («Read 2 files, ran tests, checked for errors») en vez de «2 other steps», y un paso ya no sale dos veces mientras corre.
- **Monitor sin llenar la pantalla**: si un monitor avisa muchas veces mientras Vecipp trabaja (más de 3), al terminar se junta en una línea («Monitor events (7)») con lo último que pasó.
- **Enlaces bien dibujados**: un enlace después de un texto en negrita ya no deja letras sueltas en la pantalla.
- **Búsquedas que sí responden**: si un buscador devuelve páginas de otro tema (por ejemplo, el RFC del SAT cuando buscas el RFC 4180 de CSV), no cuentan como resultados y Vecipp prueba otro.
- **Las herramientas se ven como en Claude Code**: cada paso es `● Update(src/stock.js)`, `● Bash(npm test)` o `● Fetch(https://…)`, con su detalle colgando de `⎿` (`Added 2 lines, removed 1 line` y el diff, `Wrote 32 lines to …`, `Received 241.5KB (200 OK)`). Las lecturas y búsquedas se juntan en una fila gris («Read 3 files, ran 1 shell command»); un comando dice qué hace, el comando entero y su tiempo; la lista de tareas (✔ ◼ ◻) va bajo la línea de trabajo y cada turno cierra con «✻ Forged for 8s · ↓ 2.1k tokens · done 6:13 PM». El cuadro de texto, la portada y la barra de abajo siguen siendo los de Vecipp.
- **Permisos más claros**: cuando Vecipp te pregunta, ves qué es (`Bash command`, `Edit file`), qué hace, el comando o el cambio entre líneas punteadas y `Do you want to proceed?`. Con **Tab** sobre «No» le escribes qué hacer distinto y sigue con eso.
- **«No me preguntes más por esto»**: en el permiso de un comando, `Yes, and don't ask again for: npm run *` deja pasar solos los comandos de esa familia en este proyecto (también al volver a abrir Vecipp). Es tuyo: otra cuenta en el mismo computador no lo hereda. Y es seguro con comandos encadenados: `npm run x && rm -rf …` vuelve a preguntar.
- **ctrl+o, la conversación detallada**: como en Claude Code, abre cada paso, el razonamiento y la hora y el modelo de cada respuesta; otra vez ctrl+o vuelve. Los enlaces de la conversación ahora están en `/links`.
- **Preguntas y planes como en Claude Code**: las preguntas con opciones muestran el tema (`☐ Delimiter`), cada opción con su explicación debajo y `Type something.`; tu respuesta queda como `● User answered Vecipp's questions:`. Al terminar un plan: `Ready to code?` y `Would you like to proceed?`. Un agente que arranca dice `Initializing…`, y los hooks de tu proyecto se ven en la línea de trabajo mientras corren.
- **Hooks más seguros, y un interruptor**: como los hooks corren comandos, los de una carpeta solo se activan cuando confías en ella (un `vecipp -p` sin interfaz la cuenta como confiada, así tus scripts siguen igual). Pon `"disableAllHooks": true` en `.vecipp/settings.json` para apagarlos todos de una vez, y `/hooks` te muestra los que tienes por evento (o que están apagados).
- **Muchos más momentos para enganchar un hook**: ahora también puedes correr comandos alrededor de la compactación (`PreCompact`/`PostCompact`), al cerrar la conversación (`SessionEnd`), tras un grupo de acciones (`PostToolBatch`), cuando arranca un subagente (`SubagentStart`), cuando el turno falla por la API (`StopFailure`) y cuando Vecipp te avisa (`Notification`). Y un hook `PermissionRequest` puede **responder el permiso por ti** (permitir o negar): si permite, el paso corre y se marca «Allowed by a PermissionRequest hook».
- **Un hook ya no es solo un comando**: además de `command` (ahora con `args` para correr sin shell, o `shell` para elegir bash/powershell), un hook puede ser `http` (manda el evento a una URL y su respuesta decide) o `prompt`/`agent` (un modelo de Claude juzga la condición y responde si sigue o no). Los pones en `.vecipp/settings.json` con `"type"`.
- **Hooks de ciclo de vida**: también puedes enganchar comandos cuando cambias de carpeta (`CwdChanged`), cuando cambia un archivo de ajustes (`ConfigChange`), cuando entra una `VECIPP.md` en contexto (`InstructionsLoaded`) o cuando cambia en disco un archivo que vigilas (`FileChanged`, nombrándolo en el `matcher`).
- **Varias carpetas a la vez**: con `/add-dir <carpeta>` (o pidiéndoselo a Vecipp) añades otro proyecto al espacio de trabajo sin dejar el actual: puedes leer, escribir y ejecutar en los dos, y escribir en el añadido ya no te pregunta «fuera del proyecto». Dispara el hook `DirectoryAdded`.
- **Hooks de modelo y worktree**: también puedes enganchar comandos cuando cambias de modelo (`PostModelSwitch`) o cuando creas/borras un worktree de git (`WorktreeCreate`/`WorktreeRemove`).
- **Subagentes propios más potentes**: en `.vecipp/agents/<nombre>.md` ahora el frontmatter acepta `tools` / `disallowedTools` (qué herramientas usa — si le das una de escritura, el subagente edita y pide aprobación como el principal, antes solo podían leer), `model` (`inherit` o uno tuyo), `effort`, `maxTurns`, `permissionMode` (`plan` lo deja solo mirando, `auto` lo deja actuar sin preguntar), `color` (se pinta su nombre) , `isolation: worktree` (edita en su propio worktree de git, sin tocar tu copia) y `skills` (precarga tus skills de `.vecipp/skills/` en su contexto). Como Claude Code.
- **Las páginas de internet piden permiso por sitio**: como en Claude Code, leer una página pregunta una vez por sitio (`Yes, and don't ask again for example.com`), y una página que redirige a otro sitio no se sigue sola. En modo automático no pregunta.
- **Archivos que nunca se tocan solos**: cambiar algo en `.git`, en la configuración de Vecipp (`.vecipp/`) o en archivos como `.bashrc`, `.gitconfig` o `.npmrc` siempre te pregunta, aunque estés en modo automático.
- **Conversaciones largas sin cortarse**: Vecipp sabe el tamaño real de la memoria de cada modelo (los Claude nuevos leen 1M), compacta también a mitad del trabajo y, si el modelo dice que la conversación es demasiado larga, la resume y sigue.
- **Hooks como los de Claude Code**: en `.vecipp/settings.json` puedes poner comandos que corren antes de cada acción (y pueden bloquearla o cambiarla), después, cuando envías un mensaje, al empezar la conversación o cuando Vecipp va a terminar (por ejemplo: «no termines sin correr las pruebas»). Los de antes (`beforeTool`/`afterTool`) siguen igual.
- **Doble Esc para volver atrás**: con el cuadro vacío, Esc Esc abre «Rewind»: eliges uno de tus mensajes y si vuelves el código, la conversación o los dos; tu mensaje vuelve al cuadro para mandarlo otra vez o cambiarlo.
- **Planes que pide aprobar**: el agente puede pasar solo a modo plan y presentarte el plan («Ready to code?»); si lo apruebas, sigue de una.
- **`git` pregunta antes de cambiar algo**: un commit o un push ya no pasan sin tu permiso en modo normal (mirar el estado o las diferencias sigue sin preguntar).
- **Vigila mientras trabaja**: con Monitor, Vecipp vigila un servidor o una prueba que corre de fondo y cada línea importante (un ERROR, un FAIL) le llega al momento, aunque esté haciendo otra cosa; si estaba libre, se despierta a contarte.
- **Recordatorios y tareas programadas**: el agente puede programar algo para más tarde («a las 9:52», «cada hora») igual que tú con `/schedule`.
- **Probar aparte**: el agente puede mudarse a un worktree de git para intentar algo sin tocar tu rama, y volver dejándolo o borrándolo.
- **Buscar en internet pide permiso** una vez en el proyecto (`Yes, and don't ask again for Web Search in this project`).
- **Tus acentos a salvo**: si un archivo no está en UTF-8 (muchos archivos viejos de Windows), Vecipp no lo edita a ciegas —eso rompía cada «ñ» y «á»—: te dice cómo convertirlo primero.
- **Lee antes de cambiar**: como Claude Code, Vecipp no cambia un archivo sin haberlo leído, ni lo reescribe entero si tú (o un formateador) lo cambiaste después de que lo leyera: lo vuelve a leer primero.
- **Más seguro**: un comando como `env X=1 rm -rf build` ya no pasa como si sólo mirara, y una regla que prohíbe editar `.env` vale para todas las formas de editar archivos.
- **Salidas enormes sin perder nada**: si un comando imprime más de 30 000 caracteres, Vecipp guarda la salida entera en un archivo y el agente lee de ahí lo que necesita, en vez de quedarse sin el medio.
- **Tu modelo es tu modelo**: si el que elegiste da un límite por minuto (un 429, por ejemplo Azure cuando varios agentes trabajan a la vez), Vecipp espera lo que el proveedor indica y reintenta con el mismo, hasta unos 3 minutos. Ya no salta solo a otros proveedores (y menos a uno sin créditos); eso pasa solo si lo activas con `/model auto on`.
- **Ves cuándo el modelo razonó**: los modelos gpt-5/6 de Azure razonan con el esfuerzo que elijas (los 5 niveles), pero con razonamientos cortos no comparten el resumen. Ahora Vecipp lo dice igual: «Thought for 2s» con cuántos tokens razonó. El resumen se pide más detallado, así que llega más seguido.
- **Una portada más limpia**: al abrir Vecipp ves su logo dibujado en bloques, estilo pixel (la V gris, el ▼ blanco y el ▲ verde) y, al lado, el nombre con la versión, la carpeta donde trabaja con su rama y tu cuenta, y tres atajos que puedes tocar: `/ commands`, `ctrl+\ sessions` y `? shortcuts`. Nada más: el modelo ya está en la barra de abajo.

### CLI 1.0.21 — 2026-10-20
- **Tus conversaciones son solo tuyas**: cada conversación guardada sabe de qué cuenta de Vecipp es. Si otra persona entra con su cuenta en el mismo computador, `/resume`, `/history`, `/search` y `vecipp -c` solo le muestran las suyas, `vecipp -s` no le abre las tuyas, y nada tuyo se sube a su cuenta en ia.vecipp.com. Lo que Vecipp recuerda de la máquina, lo que escribiste antes (↑) y las otras sesiones abiertas que ve también van por cuenta, y lo más delicado también: tus credenciales guardadas, tus servidores (otra cuenta nunca puede entrar a tu VPS), tus claves de API, tus skills y tus reglas viven en una carpeta solo de tu cuenta. Al entrar con otra cuenta o al cerrar sesión, la conversación abierta se guarda con la suya y empieza una nueva.
- **Varios cambios de una vez**: cuando hay que tocar varias partes de un archivo (o varios archivos), Vecipp manda todas las ediciones juntas, como Claude Code: las ves aparecer de una en gris (`● Update  archivo  queued`) y cada una se convierte en su cambio con su diff al aplicarse. Si una no calza, falla sola y las demás entran igual. En modo Ask, la pregunta dice cuál es: `edit 2 of 4`. En la prueba con un modelo gratis, la misma tarea pasó de 3,6 a 0,7 minutos.
- **Agentes en segundo plano**: cuando una tarea de verdad lo amerita (investigar varias partes a la vez, una revisión, algo largo), Vecipp lanza agentes que trabajan en paralelo mientras él sigue: ves `● 2 background agents launched (↓ to manage)` con lo que hace cada uno, y abajo una fila por agente con su paso de ahora, su tiempo y sus tokens. Cada uno avisa al terminar con lo que encontró y los archivos que cambió, y Vecipp sigue con eso (si ya había terminado su turno, se despierta solo). Con ↓ abres un agente para ver su conversación en vivo, y **lo que escribes le llega a él** (el cuadro se pone azul: `Message @explore-2…`); a uno que ya terminó, escribirle lo reanuda. `x` o `/tasks stop @nombre` lo detiene. Para algo puntual, Vecipp busca él mismo: no lanza agentes por todo.
- **Código de calidad en todo lo que construye**: cuando le pides una app, una web, un juego o una API, Vecipp parte de una plantilla bien hecha, la organiza en módulos cortos y claros, maneja los errores, la deja usable en un celular, la corre, la prueba y la mira antes de decir que está lista.
- **Juegos que se sienten bien**: pídele un juego y lo crea completo (menú, partida, fin, récord guardado, sonido, partículas, pausa, controles táctiles y de teclado), lo prueba en un navegador real a tamaño de celular con un bot que lo juega y te muestra la captura. También lo puede convertir en una app Android.
- **Bases de datos y webs de verdad**: levanta PostgreSQL, MariaDB, Redis o SQLite solo para tu máquina, crea la base con su usuario y contraseña fuerte y la deja en el `.env`; crea webs con su API, las revisa por dentro y en el navegador, y te da un enlace público temporal para mostrarlas.
- **Tus credenciales, bien guardadas**: pégale una contraseña o un token y lo usa sin escribirlo nunca en la conversación; queda en una bóveda en tu máquina.
- **Tus servidores por nombre**: guarda tu VPS, tu Windows o tu hosting (SSH, FTP o el token de cPanel) y trabaja en ellos por dentro: subir proyectos, instalar, dejarlos corriendo, crear bases en cPanel.
- **Tus sesiones se ven y se hablan**: si abres Vecipp en varias terminales, cada sesión tiene un nombre (la carpeta y dos letras, como `vecipp-ia-af`) y sabe cuáles más están abiertas, si están trabajando o libres, en qué y qué archivos están escribiendo. Antes de tocar un archivo que otra está cambiando, o antes de un commit o un despliegue, le pregunta; avisa lo que va a tocar y nunca hace commit del trabajo de otra. Lo que llega sale como `› Message from @vecipp-ia-af: …` (un clic lo abre). En modo automático contesta sola; en los demás te espera (Enter deja que Vecipp conteste). `/peers` las lista y la barra muestra `@nombre · 2 other sessions`. Un mensaje de otra sesión nunca da permisos ni aprueba nada por ti, y dos ventanas ya no continúan la misma conversación.
- **Ves cada consulta a internet**: cuando el agente lee una página o busca en la web, cada consulta sale como su propio paso, ya no escondida en «Fetched 3 pages»: `● Fetch https://…` y debajo cuánto llegó, `Received 241.5KB (200 OK)`; si falla, el motivo en rojo (`Error: socket hang up`, no un «fetch failed» genérico); mientras espera, `Fetching…` con sus segundos. Una búsqueda dice `Found 8 results in 2s` y muestra sus primeros resultados; un clic muestra todos, o las primeras líneas de la página.
- **El esfuerzo, preciso con cada modelo**: `/effort` muestra sólo los niveles que el modelo en uso tiene de verdad, con los nombres de Vecipp. Claude tiene 5; GPT-5.6 Terra, 6 (llega a **ultra**); Gemini 3.8 Flash, 3; GPT-OSS, 3; Nemotron 3 Ultra, 3 (con **none**, sin razonar); Nemotron 3.5 Lightning y Super VL, 2. Antes había 5 fijos para todos y en muchos modelos los de arriba no hacían nada. Tu elección se guarda: con un modelo que no tiene ese nivel, se usa el más cercano por debajo, y la barra muestra el que recibe. Si un proveedor rechaza un nivel y dice cuáles acepta, Vecipp lo aprende para la próxima vez.
- **Modelos gratis que funcionan**: NVIDIA retiró Kimi K3 y dejó de servir Nemotron 3 Super. Ahora el modelo rápido por defecto es **Nemotron 3.5 Lightning** y el grande es **Nemotron 3.5 Super VL**, que también ve imágenes. Si tenías elegido uno de los viejos, pasas solo al nuevo.

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

### Escritorio Próxima versión
- **Claude por la API de Anthropic, completo**: ves lo que Claude razona, tu esfuerzo llega de verdad, y ve las imágenes que le pegas.
- **El agente no pierde de vista lo que manda al fondo**: antes de terminar dice qué hace con cada comando que sigue corriendo (lo espera, lo detiene si se colgó o lo deja a propósito), nunca lo repite mientras corre, y «detén todo» detiene también los comandos.
- **Agentes según el trabajo**: empieza mirando él mismo y suma ayudantes sólo cuando la tarea lo pide, cada uno con un título que dice qué hace.

### Escritorio 1.0.14 — 2026-10-28
- **Las herramientas de Claude Code, con sus nombres**: cada paso y cada aprobación dicen `Read`, `Edit`, `Bash`…, como en Claude Code; el agente tiene la mitad de herramientas que antes, y la lista de herramientas que va en cada pedido al modelo pesa casi la mitad.
- **Un archivo largo con Claude ya no empieza de nuevo**: mientras el modelo escribe un archivo o un comando largo, Vecipp sabe que sigue trabajando. Antes, si tardaba más de 90 segundos, creía que se había colgado y le volvía a pedir lo mismo desde el principio.
- **Icono propio**: Vecipp Escritorio ya tiene su icono —el logo de Vecipp sobre un cuadro oscuro, con el triángulo verde— en el instalador, el acceso directo del escritorio, la barra de tareas y el menú Inicio (antes salía el de Electron).
- **Un diseño limpio, igual en el escritorio y en ia.vecipp.com**: grises neutros, tu mensaje en una burbuja a la derecha, la respuesta como texto limpio con un botón para copiarla, el razonamiento en una línea gris que se abre con un clic, y abajo el modelo y el aviso. La barra lateral: sesión nueva, buscar, tus recientes y tu cuenta en una sola línea (el uso del plan, el tema y los ajustes están en su menú).
- **Y trabaja como el CLI**: lo que lee, busca y ejecuta queda plegado en una sola línea gris («Read 2 files, ran 1 shell command») que se abre con un clic; cada cambio sale como `● Update(archivo)` con sus líneas en verde y rojo; el razonamiento plegado (`∴ Thought for 6s`); mientras trabaja, `✻ … (12s · esc to interrupt)` con el plan debajo, y al terminar `✻ Engineered for 8s · done 5:03 PM`. Debajo del cuadro: `✓ Ready to build` o `◑ Thinking…` / `◑ Building…`.
- **La carpeta a la vista**: arriba dice en qué carpeta trabaja; el `+` de abajo abre una sesión nueva en otra.
- **Permisos como en el CLI**: «Do you want to make this edit to app.ts?» con 1. Yes · 2. Yes, and don't ask again · 3. No; respondes con 1, 2, 3 o con las flechas y Enter, y Esc dice que no.
- **Arriba, tu computadora**: la barra de arriba es la de la ventana; muestra el nombre de tu PC con un punto verde y, al tocarlo, que Vecipp está conectado y puede usar sus archivos y apps. El título de la sesión abre su menú (abrir la carpeta, verla en ia.vecipp.com, borrarla), y en la barra lateral tienes atrás y adelante entre tus sesiones.
- **Atajos**: `Esc` interrumpe, `Ctrl+N` abre una sesión nueva y `Ctrl+B` muestra u oculta la barra lateral.

### Escritorio 1.0.13 — 2026-10-20
- **Tus conversaciones son solo tuyas**: cada conversación sabe de qué cuenta de Vecipp es. Si otra persona entra con su cuenta en el mismo computador, solo ve las suyas y no puede abrir ni borrar las tuyas, y nada tuyo se sube a su cuenta. Tus credenciales, tus servidores, tus claves de API y tus skills también son solo de tu cuenta. Al entrar con otra cuenta o al cerrar sesión, la lista se renueva y empiezas limpio.

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
