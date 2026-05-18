# <p align="center">⚡ CEPLAYA-BOT MULTI-USE MINI ⚡</p>

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

---

## 🔮 ¿Qué es Cepaya-Bot Multi-Uso?

Cepaya-Bot es una suite de automatización híbrida y modular para WhatsApp construida sobre el ecosistema multipropósito de Baileys (WhiskeySockets). A diferencia de los bots lineales tradicionales, Cepaya-Bot actúa como un asistente integral Multi-uso, capaz de gestionar desde entretenimiento y multimedia, hasta utilidades del sistema, administración avanzada de grupos y soporte conversacional mediante Inteligencia Artificial.

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
| **🎬 3. Multimedia** | Procesamiento WebP/Streams | Conversión a stickers estáticos/animados, estilo brat y streaming (<50MB).
| **🛡️ 4. Moderación** | Sistema Guardián Activo | Anti-links, anti-llamadas, muteo por flood y borrado temporal cada 6 horas. |
| **🧠 5. Inteligencia** | Pipeline NLU Integrado | Respuestas offline (Llama.cpp) o en la nube (OpenAI, Gemini, Claude).

<br/>

### 🔍 Detalle del Filtro Anti-Fallas Gramaticales
El bot cuenta con un depurador sintáctico incorporado capaz de normalizar entradas complejas de usuarios:
```text
"me puedes decir el clima de Nueva York" ➔ "clima Nueva York"
"quisiera saber el precio del bitcoin"    ➔ "precio bitcoin"
"necesito un sticker de un perro"        ➔ "sticker perro"
```
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
##  🗂️ Estructura del Proyecto (Ampliada)
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
├── 📄 ecosystem.config.js          # Configuración nativa para PM2
└── 📄 index.js                    # Punto de entrada al hilo principal
```
## 📥 Instalación y Despliegue
Selecciona tu plataforma de ejecución para ver las instrucciones requeridas:

```text
# 1. Actualizar el entorno interno
pkg update -y && pkg upgrade -y

# 2. Instalar binarios y dependencias multimedia esenciales
pkg install git nodejs-lts ffmpeg imagemagick yarn -y

# 3. Clonar repositorio e ingresar a la raíz
git clone [https://github.com/RoberthCepaya/CepayaBot-MD.git](https://github.com/RoberthCepaya/CepayaBot-MD.git)
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
 ##  📝 Ejemplos de Interacción Nativos
Comandos Generales y Media

```text
/help           # Despliega el catálogo completo de comandos activos
/ping           # Retorna la latencia exacta del servidor (<50ms)
/sticker        # Procesa imágenes/videos convirtiéndolos a WebP dinámicos
/yt <enlace>    # Descarga streams de audio/video filtrando buffers
/clima <ciudad> # Consulta meteorológica en tiempo real mediante API

```

---

## ⚡ Optimizaciones de Rendimiento

El núcleo del bot está diseñado bajo estándares de alta disponibilidad, implementando estrategias a nivel de software para mitigar el impacto en el hardware:

* 🧠 **Caché de Comandos LRU**<br/>Estructuras recursivas indexadas en memoria RAM con un límite estricto de 200 items flotantes para acelerar las búsquedas de triggers y optimizar el tiempo de respuesta.
* 🖼️ **Compresión Gráfica Asíncrona**<br/>Redimensionamiento estricto a $512 \times 512$ píxeles antes de la inyección en los codificadores de stickers, reduciendo drásticamente el consumo de ancho de banda y almacenamiento temporal.
* 💤 **Lazy Loading (Carga Perezosa)**<br/>Los módulos pesados y las librerías externas se importan únicamente bajo demanda cuando el usuario ejecuta el comando, manteniendo el proceso inicial del núcleo sumamente ligero.
* 🌐 **Pool de Conexiones Activas**<br/>Reutilización de sockets abiertos mediante agentes HTTP/HTTPS dedicados (`keep-alive`) para evitar el agotamiento de puertos en peticiones concurrentes a APIs externas.
* 🧹 **Garbage Collection Forzado**<br/>Ejecución interna y cíclica de recolección de basura cada 6 horas para forzar la liberación de bloques de memoria RAM retenidos por buffers multimedia.

<br/>



---

## ⚠️ Descargo de Responsabilidad (Disclaimer) & Privacidad

Este proyecto ha sido desarrollado exclusivamente con **fines educativos, de investigación y desarrollo de software**.

* 🚫 **Sin Relación Oficial:** Este repositorio y su creador no poseen ninguna vinculación, patrocinio ni autorización oficial por parte de **WhatsApp Inc.**, Meta Platforms Inc., ni ninguna de sus subsidiarias. El término "WhatsApp" es propiedad y marca registrada de sus respectivos titulares.
* ⚖️ **Uso Responsable:** La automatización mediante librerías de terceros puede contradecir los términos legales de la plataforma oficial. El autor **no asume responsabilidades** por bloqueos de credenciales, suspensiones de líneas telefónicas, pérdidas de historial o sanciones derivadas.
* ⚙️ **Riesgo Operativo:** El despliegue de las instancias corre bajo absoluto criterio, riesgo y responsabilidad del administrador final.
* 🔒 **Protección y Privacidad de Datos:** El ecosistema almacena registros localmente en formatos JSON (`database/`). Es responsabilidad absoluta de quien aloja la instancia asegurar el cumplimiento normativo de privacidad de datos (**GDPR, CCPA**, etc.) de su respectiva jurisdicción.

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
  <a href="https://github.com/RoberthCepaya/CepayaBot-MD/issues" target="_blank">
    <img src="https://img.shields.io/badge/GitHub_Issues-181717?style=for-the-badge&logo=github&logoColor=white" alt="Issues"/>
  </a>
</p>

<br/>

| Canal de Comunicación | Propósito | Enlace Directo |
| :--- | :--- | :--- |
| 💬 **Comunidad WhatsApp** | Grupo oficial de soporte, betas y anuncios del bot. | [Unirme al Grupo](#) |
| 📸 **Instagram Oficial** | Desarrollo diario, novedades y contenido rápido. | [Seguir en Instagram](#) |
| 📘 **Facebook Fanpage** | Lanzamientos oficiales, guías largas y directos. | [Seguir en Facebook](#) |
| 📧 **Correo de Contacto** | Consultas comerciales, colaboraciones o soporte privado. | `robertcepaya@gmail.com` |

---
<p align="center">
  ⭐ <b>¡Si te gusta el proyecto, no olvides dejar una estrella para apoyar el desarrollo!</b> ⭐<br/>
  Reportar Bug • Solicitar Feature • Ver Demo
</p>

<p align="center">Desarrollado con ❤️ por <b>Roberth Cepaya</b> — 2026</p>


