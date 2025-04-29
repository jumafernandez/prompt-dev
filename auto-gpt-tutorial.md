# 🧠 Guía de instalación y ejecución de Auto-GPT (Classic)

Esta guía explica cómo instalar y ejecutar **Auto-GPT (versión Classic)** utilizando `Poetry` y `Python 3.11` en un entorno local.

---

## ✅ Requisitos previos

1. **Python 3.11** instalado 👉 https://www.python.org/downloads/release/python-3110/
2. **Git** instalado 👉 https://git-scm.com/downloads
3. **Poetry** instalado 👉 https://python-poetry.org/docs/#installation
4. Tener una **API Key de OpenAI** activa 👉 https://platform.openai.com/account/api-keys
5. Docker instalado (opcional, pero recomendado si se desea ejecución de comandos)

---

### 🐍 Instalación de Python 3.11 y manejo de múltiples versiones

Auto-GPT requiere Python versión ≥3.10 y <3.12, por lo tanto, si ya tenés otra versión instalada (como 3.12), podés convivir con ambas versiones sin conflictos.

#### 1. Verificar la versión instalada

```bash
python --version
```
Si tenés una versión 3.12 o superior, necesitás instalar la versión 3.11 específicamente.

#### 2. Descargar Python 3.11

- Ir a https://www.python.org/downloads/release/python-3110/
- Descargar el instalador para tu sistema operativo

✅ Asegurate de tildar la opción "Add Python 3.11 to PATH" durante la instalación

⚠️ Si ya tenías otra versión instalada, el instalador de Python te permite tener ambas versiones sin reemplazar la anterior.

#### 3. Crear un entorno virtual con Python 3.11

Una vez instalado Python 3.11, podés crear un entorno virtual para Auto-GPT desde la terminal:

```bash
C:\> py -3.11 -m venv autogpt-env
```

Esto crea un entorno virtual llamado autogpt-env.

#### 4. Activar el entorno virtual

Según el sistema operativo, activá el entorno virtual:

Windows (PowerShell):
```bash
.\autogpt-env\Scripts\Activate.ps1
```

Windows (CMD):
```cmd
.\autogpt-env\Scripts\activate.bat
```

Linux/MacOS:
```bash
source autogpt-env/bin/activate
```

#### 5. Verificar que estás en el entorno correcto

Linux/MacOS:
```bash
python --version
```

Debería devolver algo como Python 3.11.x. Si es así, ¡ya estás listo para instalar dependencias y correr Auto-GPT!

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

## 📦 3. Instalar dependencias con Poetry

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
