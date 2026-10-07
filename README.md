# Editor de piezas Adrimar

Editor para armar las piezas de Instagram de Adrimar (posts, historias, foto de perfil y destacadas) y descargarlas como PNG. Funciona en el navegador, sin servidor ni instalación.

## Qué tiene la carpeta

```
adrimar-editor/
├── index.html    ← toda la aplicación (fuentes, fotos, logos y mascotas van adentro)
├── .nojekyll     ← le dice a GitHub Pages que sirva el archivo tal cual
├── .gitignore
└── README.md
```

`index.html` es autosuficiente: no carga nada de internet ni de otras carpetas. Las 8 fuentes (Outfit, DM Sans, Caveat), las 3 fotos de producto, los logos, el isotipo y las mascotas están embebidos en el propio archivo. Por eso **no hace falta subir las carpetas `Fotos`, `Iconos` ni `Instagram`** de las propuestas.

## Publicarlo en GitHub Pages

1. Crear un repositorio nuevo en GitHub (por ejemplo `adrimar-editor`).
   Con una cuenta gratuita, el repositorio tiene que ser **público** para usar Pages.
2. Subir el contenido de esta carpeta:

   ```bash
   cd adrimar-editor
   git init
   git add .
   git commit -m "Editor de piezas Adrimar"
   git branch -M main
   git remote add origin https://github.com/<usuario>/adrimar-editor.git
   git push -u origin main
   ```

   (También se puede arrastrar los archivos desde la web: *Add file → Upload files*.)
3. En el repositorio: **Settings → Pages → Build and deployment**.
   - Source: **Deploy from a branch**
   - Branch: **main**, carpeta **/ (root)** → *Save*
4. Esperar uno o dos minutos. El editor queda en:

   ```
   https://<usuario>.github.io/adrimar-editor/
   ```

## Actualizarlo

Reemplazar `index.html` por la versión nueva, y después:

```bash
git add index.html
git commit -m "Actualiza el editor"
git push
```

## Notas

- Lo que se edita se guarda en el navegador de cada persona (`localStorage`), no en GitHub. Cada dispositivo tiene su propio borrador.
- Las fotos que se suben con "Subir foto" no salen del dispositivo.
- Si el repositorio es público, el logo y las fotos de producto embebidos también quedan públicos.
