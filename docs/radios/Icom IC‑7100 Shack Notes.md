# IC‑7100 Shack Notes (KK4TSS)
---

## What I’m running
- **Radio**: Icom IC‑7100 (HF/6 m/2 m/70 cm)
- **Power**: 13.8 VDC @ ≥25–30 A for 100 W HF
- **PC link**: Single USB to PC/Mac/Linux → gives **CAT** (COM/tty) + **USB Audio CODEC**
- **Antennas**: Separate HF and VHF/UHF lines; chokes where needed
- **Tuner**: None inside — use resonant antennas or an external ATU rated for 100 W

> Rule of thumb for digital: **No compression, no EQ, no NB/NR, no ALC movement**.

---

## My baseline radio setup (one‑time)
- **USB driver** (Windows): Install Icom driver so I get CAT + USB Audio CODEC.
- **CI‑V**
  - Baud **19200** (match software)
  - Transceive **ON**
  - USB Echo Back **ON**
- **MODE SOURCES**
  - **DATA MOD = USB** (digital via USB)
  - **DATA OFF MOD = MIC** (normal SSB)
  - **USB MOD Level ~30–40%** to start; I trim so ALC just flickers on TX data.
- **SSB filters**: Voice 2.4–2.9 kHz; Digital uses **USB‑D** (wide ~3 kHz).

---

## Daily presets I actually use
### SSB voice (HF)
- Mode **USB/LSB** (not USB‑D)
- Light COMP only if needed; watch ALC on peaks
- Keep mic technique consistent

### Digital FT8/FT4
- Mode **USB‑D**, **DATA MOD = USB**
- **ALC barely flickers**; reduce app output first, then USB MOD Level
- Start ~**30 W** on HF; increase only if antenna + duty cycle can take it

### VHF/UHF FM
- Correct antenna port, squelch set, tone/offset per repeater

### D‑STAR (DR)
- **MYCALL** set (KK4TSS)
- **UR** = `CQCQCQ` for local
- Use DR memories for local repeaters/reflectors; confirm gateway suffixes

---

## WSJT‑X profile (works for me)
- **Rig**: *Icom IC‑7100*
- **CAT**: 19200 baud, **PTT via CAT**, Handshake **None**
- **Mode**: **Data/Pkt** (forces USB‑D)
- **Split**: **Rig** (cleaner TX placement)
- **Soundcard**: `USB Audio CODEC` in/out

**hamlib/rigctld I use**
```bash
# Linux/macOS example (adjust device as needed)
rigctld -m 370 -r /dev/ttyUSB0 -s 19200 -t 4532 -vvvv
# (Model 370 = IC‑7100)
```
WSJT‑X → Radio → *Network Server*: `127.0.0.1:4532`.

**Leveling**
- OS playback to `USB Audio CODEC` ~50%
- USB MOD Level so ALC just starts to move
- Keep TX audio clean; no OS “enhancements”

---

## Quick memory cheatsheet (starter)
> I keep voice vs. data channels separate and label clearly.

---

## CI‑V / USB reference (so I don’t forget)
| Setting | Value | Why |
|---|---|---|
| CI‑V Baud | **19200** | Stable; easy across apps |
| CI‑V Transceive | **ON** | Keeps software in sync |
| CI‑V USB Echo Back | **ON** | Helps hamlib behave |
| DATA MOD | **USB** | Digital audio over USB |
| DATA OFF MOD | **MIC** | Normal SSB chain |
| USB MOD Level | **Trim to no ALC** | Clean TX on FT8/FT4 |

---

## When it bites me (things I check)
- Wrong mode (doing FT8 in plain USB instead of **USB‑D**)
- ALC slammed → back down app output and USB MOD Level
- Split off in WSJT‑X on crowded bands
- Windows decided to “enhance” the USB audio (turn **all** that off)
- Driver gremlins → replug USB after installing Icom driver so CAT + Audio both show up
- D‑STAR mic gain/compression set too hot (sounds rough); keep conservative

---

## Antenna & RF sanity
- No internal tuner — resonant antennas or an external ATU
- Choke feedlines + the USB if RF gets into audio/CAT
- Keep HF and VHF/UHF feedlines separated; avoid long parallel runs

---

## License & disclaimer
These are my personal notes, “as‑is.” Verify band plans, power levels, and local rules. Text CC‑BY‑4.0; any code snippets MIT. © KK4TSS.

---

## Change log
- **2025‑09‑16**: First cut of my IC‑7100 shack notes (voice, FT8/FT4, D‑STAR).

