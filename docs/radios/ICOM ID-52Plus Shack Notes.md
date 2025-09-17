# ID‑52 Plus — My Shack Notes (KK4TSS)
--

## What I’m running
- **Radio**: Icom **ID‑52** (U.S. version) — VHF/UHF handheld with **D‑STAR** and color screen
- **Bands/Modes**: 2 m & 70 cm • **FM** & **DV (D‑STAR)** • Dual‑watch
- **Power**: **BP‑272** pack (I carry a spare); I charge via **USB‑C** when convenient
- **Audio/Control**: Built‑in **Bluetooth** (headset/VS‑3) • **microSD** for memories/recordings
- **Use cases**: Local analog repeaters/simplex, hotspot, D‑STAR reflectors, travel “Near Repeater”

> Handheld habits: keep audio clean (mic just off to the side of my mouth), use time‑out timer, and label memories clearly.

---

## My baseline handheld setup (one‑time)
- **Set MYCALL**: e.g., `KK4TSS` (Menu → DV/D‑STAR → My Call Sign)
- **Clock/GPS**: GPS **ON** (helps “Near Repeater” and position in DV); set local time zone
- **DR memories**: Load a **curated** local list (I import via cloning/microSD; fewer = faster to use)
- **Bluetooth**: Pair headset (I like PTT on a VS‑3 style device when I use BT)
- **Battery care**: I top up with USB‑C at low rates; carry one spare for events
- **Recording**: microSD → enable **voice recorder** for nets/training (optional)

---

## Analog FM (how I set it up fast)
- **Mode**: FM (not DV)
- **CTCSS/DCS**: Match repeater; confirm **offset** (+/‑) and **step**
- **Mic**: Speak across the mic (not into it); keep audio steady
- **TOT**: Time‑Out Timer enabled for long nets
- **Simplex** I keep handy:
  - **146.520** (2 m calling)
  - **446.000** (70 cm calling)

> I save local repeaters with clear labels: `City • Call • Tone • Notes`.

---

## D‑STAR quick start (DR mode I actually use)
**Goal:** CQCQCQ local on a D‑STAR repeater or talk on a reflector/hotspot.

### Local D‑STAR repeater (simple CQCQCQ)
1. **DR mode** → choose the **repeater** from DR memories (or use **Near Repeater**)
2. **UR**: `CQCQCQ`
3. **PTT** and talk. That’s a local QSO through the gateway/repeater.

### Hotspot / Reflector linking (typical flow)
1. Select my **hotspot** node in DR (your RPT1/RPT2 should already point at the hotspot)
2. **UR command** to **link** (e.g., `REF030CL` to link module C)
3. After linked, set **UR** back to `CQCQCQ` and QSO
4. **Unlink** when done (e.g., `REF030 U`)

> Module letters: **A=23 cm**, **B=70 cm/440**, **C=2 m/144**; **G** is the gateway. Keep the right module in RPT1, and `...G` in RPT2.

**DV audio**: Keep input level reasonable; don’t shout into the mic. Give a second after PTT before speaking so headers make it.

---

## GPS & “Near Repeater”
- Turn **GPS ON** → *Near Repeater* helps me pick the right D‑STAR or analog machine while traveling
- I still prune the DR list so I’m not scrolling cities I’ll never use

---

## Bluetooth notes
- Pairs easily with headsets; I keep sidetone/levels conservative
- **PTT** is still on the radio unless I use a BT PTT accessory (e.g., **VS‑3**)
- For windy spots, a wired speaker‑mic often sounds better than BT

---

## microSD, cloning, and backups
- I keep a **microSD** in the radio: voice recordings, screen captures, and **settings/memories** backups
- I export/import my DR memories and regular channels so I can recover fast after resets
- This repo holds a simple text copy of my channel plan so I can edit on desktop

---

## Memory plan (starter)
> Keep analog vs DV grouped. Label with city/use. I only keep what I actually use.

| # | Band | Freq (MHz) | Mode | Tone/Notes        | Label                   |
|---:|:----:|-----------:|:-----|:------------------|:------------------------|
| 1  | 2 m  | 146.5200   | FM   | Simplex calling   | 2m Simplex              |
| 2  | 70 cm| 446.0000   | FM   | Simplex calling   | 70cm Simplex            |
| 10 | 2 m  | —          | DV   | DR: Local D‑STAR  | Local D‑STAR (CQCQCQ)   |
| 11 | 70 cm| —          | DV   | DR: My Hotspot    | HS Link (REF030C)       |
| 12 | 70 cm| —          | DV   | DR: My Hotspot    | HS Unlink               |

_Add your real local repeaters with call, tone, and offset — and the hotspot frequency you actually run._

---

## Quick operating checklists
**Analog net**
- FM mode, correct tone/offset, battery topped, antenna fully seated
- Speak across mic; keep transmissions concise

**D‑STAR net/reflector**
- DR memory selected, **UR=CQCQCQ** (after linking)
- Leave a beat after PTT; watch for double‑keying
- Unlink when done

---

## Troubleshooting I hit the most
- **No audio on DV**: Check **UR** (CQCQCQ vs link), **RPT1/RPT2** modules, hotspot up
- **Can’t key hotspot**: You’re in **FM**, not **DV**; or wrong band/module
- **Low/harsh audio**: Move mic slightly off‑axis; don’t cup the radio
- **Near Repeater empty**: GPS off or no lock; turn GPS on and wait

---

## License & disclaimer
My personal notes, “as‑is.” Verify local repeater data, rules, and hotspot policies. Text CC‑BY‑4.0; any code snippets MIT. © KK4TSS.

---

## Change log
- **2025‑09‑17**: First cut of my ID‑52 Plus shack notes (FM + D‑STAR, hotspot flow).
