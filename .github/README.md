# GitHub Workflows para Vibra Wiki

## Despliegue a GitHub Pages

Este repositorio utiliza GitHub Actions para automatizar el despliegue del sitio Docusaurus a GitHub Pages.

### Flujo de trabajo de despliegue

El archivo `.github/workflows/deploy.yml` define un flujo de trabajo que se activa automáticamente cuando se realiza un push a la rama `main`. Este flujo de trabajo:

1. Configura un entorno Node.js
2. Instala las dependencias del proyecto
3. Construye el sitio Docusaurus
4. Despliega los archivos generados a la rama `gh-pages`

### Configuración necesaria en GitHub

Para que el despliegue funcione correctamente, debes configurar lo siguiente en tu repositorio de GitHub:

1. Ve a la configuración del repositorio: `Settings > Actions > General`
2. En la sección "Workflow permissions", selecciona "Read and write permissions" y guarda los cambios
3. Ve a la configuración de Pages: `Settings > Pages`
4. En "Source", selecciona "Deploy from a branch"
5. En "Branch", selecciona `gh-pages` y la carpeta raíz (`/`), luego guarda los cambios

### Despliegue manual

Si prefieres realizar un despliegue manual, puedes usar el siguiente comando:

```bash
GIT_USER=<tu-usuario-github> USE_SSH=true npm run deploy
```

Reemplaza `<tu-usuario-github>` con tu nombre de usuario de GitHub.

### Solución de problemas

Si encuentras problemas con el despliegue:

1. Verifica los logs de GitHub Actions en la pestaña "Actions" del repositorio
2. Asegúrate de que las configuraciones en `docusaurus.config.ts` sean correctas (url, baseUrl, organizationName, projectName)
3. Confirma que los permisos de GitHub Actions estén configurados correctamente