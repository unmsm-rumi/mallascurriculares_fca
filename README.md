# Mallas Curriculares — Rumi UNMSM

Sitio estático con las mallas curriculares interactivas de la Facultad de Ciencias Administrativas (UNMSM).

## Estructura del repo

```
rumi-mallas/
├── index.html            # Página principal (menú + carga de mallas en iframe)
├── administracion.html   # Malla de Administración
├── negocios.html         # Malla de Negocios Internacionales
├── kibu.png              # Favicon + mascota
├── Rumi.png              # Logo del header
└── README.md
```

Carreras que faltan (el `index.html` ya tiene los enlaces listos, solo falta crear el archivo):
- `turismo.html`
- `maritima.html` (o el nombre que uses — hay que agregarlo también al objeto `disponibles` en `index.html`)
- `gastronomia.html`
- `marketing.html`

Mientras no exista el archivo, el sitio muestra automáticamente el mensaje "🔧 Próximamente disponible".

## 1. Crear el repositorio en GitHub

1. Entra a https://github.com/new
2. Nombre sugerido: `rumi-mallas` (o `mallas-fca`, el que prefieras)
3. Visibilidad: **Public** (obligatorio para GitHub Pages gratis, salvo que tengas GitHub Pro)
4. NO marques "Add a README" (ya tienes uno) — déjalo vacío
5. Clic en **Create repository**

## 2. Subir los archivos (sin usar terminal, si prefieres)

**Opción A — Arrastrar y soltar (más simple):**
1. En la página del repo recién creado, clic en "uploading an existing file"
2. Arrastra los 5 archivos de esta carpeta
3. Commit message: `Primera versión del sitio`
4. Clic en **Commit changes**

**Opción B — Con Git (si ya lo usas para Ravmar/otros proyectos):**
```bash
cd rumi-mallas
git init
git add .
git commit -m "Primera versión del sitio"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/rumi-mallas.git
git push -u origin main
```

## 3. Activar GitHub Pages

1. En el repo, ve a **Settings** → **Pages** (menú izquierdo)
2. En "Build and deployment" → Source: **Deploy from a branch**
3. Branch: **main**, carpeta: **/ (root)**
4. Clic en **Save**
5. Espera 1-2 minutos. La URL te aparecerá arriba, algo como:
   `https://TU-USUARIO.github.io/rumi-mallas/`

## 4. Actualizaciones futuras

Cada vez que subas un cambio a `main` (arrastrando archivos de nuevo o con `git push`), GitHub Pages lo redeploya automáticamente en 1-2 minutos. No hay que repetir el paso 3.

## 5. Agregar una malla nueva (ej. Turismo)

1. Crea `turismo.html` con la misma estructura que `administracion.html` o `negocios.html` (mismo `<script>` con el array `cursos`, `AREAS_INFO`, etc. — cambiando los datos de la carrera)
2. En `index.html`, dentro de `renderMallaHTML()`, agrega la línea:
   ```js
   const disponibles = {
     'Administración':       'administracion.html',
     'Negocios Internacionales': 'negocios.html',
     'Turismo':              'turismo.html',   // ← ya está esta línea, solo falta el archivo
   };
   ```
   (Para Marítima, Gastronomía y Marketing, agrega líneas similares apuntando a sus archivos)
3. Sube el archivo nuevo al repo (paso 2) y listo.
