# 🎮 TUTORIAL — Deja tu PS Vita PERFECTA con RetroXam (v2.4)

Con esta guía tu PS Vita queda con:
- **El launcher RetroXam v2.4**: buscas el juego, pulsas X, se descarga y se abre solo. Con **carátulas**, iconos, temas y **AUTO-CONFIG** (bezels + shaders se instalan solos).
- **RetroArch** (132 cores) → NES, SNES, GB/GBC/GBA, Mega Drive, Mega CD, 32X, PSX, Neo Geo, CPS-1/2/3 y FBNeo — y **SHADERS** con la build Piglet.
- **DaedalusX64** → Nintendo 64 · **OpenBOR** → beats 'em up.
- **PSP** (vía **Adrenaline**, ¡NATIVO, no emulado!) y **Dreamcast** (vía **Flycast**, juegos compatibles).
- **~2.200 juegos** seleccionados (**18 sistemas**), con **prioridad a versiones en español**.

> **Flujo en 5 pasos:** Liberar → SD2Vita → Copiar kit → Instalar VPKs → Abrir RetroXam y jugar.
>
> ⚡ **Atajo (recomendado):** conecta la Vita por **FTP** (VitaShell → SELECT) y ejecuta en el PC **`INSTALAR VITA.bat`** del Escritorio: te sube TODO a su sitio solo: configs, BIOS, VPKs, datos del N64, caratulas y el extra de PSP. Después solo instalas los VPKs con X.

---

## 📦 Lo que necesitas

| Cosa | Detalle |
|---|---|
| PS Vita | Cualquier modelo. Si no está liberada → Parte 0 |
| microSD + SD2Vita | **Muy recomendado** (128 GB+). El kit + juegos no caben en la tarjeta oficial |
| PC Windows + cable USB | También vale por WiFi (FTP) |
| Kit RetroXam Vita | Acceso directo **"Kit RetroXam Vita"** del Escritorio (carpeta `C:\Users\XAM-PC\VitaKit\apps`) |

**Contenido del kit:**

| Archivo | Qué es | Tamaño |
|---|---|---|
| `RetroXam.vpk` | El launcher (**v2.4**: + **PSP y Dreamcast**, auto-config de bezels/shaders, menú de 18 sistemas) | 5 MB |
| `RetroArch_piglet.vpk` | RetroArch **CON shaders** (la recomendada) | ~473 MB |
| `RetroArch.vpk` | RetroArch "normal" (alternativa; sin menú de shaders) | ~646 MB |
| `PIBConfig.vpk` | Librerías que exige la build piglet (se abre **una vez**) | 2 MB |
| `DaedalusX64.vpk` + `DaedalusX64-data.zip` | Emulador + datos de Nintendo 64 | 3 MB + 75 MB |
| `OpenBOR.vpk` | Motor Beats of Rage | 1 MB |
| `Adrenaline.vpk` + `661.PBP` | **PSP nativo** (el firmware se baja solo; 661.PBP es el plan B) | 0,5 + 31 MB |
| `Flycast.vpk` | Dreamcast (experimental — solo juegos compatibles) | 4,6 MB |
| `ShaRKBR33D.vpk` | Librería `libshacccg.suprx` que exigen Daedalus y los shaders (se abre **una vez**) | 1,5 MB |
| `Config_RetroXam_Piglet.zip` | Bezels + shaders + ajustes por core (v1.1). **La v2.4 del launcher ya lo instala sola** — este zip es el respaldo manual | 0,7 MB |
| `RetroXamVita_Covers.zip` | Las 2.151 carátulas de todos los sistemas (opcional: se descargan solas) | 54 MB |
| `PSP_1toque\` | **Extra opcional**: lanzar juegos PSP directos desde RetroXam (ABM + AdrenalineLauncher + módulos + LEEME) | 11 MB |
| `PSVitaAlive.vpk` | **Tienda de homebrew** para la Vita (catalogo abierto, se actualiza sola) — opcional | 8 MB |
| `INSTALAR VITA.bat` | Instalador de PC en 1 paso (por FTP) | — |

---

## 🛠️ PARTE 0 — Liberar la Vita (solo si no lo está)

> Si ya tienes **Enso** instalado (se ve "HENkaku" en Ajustes), salta a la Parte 1.

1. Mira tu firmware: **Ajustes → Sistema → Información del sistema**.
   - HENlo funciona en **3.65, 3.68 y 3.74**. Si tienes otra versión, sigue la guía oficial **vita.hacks.guide** (te llevará a 3.65 igualmente).
2. En la Vita, abre el **navegador** y entra en: `http://jailbreak.psp2.dev`
3. Pulsa **"Unlock my Vita"** → **"Unlock"**. Si va bien, verás la pantalla **henlo-bootstrap**.
4. Pulsa **X en "Install henkaku"** → **X en "Install VitaDeploy"** → **X en "Exit"**.
5. **Ajustes → HENkaku Settings** → marca **"Enable Unsafe Homebrew"** → cierra Ajustes.
6. Hazla **permanente** (recomendado): abre **VitaDeploy** → **"Install a different OS"** → **"Quick 3.65 Install"** (necesita internet):
   - Espera a que descargue → **X** para confirmar → lee el aviso, espera 20 s → **X** otra vez.
   - ⚠️ No dejes que la consola se suspenda durante el proceso. Al terminar reinicia ya con CFW (**firmware 3.65 + Enso, para siempre**).
7. Instala **VitaShell** (tu gestor de archivos): **VitaDeploy → App Downloader → VitaShell** → descarga e instala.

> Referencia oficial (por si algo se tuerce): **vita.hacks.guide**

---

## 💾 PARTE 1 — SD2Vita (la memoria de verdad)

> Si hiciste "Quick 3.65 Install", **YAMT ya viene instalado** — salta al paso 1.

1. Mete el adaptador **SD2Vita con tu microSD** en la ranura de juegos.
2. **VitaDeploy → Miscellaneous → Format a storage device** → Target: `SD2Vita`, Filesystem: **`TexFAT`** → **"Format target storage"**.
3. Vuelve al menú → **Reboot**.
4. **Ajustes → Dispositivos → Dispositivos de almacenamiento** → activa **"Use YAMT"**:
   - Deja `ux0:` en `Default` y `uma0:` en `SD2Vita` → apaga y enciende la consola.
   - *(Solo si ya tenías cosas instaladas:)* en **VitaShell**, copia TODO de `ux0:` a `uma0:` (△ → Mark all → Copy → entrar en `uma0:` → △ → Paste).
5. Cambia a: **`ux0:` → `SD2Vita`** y `uma0:` → `Default` → apaga y enciende.
   → **ux0: (lo principal) ahora es tu microSD.** Todo lo que sigue va ahí.

---

## 📁 PARTE 2 — Copiar el kit a la Vita

> ⚡ **Si usas `INSTALAR VITA.bat` (PC + FTP)**: esta parte y las copias de config/BIOS las hace él solo. Salta directamente a la Parte 3 a instalar los VPKs.

1. En la Vita abre **VitaShell** (si no lo tienes: VitaDeploy → App Downloader → VitaShell).
2. Conecta por **USB**: pulsa **START** (ajustes) y comprueba que el botón SELECT está en modo **USB**; cierra con **O** y pulsa **SELECT** → conecta el cable al PC.
   - *Sin cable (WiFi):* en los ajustes de VitaShell pon el SELECT en modo **FTP**, cierra con **O** y pulsa **SELECT** → aparece una dirección `ftp://…:1337`.
3. En el PC, navega a `ux0:/` y copia ahí desde el kit: `RetroXam.vpk`, `RetroArch_piglet.vpk`, `PIBConfig.vpk`, `DaedalusX64.vpk`, `OpenBOR.vpk`, `ShaRKBR33D.vpk`, `Adrenaline.vpk`, `Flycast.vpk` (+ `661.PBP` si quieres el plan B de Adrenaline).
4. **`DaedalusX64-data.zip`**: *(el instalador del pack lo copia solo)* extráelo en el PC y copia la carpeta **`DaedalusX64`** a `ux0:/data/` → quedará `ux0:/data/DaedalusX64/…`.
   - *Alternativa en la Vita:* en VitaShell entra al zip (X) → **△ → Mark all** → **△ → Copy** → sal → `ux0:/data/` → **△ → Paste**.
5. Desconecta el cable (o cierra el FTP pulsando **SELECT**).

---

## ⚙️ PARTE 3 — Instalar los VPKs

En **VitaShell**, ve a `ux0:/` y pulsa **X sobre cada .vpk** → confirma → se instala. **En este orden**:

1. `RetroXam.vpk` — el launcher (v2.4)
2. `PIBConfig.vpk` — **ábrelo y pulsa X** (1 segundo; instala las librerías). Cierra.
3. `RetroArch_piglet.vpk` — la build con shaders (si ya tenías RetroArch, esta la **sustituye**; tus juegos y ajustes se quedan)
4. `ShaRKBR33D.vpk` — **ábrelo una vez** (instala `libshacccg.suprx`, lo exigen Daedalus y los shaders). Tarda un minuto. Reinicia después.
5. `DaedalusX64.vpk` — N64
6. `OpenBOR.vpk` — beats 'em up
7. `Adrenaline.vpk` — **ábrelo y pulsa X** (baja el firmware solo; necesita internet). PSP nativo.
8. `Flycast.vpk` — Dreamcast
9. `PSVitaAlive.vpk` — **opcional**: la tienda de homebrew para la Vita (catalogo abierto; se actualiza sola)
