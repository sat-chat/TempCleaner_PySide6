# TempCleaner (Modern UI - PySide6)

A modern GUI wrapper for temporary-file cleaning on Windows. Built with Python + PySide6.
This repository contains a ready-to-build PySide6 app, resources (icon), and PyInstaller build instructions.

## What's included
- `main.py` - PySide6 GUI app (main entrypoint)
- `requirements.txt` - Py dependencies (PySide6, pyinstaller)
- `resources/icon.png`, `resources/icon.ico` - app icon (replace if you want a custom icon)
- `README.md`, `.gitignore`, `LICENSE`

## Build (create single-file EXE)
1. Create and activate a Python virtualenv (recommended):
   ```bash
   python -m venv venv
   venv\Scripts\activate
   ```
2. Install requirements:
   ```bash
   pip install -r requirements.txt
   ```
3. Build with PyInstaller (use the ico in resources):
   ```bash
   pyinstaller --onefile --noconsole --name TempCleaner --icon=resources/icon.ico main.py
   ```
4. The single EXE will be in `dist\TempCleaner.exe`.

## Notes on icon
- `resources/icon.svg` and `resources/icon.png` are included. Windows uses `.ico` — we've included `resources/icon.ico` if Pillow was available.
- If you want a custom icon, replace `resources/icon.png` and generate an `.ico` using ImageMagick or an online converter, or use Pillow locally.

## Usage
Run `main.py` directly with Python or run the compiled EXE.
The app supports dry-run (safe default) and will request elevation if needed for admin-only actions (Windows Temp, Recycle Bin).

## License
MIT
