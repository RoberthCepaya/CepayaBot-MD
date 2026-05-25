# <p align="center">⚡ CEPAYA-BOT MULTI-USE MINI ⚡</p>

<p align="center">
  <img src="https://img.shields.io/badge/Made%20with-Baileys-00bcd4?style=for-the-badge&logo=whatsapp" alt="Baileys"/>
  <img src="https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node"/>
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge" alt="License"/>
  <img src="https://img.shields.io/badge/Status-Active%2024%2F7-brightgreen?style=for-the-badge&logo=uptime-robot" alt="Status"/>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge" alt="PRs"/>
</p>

<p align="center">
  <img src="https://giffiles.alphacoders.com/483/48361.gif" alt="Cepaya-Bot Mini" width="320" style="border-radius: 20px; border: 3px solid #a855f7; box-shadow: 0px 4px 20px rgba(168, 85, 247, 0.4);"/>
</p>

<p align="center"><b>Ecosistema Automatizado Inteligente Multi-Uso para WhatsApp MD</b><br/>
<i>Un bot diseñado para la versatilidad, la estabilidad absoluta en producción 24/7 y la integración fluida de comandos y procesamiento de lenguaje natural.</i></p>

<p align="center">
  <a href="#-qué-es-cepaya-bot-multi-uso">🔮 ¿Qué es?</a> •
  <a href="#-características-destacadas">🌟 Características</a> •
  <a href="#-arquitectura-y-capacidades-multi-uso">🛠️ Módulos</a> •
  <a href="#-flujo-de-decisiones-cruzadas-comandos-vs-ia">🧠 Flujo IA</a> •
  <a href="#-estructura-del-proyecto-ampliada">🗂️ Estructura</a> •
  <a href="#-instalación-y-despliegue">📥 Instalación</a> •
  <a href="#-configuración-del-entorno">⚙️ Configuración</a> •
  <a href="#-comandos-disponibles">💬 Comandos</a> •
  <a href="#-contribuir">🤝 Contribuir</a>
</p>

---

## 🔮 ¿Qué es Cepaya-Bot Multi-Uso?

**Cepaya-Bot** es una suite de automatización híbrida y modular para WhatsApp construida sobre el ecosistema multipropósito de **Baileys** (WhiskeySockets). A diferencia de los bots lineales tradicionales, Cepaya-Bot actúa como un asistente integral **Multi-Uso**, capaz de gestionar desde entretenimiento y multimedia, hasta utilidades del sistema, administración avanzada de grupos y soporte conversacional mediante Inteligencia Artificial.

Su arquitectura está completamente optimizada para entornos de ejecución continua (**24/7**), garantizando un consumo de recursos mínimo y un ciclo de vida persistente libre de caídas.

<br/>

---

## 🌟 Características Destacadas

* 📱 **Multi-dispositivo (MD):** Soporte nativo para WhatsApp Multi-Device.
* ⚡ **Ligero y Rápido:** Consumo optimizado de RAM y CPU.
* 🧠 **Sistema Híbrido:** Comandos tradicionales + IA conversacional sin triggers fijos.
* 🔄 **Auto-reconexión:** Reconexión automática ante micro-caídas de red.
* 🛠️ **Anti-fallas:** Sistema de depuración y sanitización gramatical inteligente.
* 📦 **Plugins Dinámicos:** Carga en caliente sin necesidad de reiniciar el bot completo.

<br/>

---

## 🛠️ Arquitectura y Capacidades Multi-Uso

| Módulo Core | Funcionalidad Clave | Propósito Técnico |
| :--- | :--- | :--- |
| **⚙️ 1. Core & Carga** | Mapeador Recursivo | Carga de comandos en caliente mediante estructura arbórea en `./commands`. |
| **📊 2. Utilidades** | Consultas API e Interfaz | Extracción de clima, divisas, traductores nativos y filtros de fallas. |
| **🎬 3. Multimedia** | Procesamiento WebP/Streams | Conversión a stickers estáticos/animados, estilo brat y streaming (<50MB). |
| **🛡️ 4. Moderación** | Sistema Guardián Activo | Anti-links, anti-llamadas, muteo por flood y borrado temporal cada 6 horas. |
| **🧠 5. Inteligencia** | Pipeline NLU Integrado | Respuestas offline (Llama.cpp) o en la nube (OpenAI, Gemini, Claude). |

<br/>

### ⚙️ Módulo 1 — Core y Automatización Básica

| Característica | Descripción |
| :--- | :--- |
| 🗂️ **Mapeador Recursivo** | Carga dinámica de comandos en caliente mediante estructura arbórea en `./commands` |
| 🔍 **Motor de Intenciones** | Escaneo inteligente con regex que prioriza keywords antes de pasar al pipeline de IA |
| 💾 **Persistencia de Sesión** | Autenticación multi-archivo para reconexiones instantáneas ante micro-cortes de red |

### 📊 Módulo 2 — Utilidades y Herramientas Globales

| Característica | Descripción |
| :--- | :--- |
| 🌐 **Consultas API en Tiempo Real** | Clima mundial, divisas, traductores y búsquedas web estructuradas |
| 🧹 **Filtro Anti-Fallas Gramaticales** | Depurador sintáctico que limpia conectores coloquiales antes de enviar a APIs externas, eliminando errores 404 |

### 🔍 Detalle del Filtro Anti-Fallas Gramaticales

El bot cuenta con un depurador sintáctico incorporado capaz de normalizar entradas complejas de usuarios:

```text
"me puedes decir el clima de Nueva York" ➔ "clima Nueva York"
"quisiera saber el precio del bitcoin"    ➔ "precio bitcoin"
"necesito un sticker de un perro"        ➔ "sticker perro"
```

### 🎬 Módulo 3 — Multimedia y Entretenimiento

| Característica | Descripción |
| :--- | :--- |
| 🖼️ **Stickers Avanzados** | Generación de stickers estáticos, animados y conversión texto→sticker estilo *brat* |
| ⬇️ **Descargador Integrado** | Descarga directa de Audio/Video desde YouTube, TikTok, Facebook e Instagram con streams optimizados |

### 🛡️ Módulo 4 — Administración de Grupos y Seguridad

| Característica | Descripción |
| :--- | :--- |
| 👮 **Control de Moderación** | Ban, Kick, Unban, tags masivos y configuración de enlaces e invitaciones |
| 🔒 **Sistema Guardián** | Anti-Call System automático y limpieza programada de archivos residuales (*Auto Clean Trash*) |

<br/>

---

## 🧠 Flujo de Decisiones Cruzadas (Comandos vs IA)

Cepaya-Bot implementa un sistema jerárquico de control de mensajes para evitar duplicaciones y respuestas innecesarias en chats de alta actividad:

```text

                   [ 💬 Mensaje Entrante ]
                               │
                               ▼
                [ 🛠️ Normalización Unicode + Trim ]
                               │
                               ▼
                [ 🧹 Limpieza Gramatical e Inyección ]
                               │
                               ▼
                [ ⏳ ¿Ignorar por rate limiting? ]
                     ├── 🟢 Sí ➔ [ Silenciar ]
                     └── 🔴 No ➔ Continuar
                               │
                               ▼
                [ 🔍 ¿Coincidencia en comandos? ]
                     ├── 🟢 Sí ➔ Validar permisos (nivel 0-3)
                     │            │
                     │            ▼
                     │       [ ⚙️ Ejecutar Plugin ]
                     │            │
                     │            ▼
                     │       [ 📝 Guardar en log ]
                     │            │
                     │            ▼
                     │       [ 🛑 Cerrar ciclo ]
                     │
                     └── 🔴 No ➔ [ 🤖 ¿Habilitada IA? ]
                                   ├── 🟢 Sí ➔ Pipeline NLU
                                   │            │
                                   │            ▼
                                   │       [ 🎯 Extraer intención ]
                                   │            │
                                   │            ▼
                                   │       [ 📂 Contextualizar ]
                                   │            │
                                   │            ▼
                                   │       [ 💬 Generar respuesta ]
                                   │            │
                                   │            ▼
                                   │       [ 📤 Responder ]
                                   │
                                   └── 🔴 No ➔ [ Silenciar ]
```

> Este diseño garantiza que **ningún mensaje sea procesado dos veces** y que el modelo de IA solo intervenga cuando ningún comando cubre la solicitud.

<br/>

---

## 🗂️ Estructura del Proyecto (Ampliada)

El ecosistema está organizado de manera modular por subcarpetas, lo que facilita una super-limpieza de argumentos, la edición rápida y la creación de nuevos comandos o complementos de IA sin alterar el núcleo principal.

```text

📂 CepayaBot-MD/
│
├── 📁 src/
│   ├── 📁 bases/
│   │   ├── 📄 loader.js           # Cargador recursivo de comandos
│   │   ├── 📄 events.js           # Manejador de eventos de Baileys
│   │   └── 📄 auth.js             # Gestión multi-sesiones (creds.json)
│   │
│   ├── 📁 database/
│   │   ├── 📄 users.json          # Perfiles y niveles de usuario
│   │   ├── 📄 groups.json         # Configuración por grupo
│   │   ├── 📄 banned.json         # Lista negra global
│   │   └── 📄 context.json        # Memoria conversacional temporal
│   │
│   ├── 📁 utils/
│   │   ├── 📄 sanitizer.js        # Limpieza gramatical avanzada
│   │   ├── 📄 api_fetcher.js      # Cliente HTTP con retry logic
│   │   ├── 📄 sticker_tools.js    # Procesamiento y conversión de WebP
│   │   └── 📄 media_downloader.js # Gestión de descargas y búfer
│   │
│   └── 📁 assets/
│       ├── 🖼️ bot_image.jpg       # Avatar oficial del bot
│       └── 🔊 notification.mp3    # Sonidos de eventos del sistema
│
├── 📁 plugins/                    # Módulos automáticos de eventos
│   ├── 📄 IA_responses.js         # Pipeline NLP completo sin triggers fijos
│   ├── 📄 group_admin.js          # Comandos internos de moderación
│   ├── 📄 sticker_gen.js          # Generador de stickers (Brat/Multimedia)
│   ├── 📄 downloader.js           # Descargas (TikTok, YT, Reels)
│   ├── 📄 utilities.js            # Herramientas globales del sistema
│   ├── 📄 ai_chat.js              # Interfaz interactiva de la IA
│   ├── 📄 leveling.js             # Sistema de niveles y experiencia (XP)
│   └── 📄 economy.js              # Sistema de moneda virtual integrada
│
├── 📁 commands/                   # Árbol recursivo de comandos por rol
│   ├── 📁 admin/                  # Comandos de administración de grupos
│   │   ├── 📄 ban.js
│   │   ├── 📄 kick.js
│   │   └── 📄 broadcast.js
│   ├── 📁 general/                # Comandos de uso público
│   │   ├── 📄 ping.js
│   │   ├── 📄 info.js
│   │   └── 📄 ayuda.js
│   └── 📁 owner/                  # Herramientas críticas del desarrollador
│       ├── 📄 eval.js
│       ├── 📄 restart.js
│       └── 📄 exec.js
│
├── 📄 config.js                   # Ajustes globales y límites del sistema
├── 📄 .env.example                # Variables de entorno críticas
├── 📄 package.json                # Gestión de módulos npm
├── 📄 ecosystem.config.js         # Configuración nativa para PM2
└── 📄 index.js                    # Punto de entrada al hilo principal
```

<br/>

---

## 📥 Instalación y Despliegue

### Requisitos previos

- **Node.js** v18 o superior
- **npm** o **yarn**
- **ffmpeg** e **imagemagick** (para procesamiento multimedia)
- Una cuenta de WhatsApp activa

```bash
# 1. Actualizar el entorno interno
pkg update -y && pkg upgrade -y

# 2. Instalar binarios y dependencias multimedia esenciales
pkg install git nodejs-lts ffmpeg imagemagick yarn -y

# 3. Clonar repositorio e ingresar a la raíz
git clone https://github.com/RoberthCepaya/CepayaBot-MD.git
cd CepayaBot-MD

# 4. Instalar árbol de dependencias Node.js
npm install

# 5. Instalar PM2 para persistencia en segundo plano (Opcional)
npm install -g pm2

# 6. Configurar variables de entorno iniciales
cp .env.example .env
nano .env  # Configura tus API keys aquí

# 7. Ejecutar el hilo del ecosistema
npm start
# O con PM2: pm2 start index.js --name "cepaya-bot"
```

> Al iniciar por primera vez, escanea el **código QR** en la terminal con tu WhatsApp para vincular la sesión.

<br/>

---

## ⚙️ Configuración del Entorno

Edita el archivo `.env` con tus credenciales y preferencias:

```env
# ── Ajustes generales ──────────────────────────────────────────
PREFIX=!                          # Prefijo de comandos
OWNER_NUMBER=51XXXXXXXXX          # Tu número (con código de país, sin +)
BOT_NAME=CepayaBot                # Nombre del bot

# ── APIs externas (opcionales) ─────────────────────────────────
OPENAI_API_KEY=tu_clave_aqui      # Para el pipeline de IA en la nube
WEATHER_API_KEY=tu_clave_aqui     # Para consultas de clima
GEMINI_API_KEY=tu_clave_aqui      # Alternativa a OpenAI

# ── Control de comportamiento ──────────────────────────────────
AI_ENABLED=true                   # Activar/desactivar el pipeline NLU
ANTI_CALL=true                    # Rechazar llamadas automáticamente
AUTO_CLEAN_HOURS=6                # Cada cuántas horas limpiar archivos temporales
RATE_LIMIT_MS=1500                # Cooldown entre respuestas (ms)
```

> **Nota:** Las claves de API son opcionales. Sin ellas, los módulos que las requieran estarán deshabilitados automáticamente.

<br/>

---

## 💬 Comandos Disponibles

> Usa el prefijo configurado (por defecto `!`) antes de cada comando. Para el catálogo completo, escribe `!menu` en el chat.

### 🛡️ Administración

| Comando | Descripción |
| :--- | :--- |
| `!ban @usuario` | Expulsa a un miembro del grupo |
| `!unban @usuario` | Desbanea a un miembro |
| `!kick @usuario` | Elimina a un participante sin ban |
| `!tag` | Etiqueta a todos los participantes |
| `!broadcast <mensaje>` | Envía un mensaje a todos los grupos |

### 🎬 Multimedia y Descargas

| Comando | Descripción |
| :--- | :--- |
| `!yt <URL>` | Descarga audio/video de YouTube |
| `!tiktok <URL>` | Descarga video de TikTok |
| `!ig <URL>` | Descarga contenido de Instagram/Reels |
| `!fb <URL>` | Descarga video de Facebook |
| `!sticker` | Convierte imagen o video a sticker WebP |
| `!brat <texto>` | Crea un sticker estilo *brat* |

### 🌐 Utilidades y APIs

| Comando | Descripción |
| :--- | :--- |
| `!clima <ciudad>` | Muestra el clima actual en tiempo real |
| `!moneda <X> a <Y>` | Convierte divisas al instante |
| `!translate <texto>` | Traduce texto automáticamente |
| `!ping` | Retorna la latencia exacta del servidor |
| `!info` | Muestra información del sistema y versión |

### 🤖 Inteligencia Artificial

| Comando | Descripción |
| :--- | :--- |
| `!ia <consulta>` | Activa el pipeline NLU directamente |
| `!contexto` | Muestra la memoria conversacional activa |
| `!resetia` | Limpia el contexto de la conversación |

<br/>

---

## ⚡ Optimizaciones de Rendimiento

El núcleo del bot está diseñado bajo estándares de alta disponibilidad, implementando estrategias a nivel de software para mitigar el impacto en el hardware:

* 🧠 **Caché de Comandos LRU** — Estructuras recursivas indexadas en memoria RAM con un límite estricto de 200 items flotantes para acelerar las búsquedas de triggers y optimizar el tiempo de respuesta.
* 🖼️ **Compresión Gráfica Asíncrona** — Redimensionamiento estricto a 512×512 píxeles antes de la inyección en los codificadores de stickers, reduciendo drásticamente el consumo de ancho de banda y almacenamiento temporal.
* 💤 **Lazy Loading** — Los módulos pesados y librerías externas se importan únicamente bajo demanda cuando el usuario ejecuta el comando, manteniendo el proceso inicial del núcleo sumamente ligero.
* 🌐 **Pool de Conexiones Activas** — Reutilización de sockets abiertos mediante agentes HTTP/HTTPS dedicados (`keep-alive`) para evitar el agotamiento de puertos en peticiones concurrentes a APIs externas.
* 🧹 **Garbage Collection Forzado** — Ejecución interna y cíclica de recolección de basura cada 6 horas para forzar la liberación de bloques de memoria RAM retenidos por buffers multimedia.

<br/>

---

## 🤝 Contribuir

¡Las contribuciones son bienvenidas! Si quieres añadir un nuevo módulo o mejorar uno existente:

1. Haz un **fork** del repositorio
2. Crea una rama: `git checkout -b feature/mi-nueva-funcion`
3. Realiza tus cambios y haz commit: `git commit -m 'feat: añadir nueva función'`
4. Haz push: `git push origin feature/mi-nueva-funcion`
5. Abre un **Pull Request**

Consulta el archivo [CONTRIBUTING.md](CONTRIBUTING.md) para las guías de estilo y convenciones de código.

<br/>

---

## ⚠️ Descargo de Responsabilidad (Disclaimer) & Privacidad

Este proyecto ha sido desarrollado exclusivamente con **fines educativos, de investigación y desarrollo de software**.

* 🚫 **Sin Relación Oficial:** Este repositorio y su creador no poseen ninguna vinculación, patrocinio ni autorización oficial por parte de **WhatsApp Inc.**, Meta Platforms Inc., ni ninguna de sus subsidiarias.
* ⚖️ **Uso Responsable:** La automatización mediante librerías de terceros puede contradecir los términos legales de la plataforma oficial. El autor **no asume responsabilidades** por bloqueos de credenciales, suspensiones de líneas telefónicas, pérdidas de historial o sanciones derivadas.
* ⚙️ **Riesgo Operativo:** El despliegue de las instancias corre bajo absoluto criterio, riesgo y responsabilidad del administrador final.
* 🔒 **Privacidad de Datos:** El ecosistema almacena registros localmente en formatos JSON (`database/`). Es responsabilidad de quien aloja la instancia asegurar el cumplimiento normativo (**GDPR, CCPA**, etc.) de su respectiva jurisdicción.

<br/>

---

## 📞 Soporte y Redes Oficiales

¡Conéctate con la comunidad y sigue las actualizaciones del proyecto en nuestras plataformas oficiales!

<p align="center">
  <a href="https://wa.me/51918583874" target="_blank">
    <img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp Group"/>
  </a>&nbsp;&nbsp;
  <a href="https://instagram.com/roberthcepaya" target="_blank">
    <img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram"/>
  </a>&nbsp;&nbsp;
  <a href="https://facebook.com/roberthccepaya" target="_blank">
    <img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" alt="Facebook"/>
  </a>&nbsp;&nbsp;
  <a href="https://github.com/RoberthCepaya/CepayaBot-MD" target="_blank">
    <img src="https://img.shields.io/badge/GitHub_Issues-181717?style=for-the-badge&logo=github&logoColor=white" alt="Issues"/>
  </a>
</p>

<br/>

| Canal de Comunicación | Propósito | Enlace Directo |
| :--- | :--- | :--- |
| 💬 **Comunidad WhatsApp** | Grupo oficial de soporte, betas y anuncios del bot. | [Unirme al Grupo](https://wa.me/51918583874) |
| 📸 **Instagram Oficial** | Desarrollo diario, novedades y contenido rápido. | [Seguir en Instagram](https://instagram.com/roberthcepaya) |
| 📘 **Facebook Fanpage** | Lanzamientos oficiales, guías largas y directos. | [Seguir en Facebook](https://facebook.com/roberthccepaya) |
| 📧 **Correo de Contacto** | Consultas comerciales, colaboraciones o soporte privado. | `robertcepaya@gmail.com` |

---

## 📄 Licencia

Este proyecto está bajo la licencia **MIT**. Consulta el archivo [LICENSE](LICENSE) para más información.

---

<p align="center">
  ⭐ <b>¡Si te gusta el proyecto, no olvides dejar una estrella para apoyar el desarrollo!</b> ⭐<br/><br/>
  <a href="https://github.com/RoberthCepaya/CepayaBot-MD/issues">Reportar Bug</a> •
  <a href="https://github.com/RoberthCepaya/CepayaBot-MD/issues">Solicitar Feature</a> •
  <a href="https://wa.me/51918583874">Ver Demo</a>
</p>

<p align="center">Desarrollado con ❤️ por <b>Roberth Cepaya</b> — 2026</p>

