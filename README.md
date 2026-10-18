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

**Vecipp IA** es un agente de programación con IA. Lee y edita tu código, corre comandos, se conecta por SSH a tus
servidores, usa el navegador y entrega documentos, páginas y diseños listos para ver. Una sola cuenta Vecipp para los
tres:

| | Para qué | Dónde trabaja |
|---|---|---|
| 🖥️ **CLI** (`vecipp`) | El agente completo en tu terminal | Tu PC o tu VPS: cualquier carpeta, varias shells, SSH, bases de datos, pruebas |
| 🪟 **Escritorio** | El mismo agente con ventana propia | Las carpetas de tu PC |
| 🌐 **Web** ([ia.vecipp.com](https://ia.vecipp.com)) | Chat, y **Código en la nube** sobre tus repos de GitHub | El navegador, sin instalar nada |

Tu uso, tus sesiones y tus artefactos se comparten entre los tres.

## Instalación

**Windows** (PowerShell):

```powershell
irm https://ia.vecipp.com/install.ps1 | iex
```

**macOS · Linux · VPS**:

```bash
curl -fsSL https://ia.vecipp.com/install.sh | bash
```

No piden permisos de administrador ni `sudo`: si no tienes Node.js 20+, instalan uno solo para tu usuario, y comprueban
la firma SHA-256 de todo lo que descargan. Para actualizar, la misma línea.

**Escritorio para Windows**: [descargar el instalador](https://ia.vecipp.com/descargas) (también en
[Releases](https://github.com/Vecipp/Vecipp-IA-Releases/releases/latest)).

## Primeros pasos

```bash
cd mi-proyecto
vecipp                     # o vecipp-cli
```

1. Escribe `/login` e inicia sesión con tu cuenta Vecipp (se abre el navegador).
2. Elige el proveedor **Vecipp IA** con `/provider`: usa tu cuenta, sin API key. (También puedes traer tu propia API key
   de NVIDIA, Groq, OpenRouter y otros.)
3. Pídele lo que necesites: *«arregla el error de la página de pagos y corre las pruebas»*.

### Comandos

| Comando | Qué hace |
|---|---|
| `/model` | Cambiar de modelo (`/model auto`: el más fuerte disponible que responda) |
| `/uso` | Tu uso: la sesión de 5 horas y la semana, el mismo de la web y el escritorio |
| `/artifacts` · `/open` | Los documentos, páginas y diseños que creó el agente, con su enlace en ia.vecipp.com |
| `/sync on\|off` | Ver tus sesiones de la terminal en [ia.vecipp.com/code](https://ia.vecipp.com/code) |
| `/resume` · `/sessions` · `/history` | Retomar una sesión guardada |
| `/plan` · `/planmode` · `/auto` | Ver el plan · pedir permiso en cada acción · aprobar cambios solo |
| `/diff` · `/context` · `/compact` | Cambios pendientes · uso del contexto · resumir para liberar contexto |
| `/init` | Analizar el proyecto y crear `VECIPP.md` |
| `/tools` · `/agent` · `/help` | Herramientas disponibles · rol del agente · ayuda |

Opciones al abrir: `vecipp -C <carpeta>`, `vecipp --version`.

## Qué puede hacer

- **Una terminal con estilo propio**: pantalla completa inspirada en Kali Linux, prompt `┌──(vecipp㉿proyecto)` fijo
  abajo, terminal translúcida (`/appearance`), ratón para desplazarte, copiar y abrir cambios y enlaces, y modo root con
  `shift+tab`. Le puedes escribir aunque esté trabajando; `ctrl+b` manda lo escrito y mueve el turno al fondo (`esc`
  lo para).
- **Trabajar en tu código**: leer, buscar, editar y crear archivos; mostrarte cada cambio antes de aplicarlo.
- **Correr cosas de verdad**: comandos, varias shells a la vez, procesos en segundo plano, pruebas y compilaciones.
- **Tus servidores**: conectarse por SSH a tu VPS y trabajar ahí con las mismas herramientas.
- **Artefactos al instante**: los documentos, páginas y diseños que crea se guardan en tu cuenta y se abren solos en
  el navegador, ya renderizados.
- **Tu historial en todas partes**: tus sesiones de la terminal y el escritorio se ven en la web.
- **Un solo uso para todo**: la sesión de 5 horas y la semana son las mismas en la web, la CLI y el escritorio.

## Planes

Hay un plan **Gratis** con uso que se renueva cada 5 horas y cada semana, y planes con más uso y más modelos. Precios y
detalles en [ia.vecipp.com/precios](https://ia.vecipp.com/precios). Con tu propia API key, la CLI y el escritorio no
gastan tu plan.

## Privacidad

Tu código se queda en tu equipo: el agente lee y edita archivos ahí. Al modelo solo le llega lo necesario para cada
paso. Los artefactos y las sesiones sincronizadas se guardan en tu cuenta, y puedes apagarlo (`/sync off`,
`/artifacts open off`).

## Versiones y ayuda

- **Novedades**: [CHANGELOG.md](CHANGELOG.md) y [Releases](https://github.com/Vecipp/Vecipp-IA-Releases/releases).
- **Documentación**: [ia.vecipp.com/docs](https://ia.vecipp.com/docs).
- **Soporte**: [soporte.vecipp.com](https://soporte.vecipp.com).

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
