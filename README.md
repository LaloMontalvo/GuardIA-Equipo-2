# GuardIA · Aplicación móvil

Aplicación Flutter con autenticación, monitoreo de cámaras, alertas y reportes. Consulta [decisiones técnicas](DECISIONES_TECNICAS.md) y [tecnologías](TECH_STACK.md) para revisar la implementación.

## Instalación y ejecución

Instala Flutter 3.29.3, JDK 17 y el SDK de Android. Ejecuta `flutter doctor` y verifica la configuración de Android antes de conectar un dispositivo o iniciar un emulador.

```bash
flutter pub get
flutter run
```

Para usar un proyecto Firebase de revisión, configura su cliente con FlutterFire y actualiza la URL de la API en `lib/core/constants/api_constants.dart`. Revisa la configuración de cámara dentro de la app y usa una cuenta de prueba con el rol asignado en Firebase. La API y los servicios de IA están en las ramas [backend](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/backend) e [ia](https://github.com/LaloMontalvo/GuardIA-Equipo-2/tree/ia).

## Generar e instalar el APK

```bash
flutter build apk --debug
adb install -r build/app/outputs/flutter-apk/app-debug.apk
```

El APK de depuración sirve para la revisión en Android. La distribución en una tienda requiere una compilación de producción con firma propia.
