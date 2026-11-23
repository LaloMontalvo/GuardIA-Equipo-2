# GuardIA � Equipo 2

Sistema de videovigilancia con panel web, API de gesti�n, servicios de inteligencia artificial y aplicaci�n m�vil Android.

| Rama | Contenido |
| --- | --- |
| [panel-web](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/panel-web) | Panel de monitoreo en React, TypeScript y Vite, documentaci�n de arquitectura y prototipos. |
| [backend](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/backend) | API Express, base de datos PostgreSQL, Cloud Functions y reglas de Firestore. |
| [ia](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/ia) | Detecci�n de personas con YOLOv8 y clasificaci�n de riesgo con los modelos entrenados. |
| [movil](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/movil) | Aplicaci�n Flutter, recursos y c�digo por plataforma. |

Cada rama incluye su gu�a de instalaci�n. Para probar el sistema integrado, configura un proyecto Firebase de revisi�n, inicia PostgreSQL y la API, y levanta los servicios de IA que vayas a usar. Configura despu�s el panel y la app con las URL de ese entorno.

## Compilaciones

El flujo [Paquetes de revisi�n](https://github.com/LaloMontalvo/GuardIA-Equipo-2/actions/workflows/paquetes.yml) genera el APK Android de depuraci�n, el sitio est�tico del panel y un ZIP con el contexto Docker del servicio de detecci�n. El APK se instala en un dispositivo Android compatible. Para que el panel compilado funcione con Firebase, provee las variables p�blicas de cliente descritas en la rama `panel-web`. La app usa la configuraci�n Firebase de cliente incluida en su c�digo.

## Historial de origen

Los ZIP de la entrega corresponden a estos commits de los repositorios originales:

- Panel, backend e IA � [rodolfo-estrada/GuardIA en e2a973e](https://github.com/rodolfo-estrada/GuardIA/commit/e2a973e994aa9ac4d3fb910f98c951f05d2f164f).
- App m�vil � [LaloMontalvo/GuardIA-Movil en dc0a42b](https://github.com/LaloMontalvo/GuardIA-Movil/commit/dc0a42be34ae6f1ed7325c214f540e91399aa542).

Los enlaces de origen permiten consultar los commits anteriores a la importaci�n. Este repositorio registra la importaci�n y los cambios de la entrega por componente.

## Revisi�n t�cnica

El asesor puede consultar las ramas p�blicas en GitHub. Si requiere probar funciones autenticadas, asigna una cuenta de revisi�n con el rol correspondiente en el entorno de prueba. Mant�n las credenciales de servidor y los archivos `.env` en la configuraci�n local o en el servicio de despliegue.
