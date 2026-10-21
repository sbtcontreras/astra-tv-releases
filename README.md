# Astra TV

Astra TV es un reproductor IPTV para Windows pensado para cuentas Xtream Codes. Reúne en una sola aplicación la TV en vivo con guía de programación, películas y series, con catch-up, control parental, favoritos y búsqueda global.

Tus credenciales y datos se guardan solo en tu equipo. Las credenciales se usan únicamente para conectarse a tu proveedor.

## Descargar

**[Descargar la última versión](https://github.com/sbtcontreras/astra-tv-releases/releases/latest)**

- Un único archivo: `AstraTV.exe`. Es portable: no requiere instalación. Ejecútalo y listo.
- Requisitos: Windows 10 u 11 de 64 bits. La app usa WebView2, que ya viene instalado en Windows 10 y 11.

### Primer inicio: aviso de SmartScreen

Windows puede mostrar la advertencia *"Windows protegió tu PC"* la primera vez que ejecutas `AstraTV.exe`. Para continuar:

1. Haz clic en **Más información**.
2. Haz clic en **Ejecutar de todas formas**.

Solo tienes que hacerlo una vez. Si prefieres comprobar el archivo antes de ejecutarlo, mira la sección [Verificar la descarga](#verificar-la-descarga).

## Actualizaciones

Astra TV busca nuevas versiones en esta página al iniciar y cada 6 horas. Cuando hay una versión nueva, la descarga, comprueba su firma digital (ed25519) con la clave incluida en la app y, si es válida, reemplaza el ejecutable y te pide reiniciar. Si la firma no coincide, la descarga se descarta.

La búsqueda automática se puede desactivar en **Ajustes**. Mientras tanto, siempre puedes buscar actualizaciones a mano.

Si usas la v0.1.0, descarga la última versión desde el enlace de arriba una sola vez. Desde la v0.2.0 en adelante, las actualizaciones son automáticas.

## Dónde se guardan tus datos

Todo se guarda localmente, en:

```
%LOCALAPPDATA%\app.astratv.desktop
```

Ahí están tus listas, el catálogo descargado, favoritos, progreso de reproducción y ajustes. Para borrar todo, cierra la app y elimina esa carpeta.

## Compartir listas (archivo `.astra`)

Puedes exportar tus listas desde **Ajustes** a un archivo `.astra` e importarlo en otro equipo.

> **Advertencia:** el archivo `.astra` contiene las **contraseñas** de tus listas en texto que se puede leer. Trátalo como una contraseña: no lo publiques, no lo subas a sitios públicos y compártelo solo por un canal privado.

## Verificar la descarga

Cada versión incluye, junto a `AstraTV.exe`, un archivo `AstraTV.exe.sha256` con la huella SHA-256 del ejecutable. Para comprobarla en PowerShell:

```powershell
(Get-FileHash .\AstraTV.exe -Algorithm SHA256).Hash.ToLower()
Get-Content .\AstraTV.exe.sha256
```

Si el primer valor coincide con el primero de `AstraTV.exe.sha256` (antes de los dos espacios), el archivo es el que se publicó.
