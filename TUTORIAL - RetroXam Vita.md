# 🎮 TUTORIAL — Deja tu PS Vita PERFECTA con RetroXam (v2.4)

Con esta guía tu PS Vita queda con:
- **El launcher RetroXam v2.4**: buscas el juego, pulsas X, se descarga y se abre solo. Con **carátulas**, iconos, temas y **AUTO-CONFIG** (bezels + shaders se instalan solos).
- **RetroArch** (132 cores) → NES, SNES, GB/GBC/GBA, Mega Drive, Mega CD, 32X, PSX, Neo Geo, CPS-1/2/3 y FBNeo — y **SHADERS** con la build Piglet.
- **DaedalusX64** → Nintendo 64 · **OpenBOR** → beats 'em up.
- **PSP** (vía **Adrenaline**, ¡NATIVO, no emulado!) y **Dreamcast** (vía **Flycast**, juegos compatibles).
- **~2.200 juegos** seleccionados (**18 sistemas**), con **prioridad a versiones en español**.

> **Flujo en 5 pasos:** Liberar → SD2Vita → Copiar kit → Instalar VPKs → Abrir RetroXam y jugar.
>
> ⚡ **Atajo (recomendado):** conecta la Vita por **FTP** (VitaShell → SELECT) y ejecuta en el PC **`INSTALAR VITA.bat`** del Escritorio: te sube TODO a su sitio solo (configs, BIOS, VPKs y el extra de PSP). Después solo instalas los VPKs con X.

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
4. **`DaedalusX64-data.zip`**: extráelo en el PC y copia la carpeta **`DaedalusX64`** a `ux0:/data/` → quedará `ux0:/data/DaedalusX64/…`.
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

> Si alguna burbuja no aparece: en VitaShell pulsa **△ → Refresh livearea**.
>
> **N64 (importante)**: copia y extrae `DaedalusX64-data.zip` en `ux0:/data/` (queda `ux0:/data/DaedalusX64/...`) y ejecuta **ShaRKBR33D** una vez. Sin esas dos cosas, Daedalus da el error **C2-12828-1**.

---

## 🎨 PARTE 4 — Bezels y shaders (AUTO — cortesía de la v2.4)

**No tienes que hacer nada**: al abrir RetroXam por primera vez (con la microSD y WiFi), el launcher **instala solo** los marcos (bezels) + shaders + ajustes por core. Lo verás en pantalla: *"Instalando config RetroXam (bezels + shaders)..."* — tarda unos segundos, una única vez.

- ✅ **Bezels**: marcos con el logo de cada consola y la seta 1-UP 🍄 en NES, SNES, GB/GBC, GBA, Mega Drive/CD, 32X, PSX, NeoGeo/Arcade y CPS-1/2 (el juego va dentro de su ventana exacta).
- ✅ **Shaders**: CRT para las de TV (crt-pi), LCD para Game Boy (lcd3x) y nitidez para GBA (sharp-bilinear). Se activan por core solos.
- **Respaldo manual** (solo si algo fallara): extraer `Config_RetroXam_Piglet.zip` en `ux0:/data/retroarch/` con VitaShell.
- **Cambiar shader a mano**: con un juego abierto → **Quick Menu → Shaders** (solo existe en la build piglet ✓) → elige otro → guarda con **Save Core Override**.
- Si algún juego saliera con la imagen movida: ábrelo con **Ajustes → Vídeo → Escalado** → "Relación de aspecto: **Personalizada**" y pon el viewport del LEEME del pack (4:3 = 120/2/720/540 · GB/GBC = 240/56/480/432 · GBA = 156/56/648/432) → **guardar override del core**. (Con la v2.4 esto no debería pasar ya.)

---

## 🧬 PARTE 5 — BIOS (la única parte que aportas tú)

Copia en **`ux0:/data/retroarch/system/`** (créala si no existe):

| Archivo | Para | ¿Obligatorio? |
|---|---|---|
| `SCPH1001.BIN` | PlayStation (pcsx_rearmed) | Muy recomendado |
| `bios_CD_E.bin` + `bios_CD_U.bin` + `bios_CD_J.bin` | Mega CD (genesis_plus_gx) | **Sí** para jugar Mega CD (una por región: EU/US/JAP) |
| `neogeo.zip` | Neo Geo | El launcher la baja sola la 1ª vez; mejor tenerla |
| `gba_bios.bin` | Game Boy Advance (mejor compatibilidad) | Opcional |

> Abre **RetroArch** una vez (así se crea `ux0:/data/retroarch/`), y copia los BIOS por USB/FTP como en la Parte 2. Los BIOS se sacan de tu propia consola o de copias legales. *(Con `INSTALAR VITA.bat` van incluidos los del kit.)*

---

## 🚀 PARTE 6 — El launcher RetroXam (tu centro de juegos)

1. Abre **RetroXam** desde la pantalla de inicio.
2. **Activa el WiFi**: la primera vez que entres a cada sistema baja su lista desde GitHub (luego queda guardada). Si te falta alguna lista, **SELECT → Actualizar listas**.
3. Controles:

| Botón | Acción |
|---|---|
| **X** | Descarga el juego (si falta) y lo abre en su emulador, ya cargado |
| **Cuadrado** | **Buscar** un juego por nombre (teclado en pantalla) |
| **Cuadrado (mantener ~1 s)** | Añadir/quitar el juego de **★ Favoritos** |
| **Triángulo** | Recargar la lista del sistema |
| **Triángulo (mantener ~1 s)** | **Borrar** el juego de la consola |
| **Arriba/Abajo** | Mover por la lista · **Izq/Der** = saltar 10 |
| **L / R** | Cambiar de sistema (consola) |
| **SELECT** | **Menú**: sistemas, buscar, favoritos, descargados, ajustes y prueba de red |
| **START** | Mostrar/ocultar la ayuda |
| **O** | Salir (o cancelar una descarga en curso) |

> 🆕 **v2.4 — PSP y Dreamcast + auto-config**: los sistemas nuevos salen en el menú (iconos oficiales). Al pulsar X en un juego **PSP** se baja a `ux0:/pspemu/ISO/` y — con el extra "1 toque" — **arranca directo**; sin el extra se abre Adrenaline para elegirlo. Los juegos de **Dreamcast** arrancan directos con Flycast. Y el launcher **se auto-configura** (bezels+shaders) la primera vez.

> 🆕 **v2.3 — descargas a prueba de balas**: descargas **por trozos**: progreso en vivo, **cancelar con O** (se conserva lo bajado) y **reanudar** donde iba al reintentar. Pantalla **Descargados** (mira con su tamaño y borra). Al abrir un juego, RetroXam **se cierra solo**. Burbuja/fondo con la seta 1-UP 🍄.

4. Leyenda: **`+`** = ya en la Vita · **`-`** = pendiente · **`★`** = favorito · **`ES`** = versión en español · punto de color = WiFi. Arriba: reloj, batería y espacio libre.
5. **Carátulas**: el panel derecho muestra la portada del juego (se descarga sola con WiFi). ¿Todas de golpe? Descomprime `RetroXamVita_Covers.zip` en `ux0:/data/retroxam/`.
6. **Descargas robustas**: primero el **PUENTE del PC/Mac**, luego http/https directos. ¿Algo falla? Menú → **START** = prueba de red; **Ajustes → Ver registro** (`ux0:/data/retroxam/retroxam.log`).
7. Los juegos se guardan en `ux0:/data/retroxam/roms/<sistema>/` (los de PSP, en `ux0:/pspemu/ISO/`). Los multi-disco crean su `.m3u` solos (y el aviso te dice cuántos discos son).
8. **Sistemas incluidos (18)**: NES · SNES · GB · GBC · GBA · N64 · Mega Drive · Mega CD · 32X · PSX · Neo Geo · CPS-1 · CPS-2 · CPS-3 · FBNeo · OpenBOR · **PSP** · **Dreamcast** (~2.200 juegos).

---

## 🎮 PARTE 7 — PSP (Adrenaline: NATIVO)

La Vita lleva el chip de PSP dentro: Adrenaline lo usa directamente. Compatibilidad prácticamente total.

1. Si no lo has hecho: abre **Adrenaline** una vez → **X** (baja el firmware solo, ~1 min). *(Plan B sin internet: copia `661.PBP` a `ux0:/app/PSPEMUCFW/661.PBP` y abre Adrenaline.)*
2. En **RetroXam → PSP**: elige un juego → X. Se descarga a `ux0:/pspemu/ISO/` solo.
3. **Abrir directo ("1 toque", opcional)**: sigue `PSP_1toque\LEEME` (instala AdrenalineBubbleManager — pone los módulos sola — e instala `AdrenalineLauncher.vpk`). Con eso, X en RetroXam abre el juego **directo, sin menús**.
4. Sin el extra: RetroXam abre **Adrenaline** y eliges el juego en **Game → Memory Stick** (están todos en `ux0:/pspemu/ISO/`).
5. A mano también puedes copiar tus propios `.iso`/`.cso` a `ux0:/pspemu/ISO/` y aparecerán en Adrenaline.

> Los juegos PSP pesan ~1,5 GB de media y son **216 GB** la lista completa: baja solo los que quieras (el launcher te avisa del tamaño).

---

## 🕹️ PARTE 8 — Dreamcast (Flycast, experimental)

1. En **RetroXam → Dreamcast**: elige un juego → X. Se descarga y **arranca directo** con Flycast.
2. La lista incluye **solo los juegos compatibles** con Flycast Vita (79, con nivel documentado: 32 fluidos / 43 jugables / 4 justos).
3. Los multidisco (Resident Evil CV, Skies of Arcadia) bajan todos los discos y crean su `.m3u`.
4. Es **experimental** en la Vita (~50%): empieza por los 2D, fighting y carreras ligeras. Si un juego va con tirones, no es tu Vita — es el emulador.

---

## 🔌 El PUENTE por PC (para redes que bloquean archive.org)

Tu red puede no dejar a la Vita conectar con archive.org (es lo que te pasaba). El **puente** lo resuelve: la Vita le pide el juego a tu **PC/Mac**, y él (que sí llega) hace de espejo.

- **Ya está montado y es automático**: el launcher prueba en orden el **Mac Mini** (siempre encendido), el **PC** y el **acceso público** del Mac. No hay que configurar nada.
- **Requisito**: que el Mac o el PC estén encendidos.
- Solo si quieres **cambiarlo**: **Ajustes → Puentes del PC/Mac**, o el archivo `ux0:/data/retroxam/puente.txt`.
- Comprobar: **SELECT → START** → debe poner `PC OK`.
- Registros: PC `C:\Users\XAM-PC\RetroXamTools\puente.log` · Mac `~/RetroXam/puente.log`.

---

## 💻 PARTE 9 — Descargar en masa desde el PC (opcional)

> Para lotes grandes (50 de PSX, toda la SNES…). Herramientas en `C:\Users\XAM-PC\RetroXamTools`.

```bat
cd C:\Users\XAM-PC\RetroXamTools

:: Bajar (reanudable; --flat deja los archivos planos, como los quiere el launcher)
python descargar_vita.py --repo https://github.com/servixam-max/RetroXamVita --out D:\VitaROMs --flat --systems nes,snes,megadrive,psp,dreamcast

:: Subirlas a la Vita directo por FTP (VitaShell en modo FTP; IP en su pantalla, puerto 1337)
python descargar_vita.py --repo https://github.com/servixam-max/RetroXamVita --out D:\VitaROMs --flat --ftp 192.168.1.50:1337 --ftp-dir /ux0:/data/retroxam/roms
```

- Si lo vuelves a lanzar, **salta lo ya descargado/subido**. Con `--limit 20` bajas solo 20 por sistema.

**Tamaños orientativos:**

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
| **PSP** | **225** | **~217 GB** | **Dreamcast** | **79** | **~35 GB** |

> Total retro ≈ **124 GB** — no hace falta todo. Gracias al `--flat`, el launcher las marcará como **`+`** y las abrirá al instante.

---

## ✨ PARTE 10 — Toques finales

- **RetroArch**: no hace falta tocar nada — el launcher le pasa el core correcto y los ajustes se guardan solos. *(Tu config de bezels/shaders la mantiene la v2.4 sola.)*
- **DaedalusX64**: no todos los juegos de N64 van finos en la Vita (es normal). También puedes meter ROMs a mano en `ux0:/data/DaedalusX64/roms/`.
- **OpenBOR**: los `.pak` se copian solos a `ux0:/data/openbor/paks/`.
- **Mandos**: la Vita usa sus controles; en RetroArch puedes reasignar en Settings → Input.

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
| **PSP** | **Adrenaline** (nativo) | — |
| **Dreamcast** | **Flycast** (experimental) | — |

---

## 🔧 Problemas típicos

| Problema | Solución |
|---|---|
| "No hay juegos cargados" | Sin WiFi o listas sin bajar: activa WiFi y **SELECT → Actualizar listas** |
| Un juego no arranca | Bórralo de su carpeta (mantén **Triángulo** en el launcher) y vuelve a descargarlo |
| Sin espacio | El launcher muestra el libre arriba; borra juegos o pon una microSD mayor |
| La burbuja no aparece | VitaShell → **△ → Refresh livearea** |
| Las descargas fallan | Que el Mac o el PC estén encendidos y SELECT → START diga `PC OK`. Diagnóstico: **Ajustes → Ver registro** |
| A veces la imagen sale **movida** (fuera del marco) | Con la v2.4 no debería pasar (auto-config). Si aún así: **Ajustes → Vídeo → Escalado** → "Relación de aspecto: Personalizada" + viewport de la tabla de la Parte 4 → guardar override del core |
| **PSP**: no arranca directo desde RetroXam | Es lo normal sin el extra: se abre Adrenaline y eliges el juego. Para el "1 toque": instala el extra de `PSP_1toque\LEEME` |
| **PSP**: un juego no aparece en Adrenaline | Debe estar en `ux0:/pspemu/ISO/` (el launcher lo pone ahí solo). Refresca con O → volver a entrar |
| Quiero otro tema o textos más grandes | **SELECT → Ajustes** → Tema / Texto (se guarda solo) |
| Quiero borrar juegos para hacer sitio | Mantén **Triángulo** sobre el juego y confirma con **X** |
| Error **0x8010113D** al instalar la VPK | Usa las VPKs actualizadas del kit (iconos 128×128 8-bit ya corregidos) |
| El launcher no ve la SD | Repasa la Parte 1 (YAMT + ux0 → SD2Vita + reinicio) |
| **Daedalus** da error **C2-12828-1** | Falta `libshacccg.suprx`: ejecuta **ShaRKBR33D** (kit), reinicia y comprueba `ur0:/data/libshacccg.suprx`. Comprueba también `ux0:/data/DaedalusX64/` |
| RetroArch no muestra **Shaders** en el menú | Necesitas la build **piglet** (viene en el kit; la "normal" no lo trae). Requisito: PIBConfig + ShaRKBR33D |
| Un juego sale **sin marco** (bezel) | El launcher lo configura solo; si no: abre RetroXam una vez (auto-config) o extrae `Config_RetroXam_Piglet.zip` en `ux0:/data/retroarch/` |

---

## 🖼️ EXTRA — Bezels estilo RetroXam (referencia)

Los marcos con el logo de cada consola y la seta 🍄 **se instalan solos con la v2.4**. Referencia:

- **Archivo**: `Config_RetroXam_Piglet.zip` (o `Bezels_RetroXam_Vita.zip` solo-marcos) → **X → Extract** en `ux0:/data/retroarch/`.
- Cobertura: NES, SNES, GB/GBC, GBA, Mega Drive/Mega CD, 32X, PSX, NeoGeo/Arcade y CPS-1/2. N64 (Daedalus) y OpenBOR no pasan por RetroArch: sin marco.
- ¿A mano? Con un juego abierto: RetroArch → Ajustes → Pantalla en pantalla → Overlay Preset → `retroxam/<sistema>.cfg` → Quick Menu → Overrides → **Save Core Override**.
- Vita 1000 (OLED): el arte es oscuro y estático; con brillo alto horas y horas podría quedar marca (mismo aviso que otros packs).

---

## 🌈 EXTRA 2 — Shaders (scanlines CRT / LCD) — referencia

- **La build piglet** (kit) + `PIBConfig` + `ShaRKBR33D` = menú **Shaders** activo dentro de RetroArch.
- **A mano**: **Quick Menu → Shaders → Load Shader Preset** → `crt/crt-pi.glslp` (TV) o `lcd/lcd3x.glslp` (Game Boy). Los pesados (crt-geom) van lentos: quédate con `crt-pi`, `lcd3x` o `sharp-bilinear-simple`. Fija el que te guste con **Save Core Override**.
- **La v2.4 ya deja elegidos los mejores por core** (CRT para consolas de TV, LCD para GB/GBC, nitidez para GBA). No hay que tocar nada.

---

*RetroXam Vita — launcher v2.4 · 18 sistemas · ~2.200 juegos · RetroArch (piglet) + DaedalusX64 + OpenBOR + Adrenaline + Flycast*
*Listas: `github.com/servixam-max/RetroXamVita` · Carátulas: `github.com/servixam-max/RetroXamVitaCovers`*
