# CepayaBot-MD
Bot de WhatsApp Multi-Device (Baileys) de alto rendimiento, optimizado con un motor de intenciones dinámico por subcarpetas, super-limpieza de argumentos y procesamiento inteligente con IA.
<div align="center">

# ⚡ CEPLAYA-BOT MULTI-USE MINI ⚡

[![Made with Baileys](https://img.shields.io/badge/Made%20with-Baileys-00bcd4?style=for-the-badge&logo=whatsapp)](https://github.com/WhiskeySockets/Baileys)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Status: Active 24/7](https://img.shields.io/badge/Status-Active%2024%2F7-brightgreen?style=for-the-badge&logo=uptime-robot)](https://github.com/)

<img src="https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?q=80&w=600" alt="Cepaya-Bot Mini" width="320" style="border-radius: 20px; border: 3px solid #a855f7; box-shadow: 0px 4px 20px rgba(168, 85, 247, 0.4);">

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
