# PingBrowser

**PingBrowser** is a minimal, encrypted-cookie-based GTK web browser using WebKit2. It features a custom title bar, basic navigation buttons, and a secure encrypted cookie manager to preserve session data across launches.

## Features

- 🌐 Load websites with WebKit2
- 🔐 Secure encrypted cookie storage using `cryptography.fernet`
- ⏪ Back and forward navigation
- 🏠 Home button (default: [vroby.ddns.net/main.php](https://vroby.ddns.net/main.php))
- 🔍 URL bar with manual entry
- 📁 Custom right-click context menu (open/copy/save links)
- 🗂️ Cookies are saved automatically when changed
- 🚪 Custom close, minimize, and maximize behavior
- 🧩 No default window decorations — uses a custom header and layout
- 📌 Tray icon support (placeholder ready)
- 📎 Copy-to-clipboard support
- 🐧 Linux-only (GTK 3, WebKit2, Python 3)

## Screenshot

![Screenshot Placeholder](https://via.placeholder.com/800x600?text=PingBrowser+Screenshot)

## Requirements

Make sure the following dependencies are installed:

- Python 3
- GTK 3
- WebKit2GTK 4.1
- PyGObject
- cryptography

On Debian/Ubuntu-based systems, you can install the requirements with:

```bash
sudo apt install python3-gi gir1.2-webkit2-4.1 gir1.2-gtk-3.0 python3-cryptography
```

Python packages:

```bash
pip install cryptography
```

## Usage

To run the browser:

```bash
python3 pingbrowser.py
```

You can optionally provide a URL as the first argument:

```bash
python3 pingbrowser.py https://example.com
```

## Cookie Encryption

All cookies are stored securely using [Fernet](https://cryptography.io/en/latest/fernet/), an authenticated symmetric encryption scheme.

- Encrypted cookie file: `~/.cookies/cookies.enc`
- Encryption key: `~/.cookies/key`

If no key is found, a new one is generated and stored securely.

## Custom Context Menu

When right-clicking a link:

- **Open Link** – loads the link in the current view
- **Save Link As…** – allows downloading the file
- **Copy Link** – copies the link to the clipboard

## Limitations

- Currently lacks tabs or multiple windows
- Not intended as a fully featured browser
- Designed for simplicity, prototyping, and educational purposes

## Development Notes

If the base64-encoded tray icon is not yet provided (`base64_icon` in `init_icon()`), it will be skipped silently with a debug message if `DEBUG = True`.

## License

MIT License
---

Feel free to fork, modify, or contribute!
