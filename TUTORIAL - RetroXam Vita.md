# 🎮 TUTORIAL — Deja tu PS Vita PERFECTA con RetroXam

Con esta guía tu PS Vita queda con:
- **El launcher RetroXam** (frontend propio): buscas el juego, pulsas X, se descarga y se abre solo.
- **RetroArch** con 132 cores → NES, SNES, GB/GBC/GBA, Mega Drive, Mega CD, 32X, PSX, Neo Geo, CPS-1/2/3 y FBNeo.
- **DaedalusX64** → Nintendo 64 · **OpenBOR** → beats 'em up.
- **~1.900 juegos** seleccionados (16 sistemas), con **prioridad a versiones en español**.

> **Flujo en 5 pasos:** Liberar → SD2Vita → Copiar kit → Instalar VPKs → Abrir RetroXam y jugar.

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
| `RetroXam.vpk` | El launcher RetroXam | 4,5 MB |
| `RetroArch.vpk` | RetroArch + 132 cores (no hace falta nada más) | ~650 MB |
| `DaedalusX64.vpk` | Emulador de Nintendo 64 | 3 MB |
| `DaedalusX64-data.zip` | Datos de DaedalusX64 (configs, idiomas, shaders) | 75 MB |
| `OpenBOR.vpk` | Motor Beats of Rage | 1 MB |

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

1. En la Vita abre **VitaShell** (si no lo tienes: VitaDeploy → App Downloader → VitaShell).
2. Conecta por **USB**: pulsa **START** (ajustes) y comprueba que el botón SELECT está en modo **USB**; cierra con **O** y pulsa **SELECT** → conecta el cable al PC.
   - *Sin cable (WiFi):* en los ajustes de VitaShell pon el SELECT en modo **FTP**, cierra con **O** y pulsa **SELECT** → aparece una dirección `ftp://…:1337` → conéctate desde el PC (FileZilla o Explorador de Windows).
3. En el PC, abre la Vita y navega a `ux0:` → **`data`**. Copia ahí estos archivos desde el **Kit RetroXam Vita**:
   - ✅ `RetroXam.vpk`
   - ✅ `RetroArch.vpk`
   - ✅ `DaedalusX64.vpk`
   - ✅ `OpenBOR.vpk`
4. **`DaedalusX64-data.zip`**: extráelo **en el PC** (clic derecho → Extraer todo) y copia la carpeta **`DaedalusX64`** que sale a `ux0:/data/` → quedará `ux0:/data/DaedalusX64/…`.
   - *Alternativa en la propia Vita:* en VitaShell entra al zip (X), pulsa **△ → Mark all**, otra vez **△ → Copy**, sal (O), ve a `ux0:/data/` y pega (**△ → Paste**).
5. Desconecta el cable (o cierra el FTP pulsando **SELECT**).

---

## ⚙️ PARTE 3 — Instalar los 4 VPKs

En **VitaShell**, ve a `ux0:/data/` y pulsa **X sobre cada .vpk** → confirma → se instala:

1. `RetroXam.vpk` — el launcher
2. `RetroArch.vpk` — es grande: tarda 1-2 min (se extrae en la consola)
3. `DaedalusX64.vpk`
4. `OpenBOR.vpk`

> Si alguna burbuja no aparece en la pantalla de inicio: en VitaShell pulsa **△ → Refresh livearea**.

---

## 🧬 PARTE 4 — BIOS (la única parte que aportas tú)

Copia en **`ux0:/data/retroarch/system/`** (créala si no existe):

| Archivo | Para | ¿Obligatorio? |
|---|---|---|
| `SCPH1001.BIN` | PlayStation (pcsx_rearmed) | Muy recomendado |
| `neogeo.zip` | Neo Geo | El launcher la baja sola la 1ª vez; mejor tenerla |
| `gba_bios.bin` | Game Boy Advance (mejor compatibilidad) | Opcional |

> Abre **RetroArch** una vez (así se crea `ux0:/data/retroarch/`), sal, y copia los BIOS por USB/FTP como en la Parte 2. Los BIOS se sacan de tu propia consola o de copias legales.

---

## 🚀 PARTE 5 — El launcher RetroXam (tu centro de juegos)

1. Abre **RetroXam** desde la pantalla de inicio.
2. **Activa el WiFi**: la primera vez que entres a cada sistema baja su lista desde GitHub (luego queda guardada).
3. Controles:

| Botón | Acción |
|---|---|
| **X** | Descarga el juego (si falta) y lo abre en su emulador, ya cargado |
| **Arriba/Abajo** | Mover por la lista |
| **Izq / Der** | Saltar 10 juegos de golpe |
| **L / R** | Cambiar de sistema (consola) |
| **START** | Mostrar/ocultar la ayuda |
| **Triángulo** | Recargar la lista del sistema · **SELECT**: recargar TODAS |
| **O** | Salir |

4. Leyenda: **`+`** = ya en la Vita · **`-`** = pendiente · **`ES`** = versión en español · punto de color = WiFi. Arriba a la derecha: **espacio libre**.
5. Los juegos se guardan en **`ux0:/data/retroxam/roms/<sistema>/`**. Los multi-disco de PSX crean su `.m3u` solos, y la BIOS de Neo Geo se descarga automáticamente.
6. **Sistemas incluidos** (16): NES · SNES · GB · GBC · GBA · N64 · Mega Drive · Mega CD · 32X · PSX · Neo Geo · CPS-1 · CPS-2 · CPS-3 · FBNeo · OpenBOR (~1.900 juegos, prioridad español).

---

## 💻 PARTE 6 — Descargar en masa desde el PC (opcional)

> Para lotes grandes (50 de PSX, toda la SNES…). Usa el PC (ya tienes las herramientas en `C:\Users\XAM-PC\RetroXamTools`).

Abre una terminal y:

```bat
cd C:\Users\XAM-PC\RetroXamTools

:: Bajar (elige sistemas; reanudable; --flat deja los archivos planos, como los quiere el launcher)
python descargar_vita.py --repo https://github.com/servixam-max/RetroXamVita --out D:\VitaROMs --flat --systems nes,snes,megadrive

:: Subirlas a la Vita directo por FTP (VitaShell en modo FTP; lee la IP en su pantalla, puerto 1337)
python descargar_vita.py --repo https://github.com/servixam-max/RetroXamVita --out D:\VitaROMs --flat --ftp 192.168.1.50:1337 --ftp-dir /ux0:/data/retroxam/roms
```

- Si lo vuelves a lanzar, **salta lo ya descargado/subido** (puedes ir por tandas).
- Con `--limit 20` bajas solo 20 por sistema (selección rápida).

**Tamaños orientativos** (para que elijas qué te cabe):

| Sistema | Juegos | Peso | Sistema | Juegos | Peso |
|---|---|---|---|---|---|
| NES | 239 | 30 MB | CPS-1 | 38 | 82 MB |
| SNES | 239 | 364 MB | CPS-2 | 41 | 549 MB |
| GB | 96 | 21 MB | CPS-3 | 6 | 278 MB |
| GBC | 53 | 73 MB | FBNeo | 220 | 1,0 GB |
| GBA | 89 | 3,7 GB | Neo Geo | 110 | 2,0 GB |
| N64 | 119 | 1,8 GB | PSX | 238 | 86,7 GB |
| Mega Drive | 186 | 168 MB | Mega CD | 43 | 9,7 GB |
| 32X | 38 | 119 MB | OpenBOR | 120 | 17,1 GB |

> Total todo ≈ **124 GB** — no hace falta todo. Gracias al `--flat`, el launcher las marcará como **`+`** y las abrirá al instante (descomprime solo).

---

## ✨ PARTE 7 — Toques finales

- **RetroArch**: no hace falta tocar nada — el launcher le pasa el core correcto de cada sistema y los ajustes se guardan solos al salir.
- **DaedalusX64**: no todos los juegos de N64 van finos en la Vita (es normal; es una consola de 2011). También puedes meter ROMs a mano en `ux0:/data/DaedalusX64/roms/` y abrirlas desde el propio emulador.
- **OpenBOR**: los `.pak` se copian solos a `ux0:/data/openbor/paks/`; a mano, ponlos ahí y abre OpenBOR para elegir cuál cargar.
- **Mandos**: la Vita usa sus propios controles; en RetroArch puedes reasignar en Settings → Input.

---

## 🧾 Resumen: qué emulador usa cada sistema

| Sistema | Emulador | Core |
|---|---|---|
| NES | RetroArch | fceumm |
| SNES | RetroArch | snes9x2005_plus |
| GB / GBC | RetroArch | gambatte |
| GBA | RetroArch | gpsp |
| Mega Drive / Mega CD | RetroArch | genesis_plus_gx |
| 32X | RetroArch | picodrive |
| PSX | RetroArch | pcsx_rearmed |
| Neo Geo | RetroArch | fbneo |
| CPS-1 / CPS-2 | RetroArch | mame2003_plus |
| CPS-3 / FBNeo | RetroArch | fbneo |
| N64 | DaedalusX64 | — |
| OpenBOR | OpenBOR | — |

---

## 🔧 Problemas típicos

| Problema | Solución |
|---|---|
| "No hay juegos cargados" | Sin WiFi o listas sin bajar: activa WiFi y pulsa **SELECT** |
| Un juego no arranca | Bórralo de `ux0:/data/retroxam/roms/<sistema>/` y vuelve a descargarlo (X sobre el juego) |
| Sin espacio | El launcher muestra el libre arriba a la derecha; borra juegos o pon una microSD mayor |
| La burbuja no aparece | VitaShell → **△ → Refresh livearea** |
| El launcher no ve la SD | Repasa la Parte 1 (YAMT + ux0 → SD2Vita + reinicio) |

---

*RetroXam Vita — 16 sistemas · ~1.900 juegos · RetroArch + DaedalusX64 + OpenBOR*
*Listas: `github.com/servixam-max/RetroXamVita`*
