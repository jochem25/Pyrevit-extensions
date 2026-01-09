# OpenAEC - pyRevit Extensions

[![pyRevit](https://img.shields.io/badge/pyRevit-4.8+-blue.svg)](https://github.com/eirannejad/pyRevit)
[![Revit](https://img.shields.io/badge/Revit-2021--2025-orange.svg)](https://www.autodesk.com/products/revit)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Open-source pyRevit tools for the AEC (Architecture, Engineering, Construction) industry.

## 🚀 Installation

1. **Download** this repository (Code → Download ZIP) or clone it
2. **Copy** the `OpenAEC.extension` folder to:
   ```
   %APPDATA%\pyRevit\Extensions\
   ```
3. **Reload** pyRevit (pyRevit tab → Reload)

That's it! You'll see a new **OpenAEC** tab in your Revit ribbon.

## 🛠️ Available Tools

### Materialen Panel

| Tool | Description |
|------|-------------|
| **NAA.K.T. Generator** | Generate standardized material names following the NAA.K.T. convention (Naam-Attribuut-Kenmerk-Toepassing). Create materials directly in Revit with custom patterns and colors. |

## 📁 Repository Structure

```
Pyrevit-extensions/
├── README.md
├── LICENSE
└── OpenAEC.extension/           ← Copy this folder to pyRevit Extensions
    ├── extension.json
    ├── lib/
    │   ├── bm_logger.py
    │   └── naakt_data/
    └── OpenAEC.tab/
        └── Materialen.panel/
            └── NAAKTGenerator.pushbutton/
```

## 📐 NAA.K.T. Material Naming Standard

The NAA.K.T. standard provides consistent material naming:

```
naam_kenmerk_toepassing_[eigen-invulling]
```

| Position | Description | Examples |
|----------|-------------|----------|
| **Naam** | Material family | beton, hout, isolatie |
| **Kenmerk** | Specific type | gewapend, vuren, pir |
| **Toepassing** | Form/application | prefab, profiel, plaat |
| **Eigen** | Custom suffix | C30/37, 100mm |

**Examples:**
- `beton_gewapend_prefab_C30/37`
- `isolatie_pir_plaat_100mm`
- `hout_eiken_profiel_50x100`

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Submit issues for bugs or feature requests
- Fork and create pull requests
- Add new tools to the extension

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

## 👥 Credits

Initiated by **3BM Bouwkunde** - Open for community contributions.

---

*Made with ❤️ for the AEC industry*
