# Script de Instalación y Ejecución Automática del Servidor HTTP para Balanzas

Este script automatiza la instalación, clonación, configuración e inicialización de un servidor HTTP escrito en Python para el proyecto **ProyectoSyncBalanzasServer**.

## ⚙️ ¿Qué hace este script?

1. Actualiza los paquetes del sistema.
2. Instala `git`, `nginx`, `python3` y `pip3`.
3. Clona el repositorio desde la rama `server`.
4. Instala las dependencias desde `requirements.txt`.
5. Ejecuta el programa `serverHttp.py` en segundo plano.
6. Añade una tarea al `crontab` para que se ejecute automáticamente al reiniciar el sistema.

## 🧾 Requisitos

- Sistema operativo basado en Debian/Ubuntu
- Acceso a internet
- Permisos de superusuario (`sudo`)

## 📁 Variables importantes

- **REPO_URL:** URL del repositorio remoto.
- **CLONE_DIR:** Ruta donde se clona el repositorio.
- **PROGRAM_NAME:** Nombre del archivo principal del servidor.
- **SETUP_FILENAME:** Archivo con las dependencias de Python.
- **PROGRAM_DIR:** Carpeta raíz del proyecto clonado.

## ▶️ Uso

1. Asegúrate de que el script tiene permisos de ejecución:

```bash
chmod +x nombre_script.sh
```

2. Ejecuta el script:

```bash
./nombre_script.sh
```

## 🔁 Ejecución automática al reinicio

El script agrega automáticamente al `crontab` la instrucción para iniciar el servidor al reiniciar el sistema:

```bash
@reboot cd /ruta/al/directorio && nohup python3 serverHttp.py &
```

## 🧯 Notas

- El script eliminará cualquier carpeta existente con el mismo nombre del proyecto si ya existe.
- Asegúrate de que no haya conflictos de nombres o procesos previos ejecutándose antes de ejecutar este script.

---

© Marsol Ingeniería – Automatización de despliegue para servidor HTTP de sincronización
