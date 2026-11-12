<!-- vecipp:cabecera — generado por aplicar-marca: no editar a mano, se regenera -->
<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/banner-oscuro.svg">
    <img src=".github/assets/banner-claro.svg" alt="Vecipp IA — Tu agente de programación en la terminal, el escritorio y la web" width="100%">
  </picture>
</p>

<p align="center">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white&style=flat-square">
  <img alt="Node.js" src="https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white&style=flat-square">
  <img alt="React" src="https://img.shields.io/badge/React-149ECA?logo=react&logoColor=white&style=flat-square">
  <img alt="Next.js" src="https://img.shields.io/badge/Next.js-000000?logo=nextdotjs&logoColor=white&style=flat-square">
  <img alt="Electron" src="https://img.shields.io/badge/Electron-47848F?logo=electron&logoColor=white&style=flat-square">
  <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white&style=flat-square">
  <img alt="Ecosistema Vecipp" src="https://img.shields.io/badge/Ecosistema_Vecipp-IA-1FC259?style=flat-square">
  <img alt="Licencia propietaria" src="https://img.shields.io/badge/licencia-propietaria-334155?style=flat-square">
  <img alt="Hecho en Colombia" src="https://img.shields.io/badge/hecho_en-Colombia-FCD116?style=flat-square">
</p>

<p align="center">
  <a href="https://vecipp.com"><b>vecipp.com</b></a> ·
  <a href="https://github.com/Vecipp/Vecipp-Negocio"><b>Vecipp Negocio</b></a> ·
  <a href="https://github.com/Vecipp/Vecipp-Barrio"><b>Vecipp Barrio</b></a> ·
  <a href="https://github.com/Vecipp/Vecipp-IA-Releases"><b>Vecipp IA</b></a>
</p>
<!-- /vecipp:cabecera -->

## Qué es

**Veci** es un agente de IA que vive en tu teléfono y en tu terminal. Lee y edita tu código, corre comandos, se conecta
por SSH a tus servidores, usa tu navegador y te entrega lo que crea listo para ver. Una sola cuenta de Veci para los dos:

| | Para qué | Dónde trabaja |
|---|---|---|
| 📱 **Veci** (la app) | El agente en tu celular, con su cara y su voz: le hablas y trabaja | Tu Android, con su propio entorno Linux |
| 🖥️ **Veci CLI** (`veci`) | El agente completo en tu terminal | Tu PC, tu VPS o tu celular: cualquier carpeta, varias shells, SSH, bases de datos, pruebas |
| 🧭 **Veci for Chrome** | Que el CLI use tu navegador (con tu permiso) | Chrome, Edge o Brave |

## Instalación

**La app**: [ia.vecipp.com/descargas](https://ia.vecipp.com/descargas) → Veci para Android.

**El CLI en Windows** (PowerShell):

```powershell
irm https://ia.vecipp.com/install.ps1 | iex
```

**El CLI en macOS · Linux · VPS · el celular**:

```bash
curl -fsSL https://ia.vecipp.com/install.sh | bash
```

No piden permisos de administrador ni `sudo`: si no tienes Node.js 20+, instalan uno solo para tu usuario, y comprueban
la firma SHA-256 de todo lo que descargan. Para actualizar, la misma línea (o Veci se actualiza solo al abrirlo).

## Primeros pasos con el CLI

```bash
cd mi-proyecto
veci                       # o veci-cli
```

1. Escribe `/login`: se abre el navegador para crear tu cuenta de Veci o entrar.
2. Conecta tu modelo con `/model`: tu propia clave (NVIDIA, Groq, OpenRouter, DeepSeek y otros) o tu cuenta de un
   proveedor.
3. Pídele lo que necesites: *«arregla el error de la página de pagos y corre las pruebas»*.

### Comandos

| Comando | Qué hace |
|---|---|
| `/model` · `/effort` | Cambiar de modelo · cuánto piensa antes de responder |
| `/resume` · `/sessions` | Retomar una conversación guardada en tu computador |
| `/plan` · `shift+tab` | Ver el plan · pasar entre preguntar, aprobar solo y planear |
| `/diff` · `/context` · `/compact` | Cambios pendientes · uso del contexto · resumir para liberar contexto |
| `/init` | Analizar el proyecto y crear `VECI.md`, las reglas que el agente sigue ahí |
| `/chrome` | Conectar tu navegador |
| `/help` | Todo lo demás |

Opciones al abrir: `veci -C <carpeta>`, `veci --version`.

## Qué puede hacer

- **Una terminal con estilo propio**: pantalla completa, ratón para desplazarte, copiar y abrir cambios y enlaces, y le
  puedes escribir aunque esté trabajando.
- **Trabajar en tu código**: leer, buscar, editar y crear archivos; mostrarte cada cambio antes de aplicarlo.
- **Correr cosas de verdad**: comandos, varias shells a la vez, procesos en segundo plano, pruebas y compilaciones.
- **Tus servidores**: conectarse por SSH a tu VPS y trabajar ahí con las mismas herramientas.
- **Tu navegador**: abrir páginas, leerlas, hacer clic y escribir por ti, y preguntarte antes de lo arriesgado.
- **En tu celular**: la app crea apps y páginas, usa el teléfono (con tu permiso) y te cuenta lo que hace mientras lo hace.

## Privacidad

Tus conversaciones, tu código y la memoria de cada proyecto se quedan en tu equipo. Al modelo que elegiste solo le
llega lo necesario para cada paso. Veci no recoge analíticas; tu cuenta guarda tu correo, tu nombre y tus dispositivos.

## Versiones y ayuda

- **Novedades**: [CHANGELOG.md](CHANGELOG.md) y las releases de este repositorio.
- **Documentación**: [ia.vecipp.com/docs](https://ia.vecipp.com/docs).

<!-- vecipp:pie — generado por aplicar-marca: no editar a mano, se regenera -->
---

## 🌎 Sobre Vecipp

**Vecipp** es un ecosistema tecnológico latinoamericano que reúne en una sola cuenta la gestión de los negocios, la vida
del barrio y la inteligencia artificial. Nació en un pueblo de Colombia con un sueño más grande que el lugar donde
empezó: demostrar que desde Latinoamérica se crea tecnología de clase mundial, y llegar a millones de personas
haciéndoles la vida más fácil. [Nuestra historia, misión y visión](https://github.com/Vecipp/Vecipp-Negocio#nuestra-historia).

| Documento | Para qué |
|---|---|
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Cómo se trabaja en este repositorio |
| [`SECURITY.md`](SECURITY.md) | Cómo reportar una vulnerabilidad |
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | Código de conducta |
| [`LICENSE.md`](LICENSE.md) | Licencia |

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/logo-vecipp-blanco.svg">
    <img src=".github/assets/logo-vecipp.svg" alt="Vecipp" height="44">
  </picture><br>
  <sub>Diseñado y desarrollado por los ingenieros de software <b>Yilmer Carrillo Diaz</b> y <b>Yeferson Carrillo Diaz</b> · © 2026 · Hecho en Colombia 🇨🇴 para Latinoamérica y el mundo</sub>
</p>
<!-- /vecipp:pie -->
