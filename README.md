# Mi IPTV — proyecto Android

Proyecto fuente para Android TV / TV Box (Kotlin + AndroidX Media3).

## Funciones incluidas en el código
- Importar listas M3U desde el almacenamiento.
- Reproducir streams compatibles con ExoPlayer.
- Categorías TV EN VIVO, VOD, SERIES, TELENOVELAS, DEPORTES y categorías originales de países/proveedores.
- Normalización de nombres de categoría para VOD, SERIES, TELENOVELAS y DEPORTES.
- Búsqueda, favoritos y orden alfabético.
- Mostrar imágenes desde `tvg-logo` cuando la lista M3U proporciona una URL válida.
- Agregar, editar y eliminar elementos.
- Exportar M3U completo o la categoría seleccionada.
- Exportar respaldo JSON.
- Detección de temporadas/capítulos con patrones S01E02, 1x02 y “Temporada 1 Capítulo 2”.
- Persistencia local.

## Generar el APK automáticamente con GitHub Actions
1. En GitHub crea un repositorio nuevo.
2. Sube **el contenido** de esta carpeta `iptv_player` (no el ZIP dentro de otra carpeta).
3. Abre la pestaña **Actions** del repositorio.
4. Selecciona **Build Mi IPTV APK** y pulsa **Run workflow**. También se ejecuta al subir cambios a `main` o `master`.
5. Cuando termine en verde, abre esa ejecución y descarga el artefacto **MiIPTV-debug-apk**. Dentro estará `app-debug.apk`.

La compilación usa JDK 17 y Gradle 8.7. El workflow está configurado, pero la compilación remota todavía debe ejecutarse en tu repositorio para confirmar que genera el APK.

## Compilar localmente
Abrir esta carpeta en Android Studio con JDK 17 y Android SDK 35; ejecutar `gradle :app:assembleDebug`.

## Límites conocidos
- Las carátulas dependen de que la lista incluya URLs `tvg-logo`; no se consulta automáticamente una base externa de películas.
- La agrupación de episodios depende de patrones reconocibles en el nombre.
- El respaldo JSON se exporta; la restauración de JSON aún no está implementada.
- No incluye listas ni contenido IPTV. Carga una lista propia autorizada.
