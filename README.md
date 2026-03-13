# 🌊 Museo Marino AR

Experiencia de Realidad Aumentada en el navegador para un museo de fauna marina.
Funciona en celular Android y computadora sin instalar ninguna app.

## 📁 Estructura del proyecto

```
museo-marino/
├── index.html        ← Página principal del museo
├── ar.html           ← Experiencia AR con cámara
├── markers.html      ← Marcadores para imprimir
├── generator.html    ← Herramienta generadora de código AR
├── models/           ← Pon aquí tus archivos .glb
│   ├── shark.glb
│   ├── octopus.glb
│   ├── turtle.glb
│   ├── clownfish.glb
│   └── crab.glb
└── README.md
```

## 🚀 Cómo subir a GitHub Pages (paso a paso)

### 1. Crear el repositorio
1. Ve a **github.com** → clic en "New repository"
2. Nombre: `museo-marino` (o el que quieras)
3. Marca **Public**
4. Clic en "Create repository"

### 2. Subir los archivos
**Opción A — Desde el navegador (más fácil):**
1. Dentro del repo, clic en "uploading an existing file"
2. Arrastra TODOS los archivos de esta carpeta
3. También arrastra la carpeta `models/` con tus .glb
4. Clic en "Commit changes"

**Opción B — Con Git (si lo tienes instalado):**
```bash
git init
git add .
git commit -m "Museo marino AR"
git remote add origin https://github.com/TU_USUARIO/museo-marino.git
git push -u origin main
```

### 3. Activar GitHub Pages
1. Ve a tu repo → **Settings** → **Pages** (menú izquierdo)
2. En "Source" selecciona **Deploy from a branch**
3. Branch: **main** → Folder: **/ (root)**
4. Clic en **Save**
5. Espera 1-2 minutos
6. Tu URL será: `https://TU_USUARIO.github.io/museo-marino/`

## 🗂️ Cómo agregar tus modelos .glb

1. Descarga tus modelos de Sketchfab en formato GLB
2. Renómbralos exactamente así:
   - `shark.glb`
   - `octopus.glb`
   - `turtle.glb`
   - `clownfish.glb`
   - `crab.glb`
3. Ponlos en la carpeta `models/`
4. En `ar.html`, descomenta las líneas que dicen `<a-asset-item ...>` y comenta o borra los placeholders

## 🖨️ Marcadores para imprimir

Abre `markers.html` y haz clic en "Imprimir todos los marcadores".

| Animal | Marcador |
|--------|----------|
| 🦈 Tiburón | HIRO |
| 🐙 Pulpo | KANJI |
| 🐢 Tortuga | Matrix 0 |
| 🐠 Pez Payaso | Matrix 1 |
| 🦀 Cangrejo | Matrix 2 |

Los marcadores HIRO y KANJI ya están cargados en `markers.html`.
Para los Matrix (0, 1, 2), descárgalos de: https://github.com/AR-js-org/AR.js

## ⚠️ Importante

- La cámara solo funciona con **HTTPS** — GitHub Pages ya lo incluye
- Para que AR funcione en celular, el visitante debe **aceptar el permiso de cámara**
- Los marcadores deben estar bien iluminados y planos
- Distancia recomendada al marcador: 20–50 cm

## 🛠️ Tecnologías usadas

- [A-Frame](https://aframe.io/) — Framework WebXR/3D
- [AR.js](https://ar-js-org.github.io/AR.js-Docs/) — Realidad aumentada en el navegador
- GitHub Pages — Hosting gratis con HTTPS

## 🔄 Cómo reemplazar los modelos placeholder

En `ar.html`, busca las secciones comentadas y sigue las instrucciones:

```html
<!-- ANTES (placeholder): -->
<a-box color="#0077cc" ...></a-box>

<!-- DESPUÉS (con tu modelo): -->
<a-entity gltf-model="#shark-model" scale="0.5 0.5 0.5" position="0 0.5 0"
  animation="property: rotation; to: 0 360 0; loop: true; dur: 6000; easing: linear">
</a-entity>
```

¡También puedes usar el `generator.html` para generar el código automáticamente! 🎉
