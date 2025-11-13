# WIFI QR Code Generator Extension

A simple, fast, and secure browser extension built with **Vue 3** and **Tailwind CSS** to generate a scannable QR code for easy WiFi network sharing.

**NOTE**: This extension is up on the google chorme store and can use it i would love if you make some improvement in this and tell me about.

[![Linkedin]](https://chromewebstore.google.com/detail/bepafkjkjgoplblekaijndbodjgcdfnh?utm_source=item-share-cb)

---

## 💡 Features

- **Instant QR Generation:** Converts SSID and Password into a standard WiFi configuration QR code (`WIFI:T:WPA;S:...;`).
- **Smooth UX:** Utilizes a custom Vue transition for a smooth slide between the input form and the generated QR code view.
- **Image Download:** Includes a button to download the generated QR code as a PNG file.
- **Modern Stack:** Built using Vue 3 (Composition API) and styled with Tailwind CSS.

---
## 📷 Images
![alt text](https://lh3.googleusercontent.com/Rlw8T7QrC9tS5NTRFCDbDw6JpkFnowaSQJw-dLBgmjtf4QtBgx9P_TWMAohhXrxhJhLFLIhZt6mBn4jcDIFoeJ_em3s=s1280-w1280-h800 "img")
![alt text](https://lh3.googleusercontent.com/jB8Bk-Fem6bk0gXVZcKImzSZY-s22h0lnBl9VGYCKOv1s1vO1nQXI7mm8EvcwEnKMR1a5zGkA4fJd1R-XcX-C4xY=s1280-w1280-h800 "img01")
![alt text](https://lh3.googleusercontent.com/HyqXBTMYH78x-sz0FBLccYUQ3nrA6DqyE6iRYuYz9nKVAxxO_3L9OHdwEyNM-_t6nvLCrezgAM9ceYPyCJBWqt8i2A=s1280-w1280-h800 "img02")
![alt text](https://lh3.googleusercontent.com/6F0GSUqd6Cigy3ttuDCg0Srt9QbV-gUPF00rcLxW1yMiJu2rTwuFz3C-NME7ZCWTt2O9y35tDeIk1YIM6t6SJNjtdjM=s1280-w1280-h800 "img03")
![alt text](https://lh3.googleusercontent.com/FpJi23WFrT8rrh8P4TCRKrqskw6xKJYeilMJhcKDGZXxWBhmPTR-A7GrxRi8kLCzh5q9pteDHhNyzIs_OyMEHV4ejg=s1280-w1280-h800 "img04")
---

## 💻 Tech Stack

| Technology    | Purpose                                       |
| ------------- | --------------------------------------------- |
| Vue 3         | Front-end framework (Composition API)         |
| Tailwind CSS  | Utility-first CSS framework for rapid styling |
| Node.js / npm | Package manager and runtime environment       |
| Vite          | Build tool and development server             |
| qrcode        | JavaScript library for generating QR codes    |

---

## 🚀 Setup & Installation

Follow these steps to get a local copy running on your development machine.

### Prerequisites

You need **Node.js** (which includes npm) installed.

```bash
node -v
npm -v
```

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/browser-Extension-WifiQrCode.git
cd browser-Extension-WifiQrCode
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Run in Development Mode

Run the development server. This command will watch your source files and automatically rebuild them on change. Keep this terminal window open.

```bash
npm run dev
# Or npm run watch, depending on your project configuration
```

### 4. Load as Unpacked Extension (Chrome/Edge/Brave)

1. Open your browser and navigate to the extensions page: chrome://extensions or edge://extensions.

2. Enable Developer mode using the toggle switch in the 3. upper-right corner.

3. Click the Load unpacked button.

4. Select the output folder of your build command (typically the dist folder).

The extension icon should now appear in your browser toolbar.

<hr/>

### ⚙️ Development Workflow

- When making changes to the code:

- Ensure your npm run dev process is running in the background.

- Save your source files (.vue, .js, etc.).

- The output files in the dist directory will be instantly updated.

- Go back to the browser's extensions page (chrome://extensions) and click the Reload (circular arrow) button on your extension tile to see the changes.

<hr/>

### 📂 Project Structure

```bash
├── dist/                     # Production ready build files
├── node_modules/             # Node dependencies
├── src/
│   ├── assets/               # CSS, Images, etc.
│   └── components/
│       └── WifiQrGenerator.vue # Main application component
├── public/                   # Static assets (e.g., manifest.json, icons)
├── package.json              # Project dependencies and scripts
└── README.md                 # This file
```

<hr/>

### 📄 License

Distributed under the MIT License. See LICENSE for more information.
