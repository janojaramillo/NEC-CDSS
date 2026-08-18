# NEC-CDSS v3.0 Pluralista — Instalación

## Qué es

Sistema de Soporte a la Decisión Clínica para Enterocolitis Necrotizante.
Motor de 7 reglas + 6 módulos anti-convergencia + Manitoba Gut Injury Score.
Funciona **offline** como app de pantalla completa en iPhone, Android y desktop.

**Autor:** Dr. Jano Jaramillo — CSS Panamá, UCIN Nivel III

---

## Archivos necesarios (6)

| Archivo | Descripción |
|---|---|
| `index.html` | Aplicación principal del CDSS |
| `manifest.json` | Manifiesto PWA (nombre, iconos, tema) |
| `sw.js` | Service Worker (caché offline) |
| `icon-180.png` | Ícono Apple Touch (iPhone) |
| `icon-192.png` | Ícono Android |
| `icon-512.png` | Ícono splash / alta resolución |

---

## Opción A: GitHub Pages (recomendado)

### 1. Crear repositorio

- Ir a [github.com](https://github.com) → **New repository**
- Nombre: `nec-cdss` (o el que prefiera)
- **Public** (obligatorio con cuenta gratuita)
- Click **Create repository**

### 2. Subir archivos

- Click **"uploading an existing file"**
- Arrastre los **6 archivos** juntos
- Click **Commit changes**

### 3. Activar GitHub Pages

- Ir a **Settings** → **Pages**
- Source: **Deploy from a branch**
- Branch: `main` → carpeta `/ (root)`
- Click **Save**
- En ~1 minuto estará disponible en:
  `https://SU-USUARIO.github.io/nec-cdss/`

### 4. Instalar en iPhone

- Abrir la URL en **Safari**
- Tocar el botón **Compartir** (⬆)
- Seleccionar **"Agregar a pantalla de inicio"**
- La app se abre en pantalla completa, sin barra de Safari
- **Funciona offline** después de la primera carga

### 5. Instalar en Android

- Abrir la URL en **Chrome**
- Aparecerá un banner "Instalar NEC-CDSS"
- O: menú ⋮ → **"Instalar app"** / **"Añadir a pantalla de inicio"**

---

## Opción B: Uso local directo

Abrir `index.html` directamente en cualquier navegador.
Funciona sin servidor. No requiere internet después de la primera carga.

---

## Actualización

Para actualizar la app después de cambios:

1. Editar `index.html` con la nueva versión
2. En `sw.js`, cambiar `CACHE_NAME` (ej: de `v1` a `v2`)
3. Subir los archivos actualizados a GitHub
4. La app se actualizará automáticamente en la siguiente visita

---

## Notas técnicas

- **PWA (Progressive Web App):** Se instala como app nativa sin App Store
- **Offline-first:** El Service Worker cachea todos los assets en la primera visita
- **Sin dependencias externas:** Todo el motor corre en el navegador
- **Sin API keys ni servidores:** Cero datos enviados a terceros
- **Compatible:** iOS 14+, Android 8+, Chrome, Safari, Firefox, Edge
