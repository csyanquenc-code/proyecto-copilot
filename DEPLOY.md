# Despliegue en GitHub Pages

Instrucciones rápidas para publicar este blog en GitHub Pages usando PowerShell (Windows):

1. Crear un nuevo repositorio en GitHub (por ejemplo `proyecto-copilot`).
2. En tu máquina, desde la carpeta del proyecto ejecutar:

```powershell
# inicializar repo local (si aún no existe)
git init;
git add .;
git commit -m "Inicial: blog técnico - Christopher Yanquen";
# crea el repositorio remoto en GitHub y añade el remote. Reemplaza URL por tu repo.
# git remote add origin https://github.com/USUARIO/proyecto-copilot.git;
# Empujar a la rama main
# git push -u origin main
```

3. Opción recomendada para GitHub Pages (usar la rama `gh-pages`):

```powershell
# Crear rama gh-pages desde main
git checkout -b gh-pages;
# Si quieres publicar en la raíz, empuja gh-pages
git push -u origin gh-pages;
```

4. Alternativa: Publicar desde la rama `main` en la carpeta `/` o `/docs` usando la configuración de GitHub:
- En el repositorio en GitHub -> Settings -> Pages -> Source -> elegir `main` branch y `/ (root)` o `/docs`.

5. Verifica la URL de GitHub Pages en la sección Pages del repositorio. La publicación puede tardar unos minutos.

Notas y recomendaciones:
- Para automatizar despliegues puedes usar GitHub Actions que construyan y publiquen en `gh-pages`.
- Si no tienes el remote, crea el repo en GitHub y luego:

```powershell
git remote add origin https://github.com/USUARIO/proyecto-copilot.git;
git push -u origin main;
```

- Reemplaza `USUARIO` y `proyecto-copilot` por los tuyos.

Si quieres, puedo generar un flujo de GitHub Actions para desplegar automáticamente a `gh-pages` cuando hagas push a `main`.