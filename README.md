<div align="center">

# GrapeDS

### Emulador de Nintendo DS y DSi para Android
### Nintendo DS and DSi emulator for Android

Un fork independiente de **melonDS Android**, con identidad propia y mejoras en la experiencia de uso.  
An independent **melonDS Android** fork with its own identity and user-experience improvements.

[![Versión](https://img.shields.io/badge/versión-2.0.9-7c3aed)](https://github.com/Unnpcmas/GrapeDS-beta)
[![Android](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)](https://github.com/Unnpcmas/GrapeDS-beta)
[![Arquitectura](https://img.shields.io/badge/arquitectura-arm64--v8a-555)](https://github.com/Unnpcmas/GrapeDS-beta)
[![Licencia](https://img.shields.io/badge/licencia-GPLv3-blue)](https://github.com/Unnpcmas/GrapeDS-beta/blob/main/LICENSE)
[![Patreon](https://img.shields.io/badge/Apoyar_GrapeDS-Patreon-FF424D?logo=patreon&logoColor=white)](https://www.patreon.com/c/AbelUki/membership)

**[Español](#español)** · **[English](#english)**

**[Descargar APK / Download APK](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.9.apk)** · **[Código fuente / Source code](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.9-source.zip)** · **[Problemas / Issues](https://github.com/Unnpcmas/GrapeDS-beta/issues)**

</div>

---

# Español

## Descargas

| Archivo | Descripción |
| --- | --- |
| [GrapeDS 2.0.9 · APK](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.9.apk) | APK beta para Android de 64 bits (`arm64-v8a`). |
| [GrapeDS 2.0.9 · Código fuente](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.9-source.zip) | Fuentes y dependencias nativas, sin compilaciones, cachés ni archivos locales. |

**Versión Android:** `2.0.9 GH` · **Código de versión:** `49` · **Paquete:** `com.grapeds.android`

El APK se distribuye como compilación **debug beta**, no como una versión de producción certificada. No incluye juegos ni archivos de Nintendo.

### Instalación

1. Descarga el archivo `.apk` desde esta página.
2. Permite la instalación desde tu navegador o gestor de archivos cuando Android lo solicite.
3. Abre el APK e instala GrapeDS.
4. Selecciona la carpeta de tus juegos obtenidos legalmente.

## Características

| Área | Funciones |
| --- | --- |
| Biblioteca | Exploración de juegos, iconos y organización de ROMs. |
| Controles | Pantalla táctil, controles en pantalla y compatibilidad con mandos. |
| Emulación | Nintendo DS y DSi, guardados y estados de partida. |
| Vídeo | Renderizado Software y OpenGL; Compute en dispositivos compatibles. |
| Personalización | Distribución de pantallas, temas e idioma inglés, español o del sistema. |
| Velocidad | Avance rápido con estado reiniciado al comenzar una sesión. |

La opción **Calidad** aparece en Ajustes como reserva para una función futura; todavía no cambia el emulador.

## Novedades de 2.0.9

- Corregida la superposición de las dos pantallas al volver a **Both screens**.
- Android espera a que el nuevo diseño quede medido antes de actualizar las áreas del renderizador.
- Conserva las mejoras de renderizado y preferencias de 2.0.8.

### Cambios incluidos desde 2.0.8

- OpenGL como selección inicial en dispositivos con GLES 3.2 cuando no existe un renderizador guardado.
- Software como selección inicial en dispositivos sin ese soporte.
- Conservación de las preferencias de renderizador ya guardadas.
- Se mantienen los ajustes de audio, avance rápido e idioma introducidos anteriormente.

Si ya tienes **Software** guardado, la actualización no lo cambia automáticamente. Puedes seleccionar **OpenGL** en **Ajustes → Vídeo** si tu dispositivo ofrece esa opción.

## Rendimiento y compatibilidad

El rendimiento depende del juego, procesador, GPU, controladores y ajustes. No se garantiza una velocidad concreta en todos los dispositivos.

- Empieza con resolución interna **1×** al utilizar renderizado acelerado.
- Mantén el avance rápido apagado para jugar a velocidad normal.
- JIT y renderizado por hilos pueden mejorar el rendimiento, según el juego y dispositivo.
- Si OpenGL presenta errores gráficos, vuelve a Software.

**Estado de verificación:** compilación y tests unitarios completados; firma del APK verificada.

### Limitaciones

- La descarga solo incluye `arm64-v8a`.
- El multijugador local y la tarjeta SD de DSi siguen pendientes en esta distribución.
- DSi/DSiWare y el firmware externo pueden requerir archivos propios válidos.

## Integración con otros frontends

```text
Paquete:   com.grapeds.android
Actividad: me.magnum.melonds.ui.emulator.EmulatorActivity
```

Utiliza una URI del juego como dato del intent y concede permiso de lectura con `FLAG_GRANT_READ_URI_PERMISSION`.

## Compilar desde el código fuente

Descarga y extrae el **ZIP ligero**. Necesitas **Java 21**, Android SDK **37**, NDK **28.0.13004108** y CMake **3.22.1**. Configura la ruta del SDK en `local.properties`.

```sh
sh ./gradlew :app:assembleGitHubProdDebug \
  -PgrapeDsAbis=arm64-v8a \
  -PgrapeDsCompact=true \
  --no-daemon --max-workers=1
```

El APK se genera en:

```text
app/build/outputs/apk/gitHubProd/debug/app-gitHub-prod-debug.apk
```

El ZIP conserva el código de la aplicación, avisos de licencia y dependencias nativas necesarias. Excluye cachés, resultados de compilación y ejemplos o documentación de Oboe no utilizados por este APK.

## Apoya GrapeDS

El apoyo es voluntario y pertenece al creador de GrapeDS

**[Apoyar GrapeDS en Patreon](https://www.patreon.com/c/AbelUki/membership)**

## Créditos

- **[melonDS](https://melonds.kuribo64.net/)** — emulador original de Arisotura y el equipo de melonDS. [Código fuente](https://github.com/melonDS-emu/melonDS).
- **[melonDS Android](https://github.com/rafaelvcaetano/melonDS-android)** — adaptación de Rafael V. Caetano y sus colaboradores, base de este proyecto.
- **[GrapeDS](https://github.com/Unnpcmas/GrapeDS-beta)** — adaptación y cambios específicos de este fork.
- Las demás bibliotecas conservan sus respectivos autores y licencias.

**GrapeDS es un fork independiente; no es una versión oficial de melonDS ni está afiliado a Nintendo.** Los nombres y marcas pertenecen a sus respectivos propietarios.

## Licencia

GrapeDS mantiene la licencia **[GNU GPLv3](https://github.com/Unnpcmas/GrapeDS-beta/blob/main/LICENSE)** del proyecto original. El código fuente correspondiente está disponible arriba.

---

# English

## Downloads

| File | Description |
| --- | --- |
| [GrapeDS 2.0.9 · APK](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.9.apk) | Beta APK for 64-bit Android devices (`arm64-v8a`). |
| [GrapeDS 2.0.9 · Source code](https://github.com/Unnpcmas/GrapeDS-beta/raw/refs/heads/main/GrapeDS-2.0.9-source.zip) | Source and native dependencies without builds, caches, or local files. |

**Android version:** `2.0.9 GH` · **Version code:** `49` · **Package:** `com.grapeds.android`

The APK is distributed as a **debug beta** build, not a certified production release. It does not include games or Nintendo files.

### Installation

1. Download the `.apk` file from this page.
2. Allow installation from your browser or file manager when Android asks.
3. Open the APK and install GrapeDS.
4. Select the folder containing your legally obtained games.

## Features

| Area | Features |
| --- | --- |
| Library | Game browsing, icons, and ROM organization. |
| Controls | Touchscreen, on-screen controls, and gamepad support. |
| Emulation | Nintendo DS and DSi, save files, and save states. |
| Video | Software and OpenGL renderers; Compute on compatible devices. |
| Customization | Screen layouts, themes, and English, Spanish, or system language. |
| Speed | Fast forward with its state reset when a session starts. |

The **Quality** setting is reserved for a future feature and does not change emulation yet.

## What's new in 2.0.9

- Fixed both screens overlapping after switching back to **Both screens**.
- Android now waits for the new layout to be measured before updating renderer areas.
- Includes the renderer and preference improvements from 2.0.8.

### Changes included since 2.0.8

- OpenGL is the initial renderer on devices reporting GLES 3.2 when no renderer preference exists.
- Software remains the initial renderer on devices without that support.
- Existing saved renderer preferences are preserved.
- Previous audio, fast-forward, and language settings remain available.

If **Software** is already saved, updating does not change it automatically. You can select **OpenGL** under **Settings → Video** when available.

## Performance and compatibility

Performance depends on the game, processor, GPU, drivers, and settings. A specific speed is not guaranteed on every device.

- Start with **1×** internal resolution when using accelerated rendering.
- Keep fast forward disabled for normal-speed gameplay.
- JIT and threaded rendering may improve performance depending on the game and device.
- Switch back to Software if OpenGL causes graphical errors.

**Verification status:** the build and unit tests completed successfully, and the APK signature was verified.

### Limitations

- The download only includes `arm64-v8a`.
- Local multiplayer and DSi SD card support remain unavailable in this distribution.
- DSi/DSiWare and external firmware may require your own valid files.

## Third-party frontend integration

```text
Package:  com.grapeds.android
Activity: me.magnum.melonds.ui.emulator.EmulatorActivity
```

Use the game URI as the intent data and grant read access with `FLAG_GRANT_READ_URI_PERMISSION`.

## Building from source

Download and extract the **lightweight ZIP**. You need **Java 21**, Android SDK **37**, NDK **28.0.13004108**, and CMake **3.22.1**. Set your SDK path in `local.properties`.

```sh
sh ./gradlew :app:assembleGitHubProdDebug \
  -PgrapeDsAbis=arm64-v8a \
  -PgrapeDsCompact=true \
  --no-daemon --max-workers=1
```

The APK is generated at:

```text
app/build/outputs/apk/gitHubProd/debug/app-gitHub-prod-debug.apk
```

The ZIP retains application code, license notices, and required native dependencies. It excludes caches, build outputs, and unused Oboe examples or documentation.

## Support GrapeDS

Support is voluntary and goes to the GrapeDS creator
**[Support GrapeDS on Patreon](https://www.patreon.com/c/AbelUki/membership)**

## Credits

- **[melonDS](https://melonds.kuribo64.net/)** — the original emulator by Arisotura and the melonDS team. [Source code](https://github.com/melonDS-emu/melonDS).
- **[melonDS Android](https://github.com/rafaelvcaetano/melonDS-android)** — Android port by Rafael V. Caetano and contributors, used as this project's foundation.
- **[GrapeDS](https://github.com/Unnpcmas/GrapeDS-beta)** — adaptation and changes specific to this fork.
- Other libraries retain their respective authors and licenses.

**GrapeDS is an independent fork. It is not an official melonDS release and is not affiliated with Nintendo.** Names and trademarks belong to their respective owners.

## License

GrapeDS retains the original project's **[GNU GPLv3 license](https://github.com/Unnpcmas/GrapeDS-beta/blob/main/LICENSE)**. The corresponding source code is available above.
