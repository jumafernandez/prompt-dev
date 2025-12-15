# 🧠 Instalación de BabyAGI clásico (macOS)

Este instructivo explica cómo instalar y ejecutar **BabyAGI clásico (versión 2023)** en macOS.  
Esta versión se utiliza con fines **educativos**, ya que permite observar claramente el funcionamiento de un agente basado en planificación de tareas.

> ⚠️ Importante  
> BabyAGI clásico está **archivado** y **no se usa en producción**.  
> En este curso lo utilizamos **para comprender conceptos**, no como herramienta final.

---

## ✅ Requisitos

Antes de comenzar, asegurate de tener:

- **macOS**
- **Python 3.10 o 3.11** (recomendado: 3.11)
- **Git**
- Una **API Key de OpenAI**

> ❌ No usar Python 3.12  
> ❌ No modificar el Python del sistema

---

## 1️⃣ Verificar versión de Python

En la terminal:

```bash
python3.11 --version
```

Salida esperada:
```text
Python 3.11.x
```

Si no tenés Python 3.11, podés instalarlo con Homebrew:

```bash
brew install python@3.11
```

---

## 2️⃣ Crear carpeta de trabajo

```bash
mkdir babyagi-classic
cd babyagi-classic
```

---

## 3️⃣ Clonar el repositorio de BabyAGI clásico

```bash
git clone https://github.com/yoheinakajima/babyagi_archive.git
cd babyagi_archive
```

Verificá que el repositorio tenga, entre otros, estos archivos:

```text
babyagi.py
requirements.txt
README.md
```

---

## 4️⃣ Crear y activar un entorno virtual

```bash
python3.11 -m venv venv
source venv/bin/activate
```

Verificación:

```bash
python --version
```

Debe mostrar:
```text
Python 3.11.x
```

---

## 5️⃣ Instalar dependencias

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 6️⃣ Instalar versión compatible del SDK de OpenAI

BabyAGI clásico **no funciona** con versiones nuevas del SDK.

```bash
pip uninstall openai -y
pip install openai==0.28.1
```

Verificación:

```bash
pip show openai
```

Debe decir:
```text
Version: 0.28.1
```

---

## 7️⃣ Crear archivo de configuración `.env`

En este repositorio **no existe** un archivo `.env.example`.  
El archivo `.env` debe crearse **manualmente**.

```bash
nano .env
```

Contenido mínimo recomendado:

```env
OPENAI_API_KEY=TU_API_KEY_AQUI
OPENAI_API_MODEL=gpt-3.5-turbo

OBJECTIVE=Analizar noticias recientes sobre inteligencia artificial y generar un breve resumen
INITIAL_TASK=Buscar noticias recientes sobre inteligencia artificial
RESULTS_STORE_NAME=results
```

⚠️ Reglas importantes:
- No usar comillas
- No dejar espacios alrededor del `=`
- Una variable por línea

Guardar y salir:
- `CTRL + O` → Enter
- `CTRL + X`

---

## 8️⃣ Ejecutar BabyAGI clásico

```bash
python babyagi.py
```

---

## ⛔ Cómo detener la ejecución

BabyAGI corre en un loop continuo.  
Para detenerlo:

```text
CTRL + C
```

---

## 🧠 Notas importantes

- BabyAGI **requiere una tarea inicial (`INITIAL_TASK`)** para comenzar.
- El agente **no infiere la primera acción por sí solo**.
- Esta es una **limitación intencional** del diseño original.
- El objetivo del ejercicio es **entender el concepto de agente**, no automatizar tareas reales.

---

## 🎓 Uso en el curso

En clase utilizaremos BabyAGI para observar:

- cómo un objetivo se descompone en tareas
- cómo se priorizan tareas
- cómo emerge un comportamiento iterativo
- cuáles son las limitaciones de estos enfoques tempranos

---

## 🧾 Conclusión

BabyAGI clásico es una herramienta **conceptual** que permite comprender el salto desde prompts aislados hacia sistemas agentic basados en planificación.

No representa el estado del arte actual, pero **sí explica su origen**.
