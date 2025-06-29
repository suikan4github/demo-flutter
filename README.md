# demo-flutter
Demonstration of flutter application, including packaging and automated releases.

[![CI/CD Pipeline](https://github.com/suikan4github/demo-flutter/actions/workflows/ci.yml/badge.svg)](https://github.com/suikan4github/demo-flutter/actions/workflows/ci.yml)
[![Deploy to GitHub Pages](https://github.com/suikan4github/demo-flutter/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/suikan4github/demo-flutter/actions/workflows/deploy-pages.yml)

## 🌐 Try it Online
**Live Demo**: [https://suikan4github.github.io/demo-flutter/](https://suikan4github.github.io/demo-flutter/)

## 📦 Download
Download the latest release for your platform:

### Linux Packages
- **Linux AppImage**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Universal Linux package (x86_64/amd64)
- **Linux .deb**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Ubuntu/Debian package (amd64)
- **Linux .rpm**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Red Hat/Fedora/CentOS package (x86_64)
- **Linux .snap**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Universal Snap package (amd64)
- **Linux tar.gz**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Archive format (x86_64/amd64)

### Windows Packages
- **Windows ZIP**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Portable Windows application (x86_64/amd64)
- **Windows MSIX**: [Latest Release](https://github.com/suikan4github/demo-flutter/releases/latest) - Modern Windows 10/11 package (x86_64/amd64)

### Installation Methods

#### Linux Installation

**AppImage (Universal):**
```bash
chmod +x demo-flutter-v*-linux-amd64.AppImage
./demo-flutter-v*-linux-amd64.AppImage
```

**Debian Package (Ubuntu/Debian):**
```bash
sudo dpkg -i demo-flutter-v*-linux-amd64.deb
sudo apt-get install -f  # Fix dependencies if needed

demo-flutter  # Run from anywhere
```

**RPM Package (Red Hat/Fedora/CentOS):**
```bash
sudo rpm -i demo-flutter-v*-linux-amd64.rpm
# or
sudo dnf install demo-flutter-v*-linux-amd64.rpm  # Fedora
# or  
sudo yum install demo-flutter-v*-linux-amd64.rpm  # CentOS/RHEL

demo-flutter  # Run from anywhere
```

**Snap Package (Universal Linux):**
```bash
sudo snap install demo-flutter-v*-linux-amd64.snap --dangerous --devmode

demo-flutter  # Run from anywhere
```
*Note: --dangerous flag is needed for local snap files not from the official store*

#### Windows Installation

**Windows Installer (Recommended):**
1. Download `demo-flutter-v*-windows-amd64-setup.exe`
2. Double-click the installer to run the setup wizard
3. Follow the installation prompts (Administrator privileges required)
4. Launch from Start Menu, Desktop shortcut, or search "Demo Flutter"

*Professional installation with Start Menu integration, Desktop shortcut, and automatic uninstaller registration*

**ZIP Package (Portable):**
1. Download `demo-flutter-v*-windows-amd64.zip`
2. Extract the ZIP file to your desired location
3. Run `demo_flutter.exe` from the extracted folder

*No installation required - fully portable Windows application*

**MSIX Package (Modern Windows 10/11):**
1. Download `demo-flutter-v*-windows-amd64.msix`
2. Double-click the MSIX file to install
3. Click "Install" when prompted (sideloading required)
4. Launch from Start Menu or search "Demo Flutter"

*Modern Windows package with automatic updates and clean uninstall*

**Note:** MSIX packages require enabling sideloading in Windows settings:
- Go to Settings > Update & Security > For developers
- Select "Sideload apps" or "Developer mode"

### Architecture Support
This application is built for **x86_64 (amd64)** architecture:
- **Linux x86_64 (amd64)**: Intel/AMD 64-bit processors, compatible with most modern Linux Desktop systems
- **Windows x86_64 (amd64)**: Intel/AMD 64-bit processors, compatible with Windows 10/11 (64-bit)

# Development

This repository contains a simple Flutter application that demonstrates basic functionality and cross-platform packaging.

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/suikan4github/demo-flutter.git
   cd demo-flutter
   ```
2. Install dependencies:
   ```bash
   flutter pub get
   ```

## Build and Run

### Linux Desktop
3. Run the application:
   ```bash
   flutter run -d linux
   ```

### Windows Desktop
3. Run the application (on Windows):
   ```bash
   flutter run -d windows
   ```

### Web
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


