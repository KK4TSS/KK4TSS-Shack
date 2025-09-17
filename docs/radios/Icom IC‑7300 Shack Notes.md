# IC‑7300 My Shack Notes (KK4TSS)
---

## What I’m running
- **Radio**: Icom IC‑7300 (HF + 6 m only, up to 100 W)
- **Tuner**: **Internal ATU** (handles modest mismatches); still prefer resonant antennas
- **PC link**: Single USB cable → **CAT** (COM/tty) + **USB Audio CODEC**
- **Important**: **No VHF/UHF, no FM mode, no D‑STAR** on the 7300 (don’t plan for FM repeaters here)

> Digital rule: **USB‑D**, **no compression/EQ/NB/NR**, and **keep ALC from moving**.

---

## My baseline radio setup (one‑time)
- **USB driver** (Windows): Install Icom driver so both CAT and “USB Audio CODEC” appear.
- **CI‑V** (Menu → Set → Connectors → CI‑V)
  - **Baud**: **115200** (fast & reliable for me) — match software. 19200 also works.
  - **CI‑V Transceive**: **ON**
  - **CI‑V USB Echo Back**: **ON**
- **MODE SOURCES**
  - **DATA MOD = USB** (digital audio over USB)
  - **DATA OFF MOD = MIC** (normal SSB chain)
  - **USB MOD Level**: start ~**30–40%**; trim so **ALC just flickers** on TX data
  - **ACC/USB AF Output Level**: ~**50%** (so apps see healthy input)
- **Filters**
  - **SSB voice**: 2.4–2.9 kHz (taste)
  - **Digital**: **USB‑D** with ~3 kHz passband
- **Turn OFF for digital**: COMP, TX EQ, NR, NB

---

## WSJT‑X profile (works for me)
- **Rig**: *Icom IC‑7300*
- **CAT**: **115200** baud, **PTT via CAT**, Handshake **None**
- **Mode**: **Data/Pkt** (forces USB‑D)
- **Split**: **Rig** (cleaner TX placement)
- **Soundcard**: `USB Audio CODEC` in/out

**hamlib/rigctld I use**
```bash
# Linux/macOS example (adjust device as needed)
rigctld -m 307 -r /dev/ttyUSB0 -s 115200 -t 4532 -vvvv
# (Model 307 = IC‑7300)
```
WSJT‑X → Radio → *Network Server*: `127.0.0.1:4532`.

**Leveling checklist**
- OS playback to `USB Audio CODEC` ~50%
- Radio **USB MOD Level** → set so **ALC barely moves**
- Start ~**30 W** on HF/6 m; increase carefully only if antenna + duty cycle allow
- Disable OS sound “enhancements” everywhere

---

## Quick operating presets
### SSB voice (HF/6 m)
- Mode **USB/LSB** (not USB‑D)
- Light COMP if needed; watch ALC on peaks
- TX Monitor on for mic checks (short bursts)

### Digital FT8/FT4
- **USB‑D**, **DATA MOD = USB**
- ALC just flickering; no COMP/EQ/NB/NR
- Typical dial spots I use:  **FT8** → 3.573 • 7.074 • 10.136 • 14.074 • 18.100 • 21.074 • 24.915 • 28.074 • **50.313** MHz

---

## Memory cheatsheet (HF/6 m only)
> I keep voice vs. data groups separate and label clearly.

---

## CI‑V / USB reference (so I don’t forget)
| Setting | Value     | Why                     |
|--------:|:----------|:------------------------|
| Baud    | **115200**| Fast & stable           |
| Transceive | **ON** | Keeps software in sync  |
| USB Echo Back | **ON** | Helps hamlib behave |
| DATA MOD | **USB**  | Digital over USB        |
| DATA OFF MOD | **MIC** | Normal SSB chain   |
| USB MOD Level | **Trim to no ALC** | Clean TX on FT8/FT4 |

---

## Antenna & RF sanity
- Internal ATU handles small mismatches; use a proper external tuner for bigger ones
- Choke feedlines and the USB cable if RF sneaks into audio/CAT
- Keep coax away from USB where possible; avoid long parallel runs

---

## Spectrum scope tips (7300)
- Set **Reference Level** so average noise sits mid‑scope
- Use **ATT/Preamp** appropriately (preamp off when strong signals, on when bands are quiet)
- Narrow **SPAN** when hunting weak FT8 signals; return to wider view for band scan

---

## Backup & cloning
- Use the **SD card** to back up **settings/memories** and to log screens if needed
- Keep this README + any WSJT‑X screenshots/exports in the repo for repeatability

---

## When it bites me (quick checks)
- Accidentally in plain USB for FT8 (should be **USB‑D**) → fix and re‑level
- ALC pinned → back down app output, then USB MOD Level
- Windows swapped the default sound device → reselect `USB Audio CODEC`
- 7300 has **no FM/D‑STAR/VHF/UHF**

---

## License & disclaimer
These are my personal notes, “as‑is.” Verify band plans, power levels, and local rules. Text can be CC‑BY‑4.0; code snippets MIT. © KK4TSS.

---

## Change log
- **2025‑09‑16**: First cut of my IC‑7300 shack notes (voice + FT8/FT4).
