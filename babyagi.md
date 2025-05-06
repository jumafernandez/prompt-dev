# 🤖 BabyAGI: Tutorial de puesta en funcionamiento

Este repositorio contiene una versión funcional del agente autónomo **BabyAGI** (archivado por su autor original). Se utiliza para demostrar cómo un agente basado en LLM puede razonar, generar tareas y simular ejecución de forma autónoma.

---

## 🧠 ¿Qué hace este agente?

- Parte de un **objetivo** definido por el usuario
- Ejecuta tareas mediante un modelo de lenguaje (GPT)
- Genera nuevas tareas en base a los resultados
- Reprioriza y repite el proceso automáticamente

> ⚠️ **Nota**: este agente *no ejecuta tareas reales* (como código o consultas), sino que *simula* la ejecución generando resultados textuales con ayuda de un modelo LLM.

---

## 🚀 Instalación paso a paso

### 1. 📦 Instalar Python 3.11

Descargar desde:  
🔗 https://www.python.org/downloads/release/python-3110/

✅ Durante la instalación, asegurate de:
- Marcar **"Add Python to PATH"**
- Seleccionar instalación para todos los usuarios (si está disponible)

---

### 2. 🧪 Crear y activar entorno virtual

Abrí una terminal y posicionate en el directorio del proyecto:

```bash
cd ruta/al/proyecto/babyagi_archive
```

Creá el entorno con Python 3.11:
```bash
py -3.11 -m venv babyagi_env
```

Activá el entorno virtual:

```bash
.\babyagi_env\Scripts\activate
```

### 3. 📥 Instalar dependencias

Con el entorno activado, ejecutá:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4. ⚙️ Configurar variables de entorno

Copiá el archivo de ejemplo .env:

```bash
copy .env.example .env
```

Editá el archivo `.env` y colocá tu clave de OpenAI:

```env
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Definí un objetivo, por ejemplo:

```env
OBJECTIVE=Generar una función en Python que calcule la sucesión de Fibonacci
INITIAL_TASK=Escribir la función en Python
```


###  5. 🏁 Ejecutar el agente
Con el entorno activado, corré el script principal:

```bash
python babyagi.py
```


