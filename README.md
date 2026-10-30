# Ghostty Debian Package Builder (.deb)

Este repositorio compila y empaqueta automáticamente [Ghostty](https://github.com/ghostty-org/ghostty) en formato `.deb` para **Debian 14 (Forky)** usando **GitHub Actions**.

## 🚀 ¿Cómo funciona?

1. **Automatizado**: Un pipeline de GitHub Actions se ejecuta 1 vez al día (06:00 UTC) para consultar si `ghostty-org/ghostty` ha publicado un nuevo release o tag.
2. **Sin duplicados**: Si la versión ya fue empaquetada y publicada en este repositorio, el workflow finaliza en segundos sin gastar minutos de cómputo.
3. **Entorno nativo**: Si hay una versión nueva, se compila dentro de un contenedor oficial `debian:forky` con todas las dependencias nativas (GTK 4, Libadwaita, GTK4 Layer Shell) y la versión exacta de Zig requerida por esa versión de Ghostty.
4. **Releases listos**: El archivo `.deb` final se publica automáticamente en la pestaña [Releases](../../releases) de este repositorio.

---

## 📦 Instalación del paquete en Debian

1. Ve a la pestaña **[Releases](../../releases)** y descarga el archivo `.deb` más reciente.
2. Instálalo en tu terminal:

```bash
sudo apt install ./ghostty_*_forky_amd64.deb
```
*(Usar `apt install` resolverá e instalará automáticamente cualquier dependencia faltante).*

---

## ⚙️ Ejecución manual

Puedes forzar la compilación de cualquier versión en cualquier momento:
1. Ve a la pestaña **Actions**.
2. Selecciona **Build Ghostty Debian Package**.
3. Haz clic en **Run workflow**.
4. *(Opcional)* Escribe un tag específico (ej. `v1.4.0`) o déjalo vacío para que compile el último release oficial existente.
