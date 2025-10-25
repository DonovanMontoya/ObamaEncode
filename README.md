# 🔒 Obama Steganography

Hide files inside images using steganography. Simple, secure, and runs entirely in your browser.

![Obama Steganography](https://img.shields.io/badge/steganography-LSB-blue) ![No Dependencies](https://img.shields.io/badge/dependencies-none-green) ![Client Side](https://img.shields.io/badge/processing-client--side-orange)

## ✨ Features

- **No File Size Limits** - Image automatically scales to fit your data
- **Instant Encoding** - Obama image pre-loaded for zero wait time
- **100% Client-Side** - No server uploads, complete privacy
- **Offline Capable** - Works without internet connection
- **Simple LSB Steganography** - Uses least significant bit encoding
- **Automatic Compression** - Files are compressed before encoding

## 🚀 Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/obama-steganography.git
   cd obama-steganography
   ```

2. **Open in browser**
   ```bash
   # Just open index.html in your browser
   open index.html  # macOS
   start index.html # Windows
   xdg-open index.html # Linux
   ```

3. **Or visit the live demo**
   [https://yourusername.github.io/obama-steganography](https://yourusername.github.io/obama-steganography)

## 📖 Usage

### Encoding (Hiding a File)

1. Open `obama-encoder-tested.html`
2. Click "Choose File" and select any file
3. Click "Encode"
4. Download the generated Obama image with your file hidden inside

### Decoding (Extracting a File)

1. Open `obama-decoder-tested.html`
2. Upload the encoded Obama image
3. Click "Decode"
4. Download your original file

## 🔧 How It Works

### Encoding Process
1. File is read as binary data
2. Metadata (filename, size) is added
3. Data is compressed using pako (zlib)
4. Length prefix (4 bytes) is prepended
5. Each bit is stored in LSB of R, G, or B channels
6. Obama image is scaled up if needed to fit all data
7. Result is saved as PNG

### Decoding Process
1. Encoded image is loaded
2. Length is read from first 32 bits
3. Data bits are extracted from RGB LSBs
4. Data is decompressed
5. Metadata is parsed
6. Original file is reconstructed

### Technical Details

- **Encoding**: 3 bits per pixel (1 bit each in R, G, B channels)
- **Capacity**: ~375 bytes per 1000 pixels
- **Compression**: Deflate/Zlib via pako.js
- **Format**: Output as PNG to preserve LSB data

## 📁 File Structure

```
obama-steganography/
├── index.html                    # Landing page
├── obama-encoder-tested.html     # Encoder tool
├── obama-decoder-tested.html     # Decoder tool
└── README.md                     # This file
```

## 🛠️ Technologies

- **Pure JavaScript** - No frameworks
- **HTML5 Canvas API** - Image manipulation
- **pako.js** - Data compression (loaded from CDN)
- **Web Crypto API** - (Future: encryption support)

## 🔒 Privacy & Security

- ✅ **100% client-side processing** - Your files never leave your computer
- ✅ **No tracking** - No analytics, no cookies
- ✅ **No servers** - Everything runs in your browser
- ✅ **Open source** - Audit the code yourself

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs
- Suggest features
- Submit pull requests
- Improve documentation

## 📝 License

MIT License - feel free to use this for any purpose.

## ⚠️ Limitations

- **Lossy formats**: Don't re-compress the encoded PNG as JPEG (will destroy hidden data)
- **Large files**: Browser memory limits may affect very large files (>100MB)
- **Detection**: LSB steganography is detectable with steganalysis tools

## 🎯 Future Enhancements

- [ ] Optional password encryption
- [ ] Multiple cover image options
- [ ] Drag & drop file upload
- [ ] Progress bars for large files
- [ ] Advanced LSB algorithms
- [ ] Mobile app version

## 🙏 Credits

- Obama image: Public domain
- Compression: [pako.js](https://github.com/nodeca/pako)

---

**Disclaimer**: This tool is for educational purposes. Always respect copyright and privacy laws.
