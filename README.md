# Asistente de Captura de Leads por Voz y Texto

Este proyecto es un asistente conversacional en español que permite recopilar información de leads (potenciales clientes) mediante voz o texto, almacenando los datos en un archivo CSV y enviándolos a un CRM externo. Además, guarda preferencias de usuario para personalizar futuras interacciones.

## Características principales
- Interacción por voz (usando reconocimiento y síntesis de voz) o texto.
- Extracción automática de nombre, empresa, presupuesto e intención usando procesamiento de lenguaje natural (NLP).
- Almacenamiento de leads en un archivo CSV (`leads.csv`).
- Envío de leads a un CRM externo vía API REST.
- Gestión de preferencias e historial de usuarios en `usuarios.json`.

## Estructura de archivos
- `main.py`: Script principal. Gestiona el flujo de conversación, entrada/salida, preferencias y almacenamiento.
- `voice_rec.py`: Funciones para reconocimiento de voz (speech-to-text).
- `dialog_manager.py`: Lógica de slots y gestión del perfil del usuario durante la conversación.
- `text.py`: Extracción de entidades (nombre, empresa, presupuesto, intención) usando modelos de NLP.
- `guardar_datos.py`: Guarda los perfiles de usuario en un archivo CSV.
- `crm_api.py`: Funciones para enviar y buscar leads en un CRM externo vía API REST.
- `preferencias.py`: Carga y guarda preferencias de usuario en `usuarios.json`.
- `leads.csv`: Archivo donde se almacenan los leads capturados.
- `usuarios.json`: Preferencias e historial de usuarios.

## Requisitos
- Python 3.8+
- Paquetes:
  - `speechrecognition`
  - `pyttsx3`
  - `transformers`
  - `requests`

Puedes instalar los requisitos con:
```bash
pip install speechrecognition pyttsx3 transformers requests
```

## Uso
1. Ejecuta el script principal:
   ```bash
   python main.py
   ```
2. Elige el modo de interacción (voz o texto).
3. Responde a las preguntas del asistente para completar tu perfil.
4. Los datos se guardarán automáticamente y se enviarán al CRM.

## Notas
- Para el reconocimiento de voz se requiere un micrófono y conexión a internet (usa Google Speech API).
- Configura la URL y el token de tu CRM en `crm_api.py`.
- El modelo de NLP usado es `mrm8488/bert-spanish-cased-finetuned-ner` (descargado automáticamente por `transformers`).

## Autor
- Desarrollado por Abner (2025)
