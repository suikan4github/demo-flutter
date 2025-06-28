# demo-flutter
Demonstration of flutter application, including packaging and automated releases.

[![CI/CD Pipeline](https://github.com/suikan4github/demo-flutter/actions/workflows/ci.yml/badge.svg)](https://github.com/suikan4github/demo-flutter/actions/workflows/ci.yml)
[![Deploy to GitHub Pages](https://github.com/suikan4github/demo-flutter/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/suikan4github/demo-flutter/actions/workflows/deploy-pages.yml)

## 🌐 Try it Online
**Live Demo**: [https://suikan4github.github.io/demo-flutter/](https://suikan4github.github.io/demo-flutter/)

## 📦 Download
Download the latest release for your platform:
- **Linux AppImage**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Universal Linux package
- **Linux .deb**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Ubuntu/Debian package
- **Linux tar.gz**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Archive format

### Installation Methods

**AppImage (Universal):**
```bash
chmod +x demo-flutter-v*.AppImage
./demo-flutter-v*.AppImage
```

**Debian Package (Ubuntu/Debian):**
```bash
sudo dpkg -i demo-flutter-v*-amd64.deb
sudo apt-get install -f  # Fix dependencies if needed
demo-flutter  # Run from anywhere
```

# Details
This repository contains a simple Flutter application that demonstrates basic functionality and packaging.

# Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/suikan4github/demo-flutter.git
   cd demo-flutter
   ```
2. Install dependencies:
   ```bash
   flutter pub get
   ```

## Build and run on Linux Desktop
3. Run the application:
   ```bash
   flutter run
   ```

## Build and run on Web
3. Run the application:
   ```bash
   flutter run -d web-server
   ```
Then, you will see output similar to the following:

   ```
    Launching lib/main.dart on Web Server in debug mode...
    Waiting for connection from debug service on Web Server...         11.9s
    lib/main.dart is being served at http://localhost:43075
    The web-server device requires the Dart Debug Chrome extension for debugging. Consider using the Chrome or Edge devices for an improved development workflow.

    Flutter run key commands.
    R Hot restart.
    h List all available interactive commands.
    d Detach (terminate "flutter run" but leave application running).
    c Clear the screen
    q Quit (terminate the application on the device).
   ```
Click the link to open the application in your web browser.


