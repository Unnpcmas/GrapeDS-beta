<div align="center">

# GrapeDS

### Emulador de Nintendo DS y DSi para Android

Un fork independiente de **melonDS Android**, con identidad propia y mejoras en la experiencia de uso.

[![Versión](https://img.shields.io/badge/versión-2.0.8-7c3aed)](https://github.com/Unnpcmas/GrapeDS-beta)
[![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)](https://github.com/Unnpcmas/GrapeDS-beta)
[![Arquitectura](https://img.shields.io/badge/arquitectura-arm64--v8a-555)](https://github.com/Unnpcmas/GrapeDS-beta)
[![Licencia](https://img.shields.io/badge/licencia-GPLv3-blue)](https://github.com/Unnpcmas/GrapeDS-beta/blob/main/LICENSE)
[![Patreon](https://img.shields.io/badge/Apoyar_GrapeDS-Patreon-FF424D?logo=patreon&logoColor=white)](https://www.patreon.com/c/unnpcmas/membership)

**[Descargar APK](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.8-arm64-debug.apk)** · **[Código fuente ligero](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.8-source.zip)** · **[Reportar un problema](https://github.com/Unnpcmas/GrapeDS-beta/issues)**

</div>

---

## Descargas

| Archivo | Descripción |
| --- | --- |
| [GrapeDS 2.0.8 · APK](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.8-arm64-debug.apk) | APK beta para Android de 64 bits (`arm64-v8a`). |
| [GrapeDS 2.0.8 · Código fuente](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.8-source.zip) | Fuentes del proyecto y dependencias nativas incluidas, sin compilaciones, cachés ni archivos locales. |

**Versión Android:** `2.0.8 GH` · **Código de versión:** `48` · **Paquete:** `com.grapeds.android`

El APK se distribuye como compilación **debug beta**, no como una versión de producción certificada. No incluye juegos ni archivos de Nintendo.

### Instalación y actualización

1. Descarga el archivo `.apk` desde esta página.
2. Permite la instalación desde tu navegador o gestor de archivos cuando Android lo solicite.
3. Abre el APK e instala GrapeDS.
4. Selecciona la carpeta de tus juegos obtenidos legalmente.

La firma de este APK coincide con la versión 2.0.7 distribuida en este repositorio: puedes instalarlo encima sin desinstalar. Instalaciones antiguas con otro certificado no admiten actualización directa. Haz una copia de tus partidas antes de cambiar de instalación.

## Características

| Área | Funciones |
| --- | --- |
| Biblioteca | Exploración de juegos, iconos y organización de ROMs. |
| Controles | Pantalla táctil, controles en pantalla y compatibilidad con mandos. |
| Emulación | Nintendo DS y DSi, guardados y estados de partida. |
| Vídeo | Renderizado Software y OpenGL; Compute disponible en dispositivos compatibles. |
| Personalización | Distribución de pantallas, temas e idioma inglés, español o del sistema. |
| Velocidad | Avance rápido con estado reiniciado al comenzar una sesión. |

La opción **Calidad** aparece en Ajustes como reserva para una función futura; todavía no cambia el emulador.

## Novedades de 2.0.8

- OpenGL como selección inicial en dispositivos que declaran soporte para GLES 3.2, cuando no hay un renderizador guardado.
- Software como selección inicial en dispositivos sin ese soporte.
- Conservación de las preferencias de renderizador ya guardadas al actualizar.
- Mantiene los ajustes de audio, avance rápido e idioma introducidos anteriormente.

Si ya tienes **Software** guardado, la actualización no lo cambia automáticamente. Puedes seleccionar **OpenGL** en **Ajustes → Vídeo**, si tu dispositivo ofrece esa opción.

## Rendimiento y compatibilidad

El rendimiento depende del juego, del procesador, de la GPU, de sus controladores y de los ajustes. No se garantiza una velocidad concreta en todos los dispositivos.

- Empieza con resolución interna **1×** cuando utilices renderizado acelerado.
- Mantén el avance rápido apagado para jugar a velocidad normal.
- JIT y renderizado por hilos pueden mejorar el rendimiento, pero su compatibilidad depende del juego y del dispositivo.
- Si OpenGL presenta errores gráficos, vuelve a Software.

**Estado de verificación:** compilación y tests unitarios completados; firma del APK verificada. La mejora de velocidad y audio de Super Mario 64 DS todavía requiere comprobación en hardware real. Que un juego 3D funcione bien no garantiza que todos tengan el mismo rendimiento.

### Limitaciones

- Esta descarga solo incluye la arquitectura `arm64-v8a`.
- El multijugador local y el soporte de tarjeta SD de DSi siguen siendo funciones pendientes de esta distribución.
- DSi/DSiWare y el uso de firmware externo pueden requerir archivos propios válidos.

## Integración con otros frontends

GrapeDS utiliza un paquete distinto al del proyecto original:

```text
Paquete:   com.grapeds.android
Actividad: me.magnum.melonds.ui.emulator.EmulatorActivity
```

Utiliza una URI del juego como dato del intent y concede permiso de lectura con `FLAG_GRANT_READ_URI_PERMISSION`. El juego debe estar accesible para GrapeDS.

## Compilar desde el código fuente

Este repositorio distribuye el código como un **ZIP ligero**. Descárgalo y extráelo antes de compilar.

Necesitas **Java 21**, Android SDK **37**, NDK **28.0.13004108** y CMake **3.22.1**. Configura la ruta de tu Android SDK en un archivo local `local.properties`.

```sh
sh ./gradlew :app:assembleGitHubProdDebug \
  -PgrapeDsAbis=arm64-v8a \
  -PgrapeDsCompact=true \
  --no-daemon --max-workers=1
```

APK generado:

```text
app/build/outputs/apk/gitHubProd/debug/app-gitHub-prod-debug.apk
```

El ZIP conserva el código usado por la aplicación, los avisos de licencia y las dependencias nativas necesarias. Excluye cachés, resultados de compilación y ejemplos/documentación de Oboe que no utiliza este APK.

Una compilación propia usa tu configuración de firma; no podrá actualizar el APK distribuido si el certificado es diferente.

## Apoya GrapeDS

Si te gusta el proyecto y quieres apoyar su desarrollo, puedes hacerlo en mi Patreon:

**[Apoyar GrapeDS en Patreon](https://www.patreon.com/c/unnpcmas/membership)**

El apoyo es voluntario. Este enlace pertenece al creador de GrapeDS; no es una campaña de donaciones de melonDS ni de su equipo original.

## Créditos

GrapeDS existe gracias al trabajo de los proyectos originales y sus colaboradores:

- **[melonDS](https://melonds.kuribo64.net/)** — emulador original, desarrollado por Arisotura y el equipo de melonDS. [Código fuente de melonDS](https://github.com/melonDS-emu/melonDS).
- **[melonDS Android](https://github.com/rafaelvcaetano/melonDS-android)** — adaptación a Android de Rafael V. Caetano y sus colaboradores, base de este proyecto.
- **[GrapeDS](https://github.com/Unnpcmas/GrapeDS-beta)** — adaptación y cambios específicos de este fork.
- Las demás bibliotecas conservan sus respectivos autores y licencias dentro del código fuente.

**GrapeDS es un fork independiente, no una versión oficial de melonDS ni un proyecto afiliado a Nintendo.** Los nombres y marcas pertenecen a sus respectivos propietarios.

## Licencia

GrapeDS mantiene la licencia **[GNU GPLv3](https://github.com/Unnpcmas/GrapeDS-beta/blob/main/LICENSE)** del proyecto original. El código fuente correspondiente a esta distribución está disponible en la descarga de arriba. Se conservan los avisos de copyright y las licencias de terceros.
