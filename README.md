# 🤖 Agente Conversacional para WhatsApp con n8n

Este repositorio contiene dos flujos avanzados de automatización con **n8n** que implementan **agentes conversacionales inteligentes conectados a WhatsApp**. Ambos proyectos se construyeron como soluciones de **mensajería enriquecida** capaces de interpretar texto, audio e imágenes, registrar datos del usuario y ofrecer respuestas personalizadas mediante inteligencia artificial.

---

## 🔁 Flujo 1: Agente Conversacional Base

Este es el flujo principal que sirvió como base para todo el sistema. Integra múltiples herramientas para permitir al bot realizar tareas complejas como:

### ✨ Funcionalidades

- 📩 **WhatsApp**: Recibe y responde mensajes a través de la API de **Evolution** o servicios compatibles.  
- 🧠 **OpenAI**: Interpreta consultas en lenguaje natural, tanto en texto como en voz e imágenes.  
- 🧠 **Think Tool (OpenAI)**: Para tareas complejas que requieren razonamiento paso a paso.  
- 🔊 **Transcripción de audio**: Detecta mensajes de voz y los convierte a texto automáticamente.  
- 🖼️ **Análisis de imágenes**: Recibe imágenes por WhatsApp y devuelve una descripción inteligente.  
- 🗂️ **Clasificación de texto (Text Classifier)**: Detecta el tipo de consulta del usuario (técnica, académica, personal o de entretenimiento).  
- 🧾 **Registro en Google Sheets**: Guarda automáticamente información de los usuarios que interactúan con el bot.  
- 💬 **Redis**: Utilizado como sistema de cola de mensajes para manejar conversaciones en partes o fragmentadas.  
- 📊 **Supabase**: Todos los datos procesados (timestamp, tipo de mensaje, categoría, etc.) se almacenan en una base de datos PostgreSQL para análisis posterior.  
- 🌐 **SerpAPI**: Permite realizar búsquedas web (por ejemplo, si el usuario solicita información en tiempo real).  

---

## 🥗 Flujo 2: Asistente de Salud y Nutrición

Este segundo flujo es una especialización del primero. Utiliza la misma estructura técnica, pero con un prompt altamente afinado para ofrecer respuestas orientadas al área de **salud, nutrición y bienestar**.  

Está diseñado para responder consultas relacionadas con **anemia**, **dietas saludables**, **estilos de vida**, **micronutrientes**, etc., siempre con un enfoque **educativo y accesible para usuarios rurales o de zonas con conectividad limitada**.

---

## 🔐 Requisitos y credenciales

Para que estos flujos funcionen correctamente, se requiere la creación y configuración de cuentas en varios servicios:

- Una cuenta en **n8n**, ya sea instalada localmente o en una VPS.  
- Acceso a una API de WhatsApp como **Evolution API**, junto con su token de autenticación.  
- Una cuenta de **OpenAI**, con una clave de API activa para permitir generación de texto, transcripción de audio y análisis de imágenes.  
- Una instancia funcional de **Redis**, ya sea en el mismo servidor o como servicio externo, para manejar la cola de mensajes por usuario.  
- Acceso a **Google Cloud** para habilitar la API de **Google Sheets** y registrar las interacciones del bot con los usuarios.  
- Una cuenta en **Supabase**, donde se configurará una tabla para almacenar datos como fechas, tipo de mensajes, categorías clasificadas, entre otros.  
- Una cuenta en **SerpAPI**, necesaria para realizar búsquedas web automatizadas desde el flujo.  

> No se requiere instalar **Luxon**, ya que está integrado en los nodos de expresiones de n8n.

Cada servicio requiere su propia configuración y autenticación (**API Keys**, **URLs**, **Tokens**, etc.), por lo que se recomienda revisar la documentación oficial de cada uno antes de ejecutar el flujo.

---

## ⚙️ Recomendaciones para la implementación

- Instala **n8n** en una **VPS** o tu entorno local.  
- Carga el archivo **.json** del flujo desde el editor de flujos.  
- Configura las **credenciales necesarias** en la sección de "Credenciales" de n8n.  
- Asegúrate de tener acceso a todas las **APIs y servicios mencionados**.  
- Para Redis, puedes usar una instancia en la nube o local.  
- Ajusta los **prompts y condiciones** según tu caso de uso.
