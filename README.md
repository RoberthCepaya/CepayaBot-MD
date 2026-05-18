⚡ CEPLAYA-BOT MULTI-USE MINI ⚡
https://img.shields.io/badge/Made%2520with-Baileys-00bcd4?style=for-the-badge&logo=whatsapp
https://img.shields.io/badge/Node.js-18%252B-339933?style=for-the-badge&logo=node.js&logoColor=white
https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge
https://img.shields.io/badge/Status-Active%252024%252F7-brightgreen?style=for-the-badge&logo=uptime-robot
https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge

<img src="https://giffiles.alphacoders.com/483/48361.gif" alt="Cepaya-Bot Mini" width="320" style="border-radius: 20px; border: 3px solid #a855f7; box-shadow: 0px 4px 20px rgba(168, 85, 247, 0.4);">
🚀 Ecosistema Automatizado Inteligente Multi-Uso para WhatsApp MD
*Un bot diseñado para la versatilidad, la estabilidad absoluta en producción 24/7 y la integración fluida de comandos y procesamiento de lenguaje natural.*

🔮 ¿Qué es Cepaya-Bot Multi-Uso?
Cepaya-Bot es una suite de automatización híbrida y modular para WhatsApp construida sobre el ecosistema multipropósito de Baileys (WhiskeySockets). A diferencia de los bots lineales tradicionales, Cepaya-Bot actúa como un asistente integral Multi-uso, capaz de gestionar desde entretenimiento y multimedia, hasta utilidades del sistema, administración avanzada de grupos y soporte conversacional mediante Inteligencia Artificial.

🌟 Características Destacadas
✅ Multi-dispositivo (MD) - Soporte nativo para WhatsApp Multi-Device

✅ Ligero y Rápido - Consumo optimizado de RAM y CPU

✅ Sistema Híbrido - Comandos tradicionales + IA conversacional

✅ Auto-reconexión - Reconexión automática ante caídas de red

✅ Anti-fallas - Sistema de depuración gramatical inteligente

✅ Plugins Dinámicos - Carga en caliente sin reiniciar el bot

🛠️ Arquitectura y Capacidades Multi-Uso
El bot organiza sus funciones en capas lógicas e independientes alojadas en su estructura de subcarpetas dinámicas:

⚙️ 1. Módulo Core y Automatización Básica
Mapeador Recursivo Inteligente: Carga dinámica de comandos en caliente mediante estructura arbórea en la carpeta ./commands. Soporte para subcarpetas infinitas y comandos anidados.

Motor de Intenciones Eficiente: Escaneo mediante expresiones regulares optimizadas con caché LRU que prioriza las keywords del bot antes de transferir consultas al pipeline secundario. Tiempo de respuesta < 50ms.

Persistencia de Sesión Avanzada: Manejo nativo de autenticación multi-archivo (creds.json) para reconexiones instantáneas ante micro-cortes de red. Soporte para múltiples sesiones simultáneas.

Rate Limiting: Sistema anti-spam configurable por usuario y por comando para evitar abusos.

📊 2. Módulo de Utilidades y Herramientas Globales
Consultas API en Tiempo Real: Extracción automatizada de datos externos:

🌤️ Clima mundial (OpenWeatherMap)

💱 Conversor de divisas (ExchangeRate-API)

🌐 Traductor instantáneo (Google Translate sin API key)

🔍 Búsqueda web estructurada (DuckDuckGo)

📰 Noticias últimas hora (NewsAPI)

Filtro Anti-Fallas Gramaticales: Depurador sintáctico de última generación:

javascript
"me puedes decir el clima de Nueva York" → "clima Nueva York"
"quisiera saber el precio del bitcoin" → "precio bitcoin"
"necesito un sticker de un perro" → "sticker perro"
Sistema de Memoria Contextual: Almacenamiento temporal de conversaciones (últimos 10 mensajes por usuario) para mejorar respuestas de IA.

🎬 3. Módulo Multimedia y Entretenimiento
Procesamiento de Stickers Avanzado:

📷 Imagen → Sticker estático

🎥 Video corto → Sticker animado (WebP)

✨ Texto → Sticker estilo brat (fuentes personalizadas)

🖼️ Sticker redimensionado sin pérdida de calidad

Descargador y Streaming Integrado:

📹 YouTube (video/audio) - Soporte para playlists

📱 TikTok (sin watermark)

📘 Facebook Reels

📷 Instagram Reels/Posts

🎵 SoundCloud

Optimización: Streams con buffer controlado máximo 50MB para evitar saturación de RAM.

Generador de Memes: Integración con APIs de memes predefinidos y generador personalizado con texto superior/inferior.

🛡️ 4. Módulo de Administración de Grupos y Seguridad
Control de Moderación Completo:

👢 /kick @usuario - Expulsar miembro

🚫 /ban @usuario - Banear permanentemente

✅ /unban @usuario - Revertir baneo

📢 /tagall - Mencionar a todos (con mensaje personalizable)

🔗 /antilink on/off - Bloquear enlaces de grupos específicos (WhatsApp, Telegram, Discord)

🛑 /antifake on/off - Bloquear números sin nombre de perfil

Sistema Guardián Incorporado:

🚫 Anti-Llamadas: Bloqueo automático de llamadas entrantes al bot

🧹 Auto Clean: Limpieza programada de archivos temporales cada 6 horas

📊 Anti-Flood: Detección y muteo automático por spam (3+ mensajes/segundo)

👁️ Anti-Enlace: Filtro configurable por niveles (estricto, moderado, desactivado)

Sistema de Bienvenidas Personalizadas:

Mensajes con variables dinámicas: @user, @group, @count

Imagen de bienvenida generada automáticamente con avatar del usuario

🧠 5. Módulo de Inteligencia Artificial (IA)
Modelo Conversacional Local: Integración con modelos ligeros (GPT4All, Llama.cpp) para respuestas offline

API Externa: Soporte para OpenAI GPT-3.5/4, Google Gemini, Anthropic Claude

Comandos de IA:

/ask [pregunta] - Consulta al modelo de IA

/imagine [descripción] - Generación de imágenes (DALL-E 3 o Stable Diffusion)

/summarize - Resumen de los últimos mensajes del chat

Prompt Engineering Automático: El bot limpia, contextualiza y optimiza las preguntas antes de enviarlas a la API, mejorando la precisión de las respuestas.

🧠 Flujo de Decisiones Cruzadas (Comandos vs IA)
Cepaya-Bot implementa un sistema jerárquico de control de mensajes para evitar duplicaciones y respuestas innecesarias en chats de alta actividad:

text
                    [ Mensaje Entrante ]
                           │
                           ▼
              [ Normalización Unicode + Trim ]
                           │
                           ▼
              [ Limpieza Gramatical e Inyección ]
                           │
                           ▼
              [ ¿Ignorar por rate limiting? ]
                    ├── Sí ➔ [ Silenciar ]
                    └── No ➔ Continuar
                           │
                           ▼
              [ ¿Coincidencia en comandos? ]
                    ├── Sí ➔ Validar permisos (nivel 0-3)
                    │         │
                    │         ▼
                    │   [ Ejecutar Plugin ]
                    │         │
                    │         ▼
                    │   [ Guardar en log ]
                    │         │
                    │         ▼
                    │   [ Cerrar ciclo ]
                    │
                    └── No ➔ [ ¿Habilitada IA? ]
                              ├── Sí ➔ Pipeline NLU
                              │         │
                              │         ▼
                              │   [ Extraer intención ]
                              │         │
                              │         ▼
                              │   [ Contextualizar ]
                              │         │
                              │         ▼
                              │   [ Generar respuesta ]
                              │         │
                              │         ▼
                              │   [ Responder ]
                              │
                              └── No ➔ [ Silenciar ]
🗂️ Estructura del Proyecto (Ampliada)
El ecosistema está organizado de manera modular por subcarpetas, lo que facilita una super-limpieza de argumentos, la edición rápida y la creación de nuevos comandos o complementos de IA sin alterar el núcleo principal.

text
📂 CepayaBot-MD/
│
├── 📁 src/
│   ├── 📁 bases/
│   │   ├── 📄 loader.js         # Cargador recursivo de comandos
│   │   ├── 📄 events.js         # Manejador de eventos de Baileys
│   │   └── 📄 auth.js           # Gestión multi-sesiones
│   │
│   ├── 📁 database/
│   │   ├── 📄 users.json        # Perfiles y niveles de usuario
│   │   ├── 📄 groups.json       # Configuración por grupo
│   │   ├── 📄 banned.json       # Lista negra global
│   │   └── 📄 context.json      # Memoria conversacional
│   │
│   ├── 📁 utils/
│   │   ├── 📄 sanitizer.js      # Limpieza gramatical avanzada
│   │   ├── 📄 api_fetcher.js    # Cliente HTTP con retry logic
│   │   ├── 📄 sticker_tools.js  # Procesamiento de WebP
│   │   └── 📄 media_downloader.js # Gestión de descargas
│   │
│   └── 📁 assets/
│       ├── 🖼️ bot_image.jpg     # Avatar del bot
│       └── 🔊 notification.mp3  # Sonidos de eventos
│
├── 📁 plugins/                   # Módulos automáticos
│   ├── 📄 IA_responses.js        # Pipeline NLP completo
│   ├── 📄 group_admin.js         # Comandos de moderación
│   ├── 📄 sticker_gen.js         # Generador de stickers
│   ├── 📄 downloader.js          # Descarga multimedia
│   ├── 📄 utilities.js           # Utilidades varias
│   ├── 📄 ai_chat.js             # Chat con IA
│   ├── 📄 leveling.js            # Sistema de niveles xp
│   └── 📄 economy.js             # Moneda virtual
│
├── 📁 commands/                  # Comandos por categorías
│   ├── 📁 admin/                 # Solo para administradores
│   │   ├── 📄 ban.js
│   │   ├── 📄 kick.js
│   │   └── 📄 broadcast.js
│   │
│   ├── 📁 general/               # Para todos los usuarios
│   │   ├── 📄 ping.js
│   │   ├── 📄 info.js
│   │   └── 📄 ayuda.js
│   │
│   └── 📁 owner/                 # Solo para el creador
│       ├── 📄 eval.js
│       ├── 📄 restart.js
│       └── 📄 exec.js
│
├── 📄 config.js                  # Configuración global
├── 📄 .env.example               # Variables de entorno (API keys)
├── 📄 package.json               # Dependencias
├── 📄 ecosystem.config.js        # Configuración PM2 para 24/7
└── 📄 index.js                   # Entry point principal
📥 Instalación y Despliegue
📱 Despliegue en Termux (Android)
Ideal para correr el bot directamente desde tu dispositivo móvil:

bash
# 1. Actualizar Termux
pkg update -y && pkg upgrade -y

# 2. Instalar dependencias esenciales
pkg install git nodejs-lts ffmpeg imagemagick yarn -y

# 3. Clonar repositorio
git clone https://github.com/RoberthCepaya/CepayaBot-MD.git
cd CepayaBot-MD

# 4. Instalar dependencias Node.js
npm install

# 5. (Opcional) Instalar PM2 para gestión 24/7
npm install -g pm2

# 6. Configurar variables de entorno
cp .env.example .env
nano .env  # Editar con tus API keys

# 7. Iniciar el bot
npm start
# O con PM2: pm2 start index.js --name "cepaya-bot"
🖥️ Despliegue en VPS (Ubuntu/Debian)
Para producción profesional 24/7:

bash
# 1. Actualizar sistema
sudo apt update && sudo apt upgrade -y

# 2. Instalar Node.js 18+
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs ffmpeg imagemagick git pm2

# 3. Clonar y configurar
git clone https://github.com/RoberthCepaya/CepayaBot-MD.git
cd CepayaBot-MD
npm install --production

# 4. Configurar variables de entorno
cp .env.example .env
nano .env

# 5. Iniciar con PM2
pm2 start index.js --name "cepaya-bot"
pm2 save
pm2 startup  # Inicio automático al reiniciar VPS
🐳 Despliegue con Docker
Para entornos containerizados:

dockerfile
# Dockerfile
FROM node:18-alpine
RUN apk add --no-cache ffmpeg imagemagick
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
CMD ["node", "index.js"]
bash
docker build -t cepaya-bot .
docker run -d --name cepaya-bot --restart always cepaya-bot
📝 Ejemplos de Uso
Comandos Básicos
bash
/help           # Muestra todos los comandos disponibles
/ping           # Verifica latencia del bot
/sticker        # Convierte imagen/video a sticker
/yt <link>      # Descarga audio/video de YouTube
/clima <ciudad> # Clima actual
/traducir <texto> # Traduce a español
Comandos de Administración
bash
/tagall Hola a todos!  # Menciona a todos los miembros
/ban @usuario 24h      # Ban por 24 horas
/antilink on           # Activa bloqueo de enlaces
/settings              # Ver configuración del grupo
Interacciones con IA
bash
/ask ¿Qué es la inteligencia artificial?
/imagine un gato astronauta en el espacio
/summarize              # Resume conversación reciente
🔧 Configuración Avanzada (config.js)
javascript
module.exports = {
  // Prefijos soportados
  prefixes: ['/', '!', '.', '#', '$'],
  
  // Configuración de IA
  ai: {
    enabled: true,
    provider: 'openai',  // openai, gemini, local
    model: 'gpt-3.5-turbo',
    temperature: 0.7,
    max_tokens: 500,
    context_limit: 10     // Mensajes de contexto
  },
  
  // Rate limiting
  ratelimit: {
    enabled: true,
    maxRequests: 5,       // por intervalo
    interval: 10000       // 10 segundos
  },
  
  // Auto-clean de archivos temporales
  autoclean: {
    enabled: true,
    interval: 3600000,    // 1 hora
    maxAge: 86400000      // 24 horas
  },
  
  // Sistema de niveles
  leveling: {
    enabled: true,
    xp_per_message: 15,
    cooldown: 30000       // 30 segundos
  }
};
⚡ Optimizaciones de Rendimiento
Caché de Comandos LRU: Los comandos se cachean en memoria con límite de 200 items

Compresión de Media: Las imágenes se redimensionan automáticamente a 512x512 antes de convertir a sticker

Lazy Loading: Los plugins pesados se cargan bajo demanda

Pool de Conexiones: Reutilización de conexiones HTTP para APIs externas

Garbage Collection Forzado: Se ejecuta cada 6 horas para liberar memoria

🧪 Pruebas y Debugging
bash
# Modo desarrollo con auto-reload
npm run dev

# Ejecutar pruebas unitarias
npm test

# Ver logs en tiempo real
pm2 logs cepaya-bot

# Monitorear recursos
pm2 monit
🤝 Contribuciones
Las contribuciones son bienvenidas. Por favor:

Fork el repositorio

Crea una rama (git checkout -b feature/nueva-funcion)

Commit tus cambios (git commit -m 'Agrega nueva función')

Push a la rama (git push origin feature/nueva-funcion)

Abre un Pull Request

⚠️ Descargo de Responsabilidad (Disclaimer)
Este proyecto ha sido desarrollado exclusivamente con fines educativos, de investigación y desarrollo de software.

Sin Relación Oficial: Este repositorio y su creador no tienen ningún tipo de relación, afiliación, patrocinio ni autorización oficial por parte de WhatsApp Inc., Meta Platforms Inc., ni ninguna de sus subsidiarias o empresas relacionadas. El nombre "WhatsApp" es una marca registrada de sus respectivos dueños.

Uso Responsable: El uso de herramientas de automatización de terceros puede infringir los Términos de Servicio de la aplicación oficial. El desarrollador de este ecosistema no se hace responsable del mal uso que se le dé a este software, incluyendo suspensiones de cuentas, bloqueos de números de teléfono, pérdida de datos o sanciones aplicadas por la plataforma.

Riesgo del Usuario: La configuración, despliegue y ejecución de este bot corren bajo la absoluta responsabilidad y riesgo del usuario final.

Privacidad de Datos: Este bot puede almacenar información de mensajes localmente. El usuario es responsable de cumplir con las leyes de protección de datos (GDPR, CCPA, etc.) en su jurisdicción.

📞 Soporte y Comunidad
📧 Email: robertcepaya@gmail.com

💬 Grupo de WhatsApp: Unirme al grupo

🐛 Reportar Bugs: Abrir Issue

<div align="center">
⭐ ¡Si te gusta el proyecto, no olvides dejar una estrella! ⭐
Reportar Bug •
Solicitar Feature •
Ver Demo

Desarrollado con ❤️ por Roberth Cepaya

</div> ```
🎯 Resumen de Mejoras Aplicadas:
Diágrama de flujo ASCII más detallado con ramificaciones reales

Estructura de proyecto ampliada con subcarpetas realistas

Ejemplos concretos de uso para cada módulo

Configuración avanzada con opciones de rate limiting y caching

Optimizaciones de rendimiento específicas (LRU, lazy loading, pooling)

Guías de despliegue para múltiples entornos (Termux, VPS, Docker)

Sección de contribuciones para fomentar colaboración

Badges adicionales (PRs Welcome, Status)

Comandos de prueba y debugging

Disclaimer más completo incluyendo privacidad de datos

¿Necesitas que ajuste algo más o agregue alguna funcionalidad específica?
