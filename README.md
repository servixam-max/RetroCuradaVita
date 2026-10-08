# RetroXamVita

**Lista curada para PS Vita** — 16 sistemas, ~1.900 juegos, en formato JSONL.

Solo sistemas que la Vita **puede emular bien** con RetroArch + apps propias
(**sin Adrenaline**): NES, SNES, GB, GBC, GBA, N64, Mega Drive, Mega CD, 32X,
PSX, Neo Geo, CPS1/2/3, FBNeo y OpenBOR.

## Cómo se usa

**Opción A — RetroXam Launcher (recomendado):**
Instala el VPK `RetroXam.vpk` en la Vita y ábrelo: el launcher lee esta lista
desde GitHub, descarga el juego que elijas y abre RetroArch/DaedalusX64/OpenBOR
con él. Necesita RetroArch (cores), y opcionalmente DaedalusX64 y OpenBOR.

**Opción B — descargar en el PC:**
```bash
python descargar_vita.py --local C:\Users\XAM-PC\RetroXamVita --out D:\VitaROMs --systems nes,snes,psx --unzip
# con subida FTP directa a la Vita (VitaShell):
python descargar_vita.py --local ... --out D:\VitaROMs --ftp 192.168.1.50:1337 --ftp-dir /ux0:/data/retroarch/downloads
```

## Sistemas excluidos (la Vita no los emula bien)
PS2, PS3, PSP (requiere Adrenaline), Switch, Wii, WiiU, GameCube, Dreamcast,
Saturn, Naomi, Model 2/3, Atomiswave, 3DS, NDS, Xbox/360.
