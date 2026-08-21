# PeakML

A local-first desktop app for preparing data. Open a file — or a folder of
documents — change it by clicking and typing, and every change lands in a
visible recipe of steps. Save the recipe, version it, point it at next month's
export, and take it away as runnable Python.

No network calls. No telemetry. No model in the product — the judgement it
offers is deterministic profiling.

**This repository holds downloads only.** PeakML's source is not public.

---

## Download 0.1.0

| Platform | File |
| --- | --- |
| **macOS** — Apple Silicon (M1 and later) | [`PeakML-0.1.0-mac-arm64.dmg`](https://github.com/Orion-AC/PeakML-releases/releases/download/v0.1.0/PeakML-0.1.0-mac-arm64.dmg) |
| **macOS** — Intel | [`PeakML-0.1.0-mac-x64.dmg`](https://github.com/Orion-AC/PeakML-releases/releases/download/v0.1.0/PeakML-0.1.0-mac-x64.dmg) |
| **Windows** — x64 | [`PeakML-0.1.0-win-x64.exe`](https://github.com/Orion-AC/PeakML-releases/releases/download/v0.1.0/PeakML-0.1.0-win-x64.exe) |

**[All releases →](https://github.com/Orion-AC/PeakML-releases/releases)**

Not sure which Mac you have? Click the Apple menu ▸ **About This Mac**. A chip
named *Apple M1*, *M2*, *M3* or *M4* means Apple Silicon; one named *Intel*
means Intel.

### Requirements

- **macOS 11 Big Sur** or later, or **Windows 10** or later, 64-bit.
- About **1 GB** of disk space. The installers are large because PeakML ships
  its own Python runtime — pandas, numpy, scipy, scikit-learn and pyarrow are
  inside the app, so nothing needs to be installed alongside it.

---

## Installing

These builds are **not code-signed yet**, so both systems will warn you the
first time. The warning is about the absence of a paid certificate, not about
anything found in the app.

### macOS

Open the `.dmg` and drag PeakML to Applications. Then, the first time only:

1. Open Applications in Finder.
2. **Right-click** PeakML and choose **Open** — double-clicking will not work
   yet, and will offer only *Move to Trash*.
3. Click **Open** in the dialog.

macOS remembers the choice; afterwards it launches normally.

If you see *"PeakML is damaged and can't be opened"*, macOS has quarantined the
download. Clear the flag:

```sh
xattr -d com.apple.quarantine /Applications/PeakML.app
```

### Windows

Run the `.exe`. When SmartScreen appears, click **More info**, then
**Run anyway**. The installer lets you choose where PeakML goes.

---

## Verifying your download

Checksums for every file are attached to each release as `SHA256SUMS.txt`.

```sh
# macOS / Linux
shasum -a 256 -c SHA256SUMS.txt

# Windows PowerShell
Get-FileHash .\PeakML-0.1.0-win-x64.exe -Algorithm SHA256
```

---

## What PeakML does

**Every mutation becomes a recorded step.** Typed cells, pastes, fills, row and
column deletes, sorts, filters, replaces, and all 46 statistical transforms land
in the Applied Steps panel. The grid is always recomputed from the original file
through the ordered steps, so nothing changes invisibly and everything is
reversible.

- **Columns are typed and homogeneous.** An edit is validated against the
  column's type and refused if it does not fit — deliberately unlike a raw
  spreadsheet.
- **Fitted transforms stay leakage-safe.** Scalers and encoders learn their
  parameters from the fitting set and reapply them; the status bar always says
  which data that is.
- **The recipe outlives the file.** It is a document with an id, a version, a
  history and a diff, and it can be pointed at data it was never written on.
- **Recipes export as runnable Python.**

### What PeakML is not

- **Not a spreadsheet.** An edit that does not fit a column's type is refused,
  not accepted as text.
- **Not a notebook.** There is no free-form code cell.
- **Not a modelling tool.** It prepares data and stops.
- **Not a database.** Everything is held in memory. A few million rows is
  comfortable; a hundred million is not.

---

## Reporting a problem

Open an issue on this repository. Include your operating system, the PeakML
version, and what you did before it went wrong.

---

© 2026 Orionac Private Limited.
