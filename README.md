# NAA.K.T. Generator for Revit

[![pyRevit](https://img.shields.io/badge/pyRevit-4.8+-blue.svg)](https://github.com/eirannejad/pyRevit)
[![Revit](https://img.shields.io/badge/Revit-2021--2025-orange.svg)](https://www.autodesk.com/products/revit)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Language](https://img.shields.io/badge/Language-Dutch-yellow.svg)](#)

A pyRevit extension for generating standardized material names in Autodesk Revit, following the **NAA.K.T.** convention (Naam-Attribuut-Kenmerk-Toepassing).

![NAA.K.T. Generator Screenshot](docs/screenshot.png)

## 🎯 Purpose

In BIM projects, consistent material naming is crucial for:
- **Schedules & quantities** - reliable filtering and grouping
- **Material libraries** - organized, searchable databases
- **Model exchange** - unambiguous material identification
- **Team collaboration** - everyone uses the same naming logic

The NAA.K.T. standard provides a hierarchical naming structure that is both human-readable and machine-parseable.

## 📐 NAA.K.T. Format

```
naam_kenmerk_toepassing_[eigen-invulling]
```

| Position | Dutch | Description | Examples |
|----------|-------|-------------|----------|
| 1 | **Naam** | Material family/group | beton, hout, isolatie, metaal |
| 2 | **Kenmerk** | Specific type/variant | gewapend, vuren, pir, staal |
| 3 | **Toepassing** | Form/application | prefab, profiel, plaat, buis |
| 4 | **Eigen** | Custom suffix (optional) | C30/37, 100mm, RAL9010 |

### Examples
```
beton_gewapend_prefab_C30/37
isolatie_pir_plaat_100mm
hout_eiken_profiel_50x100
metaal_staal_buis_koker60x60
```

## ✨ Features

- **WPF Interface** - Modern tabbed UI with pattern & color configuration
- **Extensible Database** - Add custom names, properties, and applications on-the-fly
- **Material Creation** - Directly create Revit materials with configured patterns/colors
- **Clipboard Copy** - Quick copy generated names for use elsewhere
- **Smart Matching** - Finds similar existing materials as duplication source
- **Dutch Building Industry** - Pre-configured with common Dutch construction materials

## 📦 Installation

### Option 1: Full Extension (Recommended)
Copy the `3BM_Bouwkunde.extension` folder to your pyRevit extensions directory:
```
%APPDATA%\pyRevit\Extensions\
```

### Option 2: Standalone Tool
Copy just the `NAAKTGenerator.pushbutton` folder into any existing pyRevit extension panel.

### Requirements
- Autodesk Revit 2021 or newer
- [pyRevit](https://github.com/eirannejad/pyRevit) 4.8 or newer

## 🚀 Usage

1. Open Revit with a project or family document
2. Navigate to **3BM Bouwkunde** tab → **Materialen** panel → **NAA.K.T.**
3. **Tab 1 - NAA.K.T. Naam:**
   - Select a **Naam** (material group)
   - Select a **Kenmerk** (characteristic)
   - Select a **Toepassing** (application)
   - Optionally add custom suffix
4. **Tab 2 - Pattern & Kleur:**
   - Configure surface pattern and colors
   - Configure cut pattern and colors
5. Click **Kopieer** to copy the name, or **Maak Materiaal** to create it in Revit

## 📁 File Structure

```
NAAKTGenerator.pushbutton/
├── script.py           # Main Python script
├── UI.xaml             # WPF interface definition
├── bundle.yaml         # pyRevit button configuration
└── icon.png            # Button icon (32x32)

lib/
├── bm_logger.py        # Logging utility
└── naakt_data/
    ├── naakt_namen.json        # Material groups
    ├── naakt_kenmerken.json    # Characteristics per group
    └── naakt_toepassingen.json # Applications per group
```

## 🔧 Customization

### Adding New Material Groups
Click the **+** button next to any dropdown, or edit the JSON files directly:

```json
// naakt_namen.json
{
  "namen": ["beton", "hout", "isolatie", "your_new_material"]
}
```

### Modifying Keywords for Smart Matching
Edit the `MATERIAAL_KEYWORDS` dictionary in `script.py` to improve material matching:

```python
MATERIAAL_KEYWORDS = {
    'beton': ['beton', 'concrete', 'cementgebonden'],
    'your_material': ['keyword1', 'keyword2'],
}
```

## 🏗️ Technical Details

- **Python**: IronPython 2.7 (pyRevit embedded)
- **UI Framework**: WPF (Windows Presentation Foundation)
- **Revit API**: Material creation, FillPattern management
- **Data Storage**: JSON files (human-editable)

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

## 👥 Credits

Developed by **3BM Bouwkunde** - A Dutch architectural/engineering firm specializing in building physics and structural design.

## 🤝 Contributing

Contributions welcome! Please feel free to submit issues or pull requests.

---

*Made with ❤️ for the Dutch AEC industry*
