# BIP 39 Mnemonic Dot Map Generator

A single-file web application that generates OneKey-style visual dot maps for BIP 39 mnemonic phrases.
## 🌐 Live Demo

## https://arg9244.github.io/bip39-dotmap/

## ✨ Features

- **OneKey-Style Visualization** - Each word encoded as 12 dots representing binary bits
- **Flexible Input** - Accept any number of BIP 39 words (no hard limit)
- **Real-time Validation** - Instant feedback on valid/invalid BIP 39 words
- **Interactive Tooltips** - Hover to see binary breakdown and calculations
- **Multiple Color Schemes** - Default (B&W), Dark mode, Light mode
- **Export Options** - Download as PNG image or PDF document
- **Fully Self-Contained** - Single HTML file, no server required
- **No External Data Collection** - Everything runs locally in your browser

## 📖 How It Works

### The Dot Map System

Each BIP 39 word has an index from 0 to 2047. This index is converted to 12 dots, where each dot position represents a power of 2:

| Dot 1 | Dot 2 | Dot 3 | Dot 4 | Dot 5 | Dot 6 | Dot 7 | Dot 8 | Dot 9 | Dot 10 | Dot 11 | Dot 12 |
|-------|-------|-------|-------|-------|-------|-------|-------|-------|--------|--------|--------|
| 2048  | 1024  | 512   | 256   | 128   | 64    | 32    | 16    | 8     | 4      | 2      | 1      |

- **Filled dot (●)** = That power of 2 is included in the sum
- **Empty dot (○)** = That power of 2 is not included

### Example

Word: "abandon" (index 0)
```
○ ○ ○ ○ ○ ○ ○ ○ ○ ○ ○ ○  = 0
```

Word: "ability" (index 1024)
```
○ ● ○ ○ ○ ○ ○ ○ ○ ○ ○ ○  = 1024
```

Word: "chunk" (index 1337 = 1024 + 256 + 32 + 16 + 8 + 1)
```
○ ● ○ ● ○ ○ ● ● ● ○ ○ ●  = 1024 + 256 + 32 + 16 + 8 + 1 = 1337
```

## 🚀 Usage

1. Open `bip39-dotmap.html` in any modern web browser
2. Enter your mnemonic phrase or click "Generate Random" for a demo
3. View the interactive dot map visualization
4. Export as PNG or PDF for backup
## 🔒 Privacy & Security

- **100% Client-Side** - All processing happens in your browser
- **No Data Transmission** - Your mnemonic never leaves your device
- **No Cookies/Tracking** - No analytics or tracking scripts
- **Open Source** - Full source code visible in the HTML file

⚠️ **Warning**: This tool is for educational and visualization purposes only. Never share your actual cryptocurrency mnemonic phrases. Random generated mnemonics are for demonstration only.

## 🛠️ Technical Details

- **BIP 39 Standard** - Uses the official 2048-word BIP 39 wordlist
- **Canvas API** - For rendering the dot map visualization
- **jsPDF** - For PDF generation (loaded from CDN)
- **No Dependencies** - Everything else is embedded

## 📋 Browser Support

- Chrome/Edge (recommended)
- Firefox
- Safari
- Any modern browser with Canvas and ES 6 support

## 📄 License

MIT License - Feel free to use, modify, and distribute.

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest features
- Submit pull requests

---

**Disclaimer**: This is an unofficial tool for educational purposes. Use at your own risk. Always verify your backup methods and never share your real mnemonic phrases.
