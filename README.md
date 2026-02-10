# Custom Batocera Build – SM9550 (Odin 2 / Portal / Mini / Thor)

Custom Batocera image tailored for **Snapdragon SM8550** handhelds and consoles.

---

## ✅ Supported Devices

* **Odin 2**
* **Odin 2 Portal**
* **Odin 2 Mini**
* **Ayn Thor** *(SM8550 model only — not the SM8250 Lite variant)*

Tested with Rocknix ABL
See https://wiki.batocera.org/hardware:ayn for bootloader 

---

## 🎮 Included Emulators & Systems

### PlayStation 2 — AetherSX2

* Pre‑configured profiles included
* Configs integrated into **EmulationStation**
* Optimized per‑device defaults

⚠️ **Important:**
Gamepad mapping must be performed manually:

* Launch `aethersx2` via **CLI**
* Do **NOT** launch from **F1 → PCManFM**
* ES Python launchers modify SDL mappings

---

### Nintendo Wii U — Cemu

* Updated to recent working builds
* Stability improvements verified

**Testing note:**

* *Mario Kart 8* no longer crashes after first race (confirmed in testing)

---

### PlayStation 3 — RPCS3

* Enabled and integrated
* Runs within Box64 translation layer

---

### PlayStation Vita — Vita3K

* Fully enabled
* ES integrated

---

### Nintendo Switch Emulators

Included:

* **Citron**
* **Eden**
* **Ryujinx**

⚠️ **Eden Controller Mapping Note:**
Same behavior as AetherSX2:

* Must launch via **CLI** for initial gamepad mapping
* Avoid F1/PCManFM launch
* ES launcher alters SDL input enumeration

---

## 🪟 Windows / PC Compatibility Layer

### Box64 + Wine Stack

Enabled components:

* Box64 userspace translation
* Batocera Wine system integration
* Proton Runner (recommended)

Supported package formats:

* `.wtgz`
* `.wsquashfs`

These launch directly through the Batocera Windows system.

---

## 🧩 Flatpak Support

* Fully enabled
* CLI usage recommended
* **Flathub remote supported**

### Add Flathub

```bash
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

### Example Install

```bash
flatpak install flathub org.mozilla.firefox
flatpak run org.mozilla.firefox
```

Flatpak integration is provided for advanced users who want desktop apps, tools, or experimental packages alongside Batocera.

---

## 🖥️ Display Server / Desktop Stack

### Graphics & Kernel Base

* **Mesa:** 25.3.5
* **Linux Kernel:** 6.18.9

Optimized for modern Adreno GPU support, Wayland stability, and translation layers (Box64 / Wine / RPCS3).

---

* **Wayland** based session
* **Labwc** compositor

Optimized for handheld GPU/driver stack and low-overhead UI navigation.

⚠️ **Permission Caveat (XWayland Apps):**

Labwc may introduce permission or launch issues with some XWayland applications, particularly:

* Wine / Proton titles
* Legacy SDL/X11 apps
* Certain Flatpak desktop programs

If problems occur, test under alternative compositors or X11 environments to rule out Wayland permission constraints.

---

## 🖥️ Display Server / Desktop Stack

* **Wayland** based session
* **Labwc** compositor

Optimized for handheld GPU/driver stack and low‑overhead UI navigation.

---

## ⚠️ Input Mapping Caveat

Emulators affected:

* AetherSX2
* Eden

Issue:

EmulationStation Python launchers modify SDL controller mappings, which can:

* Break detection
* Mis‑order inputs
* Prevent correct binding

### ✔ Recommended Setup Procedure

1. Launch emulator from CLI:

   ```bash
   aethersx2
   ```

   or

   ```bash
   eden
   ```

2. Configure controller mapping

3. Save profile

4. Exit emulator

5. Launch normally from EmulationStation afterward

---

## 📦 Additional Notes

* Proton runner provides best compatibility for Wine titles
* Switch emulator performance varies per title
* RPCS3 compatibility depends heavily on SPU load & driver state
* Flatpak is CLI‑only by design in this build

---

## 🛠️ Target Audience

This image is intended for:

* Advanced users
* Developers
* Handheld performance tweakers
* Box64 / Wine experimenters

Not recommended for plug‑and‑play beginners.

---

## 📜 Disclaimer

This is a **custom community build**.

* Not affiliated with the official Batocera project
* Stability, performance, and compatibility may vary
* Provided as‑is without warranty

### ❗ Support Policy

**Do NOT request support from official Batocera developers for issues related to this build.**


Respect upstream developers’ time and support boundaries.

---

**Enjoy the build — and push the SM9550 to its limits.**
