# 🤖 n8n Workflows & AI Agent "Paco" 

Bienvenido al repositorio de automatizaciones y copias de seguridad de mi servidor **n8n self-hosted**. 

Este repositorio actúa como el cerebro central y la bóveda de seguridad de **Paco**, mi asistente personal basado en Inteligencia Artificial (DeepSeek), diseñado para actuar como un "Segundo Cerebro" y optimizar la gestión diaria de información, agenda y tareas.

---

## 🧠 Sobre "Paco" (El Agente IA)
Paco es un asistente conversacional y ejecutivo construido sobre el motor de [n8n](https://n8n.io/) usando LangChain y modelos de DeepSeek. Está alojado en un VPS privado y es capaz de tomar decisiones, usar herramientas y aprender sobre la marcha gracias a su memoria a largo plazo conectada a una base de datos PostgreSQL.

### 🛠️ Capacidades y Herramientas Integradas:
- 💬 **Telegram (Interfaz Principal):** Comunicación fluida, envío de documentos y respuesta por texto enriquecido.
- 🎙️ **Siri / Voz (Webhooks):** Respuestas ultra-cortas optimizadas para ser leídas en voz alta a través de atajos de iOS.
- 🏃 **Strava:** Monitorización automática de entrenamientos (tiempo, distancia, tipo de deporte) y registro de hitos de rendimiento físico.
- 📅 **Google Calendar & Tasks:** Gestión completa de agenda (crear, leer y modificar eventos/tareas).
- 📧 **Gmail:** Lectura, filtrado y búsqueda inteligente de correos electrónicos.
- 💾 **Memoria a Largo Plazo (PostgreSQL):** Base de datos relacional (`memoria_paco`) donde el agente guarda y consulta proactivamente datos personales, gustos e información clave.
- 🔍 **SerpAPI:** Acceso a internet en tiempo real para búsquedas de Google y scraping de URLs.

---

## 📂 Estructura del Repositorio

Los archivos de este repositorio son exportaciones nativas de n8n en formato `.json`. Se suben aquí de forma totalmente automática mediante un **flujo de Auto-Backup** programado en el propio n8n, llamado github.

* *El nombre de cada archivo se genera automáticamente limpiando el nombre original del workflow en n8n.*

---

## 🔄 El Sistema de Backup Automático (github.json)
La actualización de este repositorio no requiere intervención manual. Un flujo específico dentro de n8n se encarga de:
1. Dispararse según un cronograma (`Schedule Trigger`).
2. Consultar la API interna de n8n (`/api/v1/workflows`) para obtener la lista de todos los flujos activos.
3. Convertir el contenido a formato Base64.
4. Conectarse a la API de GitHub para subir/actualizar los archivos (`.json`) en este repositorio con un mensaje de commit que incluye la fecha y hora exacta de la copia.

---

## 🚀 Cómo restaurar un Workflow
Si necesitas importar alguno de estos flujos a una instancia nueva de n8n:

1. Haz clic en el archivo `.json` que deseas restaurar dentro de GitHub.
2. Copia todo el contenido en crudo (*Raw*).
3. Ve a tu panel de n8n, crea un workflow en blanco.
4. Simplemente **pega (Ctrl+V / Cmd+V)** en el lienzo, o ve al menú de opciones arriba a la derecha > *Import from File / Import from URL*.
5. ¡Asegúrate de reconfigurar tus propias credenciales en los nodos correspondientes!

---

## ⚙️ Stack Tecnológico
* **Orquestador:** n8n (Dockerizado tras Caddy Reverse Proxy).
* **LLM:** DeepSeek (API).
* **Base de Datos:** PostgreSQL.
* **Sincronización de Archivos:** Syncthing.
* **Lenguajes:** JavaScript (expresiones de n8n), SQL, Markdown.

---
*Repositorio mantenido automáticamente por n8n. Creado por [Alejandro Rico](https://github.com/alejandroricogarcia05).*
