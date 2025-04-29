# 🧠 Guía de instalación y ejecución de Auto-GPT (Classic) en Windows

Esta guía explica cómo instalar y ejecutar **Auto-GPT (versión Classic)** utilizando `Poetry` y `Python 3.11` en un entorno local de Windows.

---

## ✅ Requisitos previos

1. **Python 3.11** instalado 👉 https://www.python.org/downloads/release/python-3110/
2. **Git** instalado 👉 https://git-scm.com/downloads
3. **Poetry** instalado 👉 https://python-poetry.org/docs/#installation
4. Tener una **API Key de OpenAI** activa 👉 https://platform.openai.com/account/api-keys
5. Docker instalado (opcional, pero recomendado si se desea ejecución de comandos)

---

## 📦 1. Clonar el repositorio de Auto-GPT

Abrí una terminal y ejecutá:

```bash
git clone https://github.com/Significant-Gravitas/Auto-GPT.git
cd Auto-GPT
```

## 📁 2. Ingresar a la versión classic
```bash
cd classic/original_autogpt
```

##📦 3. Instalar dependencias con Poetry

```bash
poetry install
```

⚠️ Si ves un error por dependencias, asegurate de estar usando Python 3.11 y no tener conflictos de entorno.

## 🔑 4. Configurar la API key de OpenAI

Duplicá el archivo .env.template y renombralo como .env. Luego editá el archivo .env y completá esta línea:

```bash
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## 🛠️ 5. Ejecutar Auto-GPT
Desde la carpeta classic/original_autogpt, ejecutá:

```bash
poetry run autogpt
```

Esto va a levantar Auto-GPT y te preguntará si querés habilitar telemetría (podés escribir no).

## 🧪 6. Probar una tarea simple

Cuando aparezca el prompt:

```bash
Enter the task that you want AutoGPT to execute...
```

Podés escribir, por ejemplo:
```bash
Me podés decir los primeros tres números primos? Respondé en español.
```

### 📌 Notas adicionales
- Si usás modelos como gpt-4-turbo, asegurate de tener acceso en tu cuenta de OpenAI.
- Si aparece algún error como No module named autogpt, asegurate de haber ejecutado desde la carpeta correcta (classic/original_autogpt) y haber hecho poetry install en classic/.
