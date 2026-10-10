# RetroXamVita

**Lista curada para PS Vita** — 18 sistemas, ~2.200 juegos, en formato JSONL.

Sistemas que la Vita emula bien con RetroArch + apps propias: NES, SNES, GB,
GBC, GBA, N64, Mega Drive, Mega CD, 32X, PSX, Neo Geo, CPS1/2/3, FBNeo y
OpenBOR — más **PSP** (vía **Adrenaline**, nativo) y **Dreamcast** (vía
**Flycast**, solo juegos compatibles).

## Cómo se usa

**Opción A — RetroXam Launcher (recomendado):**
Instala el VPK `RetroXam.vpk` en la Vita y ábrelo: el launcher lee esta lista
desde GitHub, descarga el juego que elijas y abre RetroArch/DaedalusX64/OpenBOR
con él. Necesita RetroArch (cores), y opcionalmente DaedalusX64 y OpenBOR.
Para PSP hace falta Adrenaline; para Dreamcast, Flycast.

**Opción B — descargar en el PC:**
```bash
python descargar_vita.py --local C:\Users\XAM-PC\RetroXamVita --out D:\VitaROMs --systems nes,snes,psx --unzip
# con subida FTP directa a la Vita (VitaShell):
python descargar_vita.py --local ... --out D:\VitaROMs --ftp 192.168.1.50:1337 --ftp-dir /ux0:/data/retroarch/downloads
```

## Notas

- **psp.jsonl** (225 juegos): .iso/.cso para Adrenaline → `ux0:/pspemu/ISO/`.
- **dreamcast.jsonl** (79 juegos): solo Perfect/Playable en Flycast Vita (.chd;
  multidisco en .m3u).
- El resto de sistemas: listas para el launcher RetroXam (carátulas en
  `servixam-max/RetroXamVitaCovers`).

## Sistemas excluidos (la Vita no los emula bien)
PS2, PS3, Switch, Wii, WiiU, GameCube, Saturn, Naomi, Model 2/3, Atomiswave,
3DS, NDS, Xbox/360.
