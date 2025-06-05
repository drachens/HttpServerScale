# Flask Image Upload & Listing API

Este proyecto es una pequeña API REST desarrollada con Flask que permite cargar imágenes a un servidor Linux y listarlas desde una carpeta específica. Es ideal para balanzas inteligentes u otros dispositivos que requieren almacenar y consultar archivos de imagen de forma remota.

## 📦 Endpoints

### 1. `POST /upload`
Permite subir una imagen al servidor.

- **Campos requeridos en el `form-data`:**
  - `file`: archivo de imagen (ej. `.jpg`, `.png`, etc.)
  - `newFileName`: nombre con el que se guardará el archivo en el servidor

- **Respuesta exitosa:**
  ```json
  200 OK
  "Archivo cargado exitosamente en /ruta/del/archivo.jpg"
  ```

- **Errores posibles:**
  - `401`: No se ha enviado un archivo
  - `402`: No se seleccionó ningún archivo

### 2. `GET /listImages`
Retorna una lista de los archivos (imágenes) almacenados en la carpeta destino.

- **Respuesta exitosa:**
  ```json
  {
    "imagenes": ["imagen1.jpg", "imagen2.png", ...]
  }
  ```

- **Errores posibles:**
  - `403`: No hay imágenes en la carpeta
  - `500`: Error interno al acceder a los archivos

## 🔐 CORS
Se habilita CORS globalmente para permitir solicitudes desde otros dominios.

## 🛠️ Configuración

- Carpeta de destino de archivos:
  ```python
  UPLOAD_FOLDER = "/usr/lib/balance-app/.dart_tool/productImages"
  ```
- Tamaño máximo del archivo: 3 MB

## ▶️ Ejecución

Para correr el servidor:

```bash
python app.py
```

La API quedará escuchando en `http://0.0.0.0:5000`.

---

© Marsol Ingeniería – Servicio de carga y gestión de imágenes en balanzas
