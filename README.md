# CepayaBot-MD
Bot de WhatsApp Multi-Device (Baileys) de alto rendimiento, optimizado con un motor de intenciones dinámico por subcarpetas, super-limpieza de argumentos y procesamiento inteligente con IA.
<div align="center">

# ⚡ CEPLAYA-BOT MULTI-USE MINI ⚡

[![Made with Baileys](https://img.shields.io/badge/Made%20with-Baileys-00bcd4?style=for-the-badge&logo=whatsapp)](https://github.com/WhiskeySockets/Baileys)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Status: Active 24/7](https://img.shields.io/badge/Status-Active%2024%2F7-brightgreen?style=for-the-badge&logo=uptime-robot)](https://github.com/)

<img src="https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?q=80&w=600](https://giffiles.alphacoders.com/483/48361.gif" alt="Cepaya-Bot Mini" width="320" style="border-radius: 20px; border: 3px solid #a855f7; box-shadow: 0px 4px 20px rgba(168, 85, 247, 0.4);">

### 🚀 Ecosistema Automatizado Inteligente Multi-Uso para WhatsApp MD

*Un bot diseñado para la versatilidad, la estabilidad absoluta en producción 24/7 y la integración fluida de comandos y procesamiento de lenguaje natural.*

</div>

---

## 🔮 ¿Qué es Cepaya-Bot Multi-Uso?

**Cepaya-Bot** es una suite de automatización híbrida y modular para WhatsApp construida sobre el ecosistema multipropósito de **Baileys**. A diferencia de los bots lineales tradicionales, Cepaya-Bot actúa como un asistente integral **Multi-uso**, capaz de gestionar desde entretenimiento y multimedia, hasta utilidades del sistema, administración avanzada de grupos y soporte conversacional mediante Inteligencia Artificial.

Su arquitectura está completamente optimizada para entornos de ejecución continua (**24/7**), garantizando un consumo de recursos mínimo y un ciclo de vida persistente libre de caídas.

---

## 🛠️ Arquitectura y Capacidades Multi-Uso

El bot organiza sus funciones en capas lógicas e independientes alojadas en su estructura de subcarpetas dinámicas:

### ⚙️ 1. Módulo Core y Automatización Básica
* **Mapeador Recursivo:** Carga dinámica de comandos en caliente mediante estructura arbórea en la carpeta `./commands`.
* **Motor de Intenciones Eficiente:** Escaneo inteligente mediante expresiones regulares que prioriza las keywords del bot antes de transferir consultas al pipeline secundario.
* **Persistencia de Sesión:** Manejo nativo de autenticación multi-archivo para reconexiones instantáneas ante micro-cortes de red.

### 📊 2. Módulo de Utilidades y Herramientas Globales
* **Consultas API en Tiempo Real:** Extracción automatizada de datos externos (Clima mundial, divisas, traductores, búsquedas web estructuradas).
* **Filtro Anti-Fallas Gramaticales:** Depurador sintáctico que remueve conectores coloquiales (ej: *"me puedes decir el clima de..."*) entregando solo la consulta limpia a las APIs para erradicar errores de tipo 404 (Not Found).

### 🎬 3. Módulo Multimedia y Entretenimiento
* **Procesamiento de Stickers Avanzado:** Generadores dinámicos de stickers (estáticos, animados, conversión de texto a sticker estilo *brat* mediante APIs externas).
* **Descargador y Streaming Integrado:** Módulos de búsqueda y descarga directa de contenido multimedia (Audio/Video de YouTube, TikTok, Facebook e Instagram) con streams optimizados para no saturar el buffer de memoria.

### 🛡️ 4. Módulo de Administración de Grupos y Seguridad
* **Control de Moderación Completo:** Comandos automatizados de gestión (Ban, Kick, Unban, tags masivos, configuraciones de enlaces e invitaciones).
* **Sistema Guardián Incorporado:** Inicialización automatizada de filtros anti-llamadas (*Anti-Call System*) y limpieza programada de archivos residuales en el almacenamiento local (*Auto Clean Trash*).

---

## 🧠 Flujo de Decisiones Cruzadas (Comandos vs IA)

Cepaya-Bot implementa un sistema jerárquico de control de mensajes para evitar duplicaciones y respuestas innecesarias en chats de alta actividad:

```text
[ Mensaje Entrante ] 
         │
         ▼
[ Limpieza Gramatical e Inyección de Signos ]
         │
         ▼
[ ¿Existe coincidencia en subcarpetas de comandos? ]
         ├── Sí ➔ Ejecuta Plugin Modular (Cierra ciclo)
         └── No ➔ Transfiere control al Pipeline de IA (Procesando con IA)


## **🗂️ Estructura del Proyecto**

El ecosistema está organizado de manera modular por subcarpetas, lo que facilita una super-limpieza de argumentos, la edición rápida y la creación de nuevos comandos o complementos de IA sin alterar el núcleo principal.

```text
📂 CepayaBot-MD/
├── 📁 src/
│   ├── 📁 bases/          # Archivos esenciales y cargadores del sistema
│   ├── 📁 database/       # Gestión de datos, usuarios y configuraciones de grupos
│   └── 📁 utils/          # Herramientas multimedia y funciones secundarias (e.g. bot_image.jpg)
├── 📁 plugins/            # Módulos automáticos e independientes del bot
│   ├── 📄 IA_responses.js # Procesador inteligente de intenciones sin triggers fijos
│   ├── 📄 group_info.js   # Comandos y gestión de administración de grupos
│   ├── 📄 sticker_gen.js  # Creador de stickers (estilo brat y multimedia)
│   └── 📄 uptime.js       # Monitoreo de estado y actividad en el servidor
├── 📄 config.js           # Archivo global de configuraciones (tokens, prefijos, número)
├── 📄 package.json        # Dependencias principales del ecosistema (Baileys, etc.)
└── 📄 index.js            # Punto de arranque y conexión con el servidor


## **📥 Instalación y Despliegue**

Sigue los comandos detallados según el entorno donde vayas a desplegar el ecosistema de **CepayaBot-MD**.

### **📱 Despliegue en Termux (Android)**
Ideal para correr el bot directamente desde tu dispositivo móvil. Abre Termux y ejecuta los siguientes comandos uno por uno:

```bash
# 1. Actualizar el entorno de Termux
pkg update -y && pkg upgrade -y

# 2. Instalar herramientas básicas y Node.js
pkg install git nodejs ffmpeg imagemagick -y

# 3. Clonar el repositorio oficial
git clone [https://github.com/RoberthCepaya/CepayaBot-MD.git](https://github.com/RoberthCepaya/CepayaBot-MD.git)
cd CepayaBot-MD

# 4. Instalar las dependencias del sistema
npm install

# 5. Iniciar el bot y escanear el código QR
npm start


---

## **⚠️ Descargo de Responsabilidad (Disclaimer)**

Este proyecto ha sido desarrollado exclusivamente con **fines educativos, de investigación y desarrollo de software**. 

- **Sin Relación Oficial:** Este repositorio y su creador no tienen ningún tipo de relación, afiliación, patrocinio ni autorización oficial por parte de **WhatsApp Inc.**, Meta Platforms Inc., ni ninguna de sus subsidiarias o empresas relacionadas. El nombre "WhatsApp" es una marca registrada de sus respectivos dueños.
- **Uso Responsable:** El uso de herramientas de automatización de terceros puede infringir los Términos de Servicio de la aplicación oficial. El desarrollador de este ecosistema **no se hace responsable** del mal uso que se le dé a este software, incluyendo suspensiones de cuentas, bloqueos de números de teléfono, pérdida de datos o sanciones aplicadas por la plataforma.
- **Riesgo del Usuario:** La configuración, despliegue y ejecución de este bot corren bajo la absoluta responsabilidad y riesgo del usuario final.
