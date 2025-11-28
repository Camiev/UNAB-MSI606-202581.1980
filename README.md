# UNAB-MSI606-202581.1980

# 📌 Instalación local de Python y dependencias

Este documento explica cómo instalar Python 3.11, crear un entorno virtual y ejecutar el archivo Jupyter Notebook (`.ipynb`) con todas sus dependencias de forma local, así ayudar a evitar conflictos entre versiones de Python y dependencias.

---

## ✅ 1. Instalar Python
Descargar e instalar Python desde el sitio oficial:

https://www.python.org/downloads/

---

## ✅ 2. Crear un entorno virtual dentro del proyecto

Ubícate en la carpeta del proyecto y crear el entorno virtual:

```bash
python3.11 -m venv venv
```

Activar el entorno virtual

macOS / Linux:

```bash
source venv/bin/activate
```

Windows (PowerShell):

```bash
venv\Scripts\Activate
```

Verifica que está usando 3.11:
```bash
python --version
```

Debe decir:

```bash
Python 3.11.x
```

## ✅ 3. Instalar Jupyter y dependencias

Si el proyecto ya incluye un requirements.txt:
```bash
pip install -r requirements.txt
```

Si NO existe requirements.txt, instalar Jupyter manualmente:
```bash
pip install jupyter notebook
```

Instalar librerías necesarias según el notebook (ejemplo):

```bash
pip install numpy pandas matplotlib scikit-learn
```

(Opcional) Crear un archivo requirements.txt del entorno actual

```bash
pip freeze > requirements.txt
```

## ✅ 4. Instalar ipykernel dentro del venv

Esto permite usarlo en Cursor para los notebooks:

```bash
pip install ipykernel
```

## ✅ 5. Registrar el entorno como kernel para Jupyter / Cursor

```bash
python -m ipykernel install --user --name py311 --display-name "Python 3.11 (venv)"
```

Esto creará un kernel llamado Python 3.11 (venv) visible en Select Kernel.

## ✅ 6. Reiniciar Cursor

Cierra y vuelve a abrir Cursor
o

Ejecuta Developer: Reload Window

Ahora al abrir tu .ipynb, en Select Kernel debería aparecer:

```bash
✔ Python 3.11 (venv)
```