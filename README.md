# GuardIA · Panel web

Panel de monitoreo y administración en React, TypeScript y Vite. Los diagramas están en `architecture/` y los prototipos en `mockups/` y `mockups_realistic/`.

## Instalación y ejecución

Instala Node.js 22 y npm. Copia `.env.example` a `.env` y completa `VITE_FIREBASE_*` con la configuración del cliente web de tu proyecto Firebase. Define `VITE_API_BASE_URL` con la URL de la API de la rama [backend](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/backend). El valor local habitual es `http://localhost:4000`.

```bash
npm ci
npm run dev
```

Abre la URL que muestra Vite. Para compilar y revisar el paquete estático:

```bash
npm run build
npm run preview
```

Publica el contenido de `dist/` en un servidor estático con fallback a `index.html` para las rutas de la SPA. Los valores `VITE_*` quedan incorporados en el navegador durante la compilación. En GitHub Actions se pueden configurar como variables del repositorio con los mismos nombres.

La detección y clasificación de riesgo se encuentran en la rama [ia](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/ia).
