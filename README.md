# 🔒 Obama Steganography

Hide files inside images using LSB steganography. Runs entirely in your browser.

![Obama Steganography](https://img.shields.io/badge/steganography-LSB-blue) ![Client Side](https://img.shields.io/badge/processing-client--side-orange)

## Features

- Auto-scales image to fit any file size
- Optional password encryption (XOR cipher)
- 100% client-side - your files never leave your device
- Works offline
- Automatic compression

## Usage

### Encode (Hide a File)
1. Open `obama-encoder.html`
2. Select a file
3. Optionally enter a password
4. Click "Encode" and download the image

### Decode (Extract a File)
1. Open `obama-decoder.html`
2. Upload the encoded image
3. Enter password if used
4. Click "Decode" and download your file

## How It Works

Files are compressed, optionally encrypted, then hidden in the least significant bits of the image's RGB channels (3 bits per pixel). The Obama image scales automatically to fit your data.

## Limitations

- Don't convert the encoded PNG to JPEG (will destroy data)
- XOR encryption is basic protection, not cryptographically secure
- LSB steganography is detectable with analysis tools

## License

MIT License

---

**Disclaimer**: For educational purposes only.
