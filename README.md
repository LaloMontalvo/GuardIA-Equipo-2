# GuardIA · Backend

API Express, esquema PostgreSQL, reglas de Firestore y Cloud Functions. Usa Node.js 22 para la API y el runtime de Node.js declarado en `functions/package.json` para las funciones.

## API y PostgreSQL

Desde la raíz de la rama:

```bash
docker compose up -d postgres
cd api
npm ci
```

Copia `api/.env.example` a `api/.env` antes de iniciar la API. Configura la conexión a PostgreSQL en el puerto local 5433 y Firebase Admin para el entorno de revisión. El contenedor aplica `db/init.sql` al inicializar una base vacía.

Desde `api/` ejecuta:

```bash
npm start
```

Comprueba `GET http://localhost:4000/health`. Consulta [Configuración de PostgreSQL y API](docs/postgres-api-setup.md) y [Autenticación móvil](docs/mobile-api-auth.md) para los detalles de integración.

Cuando ejecutes la rama [ia](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/ia) en la misma máquina, la API buscará detección en el puerto 8000 y clasificación de riesgo en el 8001. Si se ejecutan en otro host, define `IA_GUARDIA_URL` y `ML_SERVICE_URL` en `api/.env`.

## Firebase

Instala las dependencias con `npm ci` dentro de `functions/`. Consulta la [guía de OTP](docs/email-otp-setup.md) para configurar el correo y selecciona tu proyecto de revisión en Firebase CLI antes de ejecutar emuladores o desplegar. Las reglas se encuentran en `firestore.rules` y las funciones se registran en `firebase.json`.
