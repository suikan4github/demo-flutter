# CHANGELOG

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
### Changed
### Deprecated
### Removed
### Fixed
### Security
### Known Issue

## [v1.11.1] 2025-06-29
### Fixed
- Fix macOS ARM64 build failure due to invalid `--target-platform` flag
- Use platform-specific GitHub Actions runners for native architecture builds
- Replace `--target-platform` approach with runner-based architecture targeting
- Use `macos-13` (Intel) runner for x86_64 builds and `macos-latest` (Apple Silicon) for ARM64 builds
- Ensure proper native binary generation for each macOS architecture

### Technical Details
- Remove unsupported `--target-platform darwin-arm64` and `--target-platform darwin-x64` flags
- Use `macos-13` runner for Intel-based x86_64 native builds
- Use `macos-latest` runner for Apple Silicon ARM64 native builds
- Each runner produces optimized binaries for its native architecture
- Maintain standard `flutter build macos --release` command for both architectures

## [v1.11.0] 2025-06-29
### Added
- Apple Silicon (ARM64) native support for macOS platform
- Dedicated ARM64 builds for M1/M2/M3 Mac computers
- Native Apple Silicon performance without Rosetta 2 translation
- macOS ARM64 ZIP package: `demo-flutter-${version}-macos-arm64.zip`
- macOS ARM64 DMG package: `demo-flutter-${version}-macos-arm64.dmg`
- Architecture-specific download guidance in documentation
- Separate build jobs for x86_64 and ARM64 macOS architectures

### Changed
- Expand macOS support from Intel-only to Universal (Intel + Apple Silicon)
- Update macOS package naming to clarify architecture (amd64 vs arm64)
- Enhance macOS installation instructions with architecture selection guidance
- Improve CI/CD pipeline with dual-architecture macOS builds
- Update documentation to reflect multi-architecture macOS support

### Technical Details
- Use `--target-platform darwin-arm64` for native Apple Silicon builds
- Use `--target-platform darwin-x64` for Intel Mac builds
- Maintain separate GitHub Actions jobs for each architecture
- Provide optimal performance for both Intel and Apple Silicon Macs
- Clear architecture identification in package filenames and DMG volume names

## [v1.10.1] 2025-06-29
### Fixed
- Fix macOS build failure due to missing macOS platform support in project
- Add `flutter create --platforms=macos .` to GitHub Actions workflow
- Ensure macOS desktop project configuration is properly initialized
- Resolve "No macOS desktop project configured" error in CI/CD pipeline
- Add macOS platform files (macos/ directory) to the repository

### Technical Details
- Add macOS platform support generation step in both ZIP and DMG build jobs
- Use `flutter create --platforms=macos .` to add macOS support to existing project
- Include complete macOS project structure with Xcode configuration
- Ensure proper macOS .app bundle generation for both distribution formats

## [v1.10.0] 2025-06-29
### Added
- macOS platform support with ZIP and DMG distribution formats
- Automated macOS build in GitHub Actions release workflow
- Cross-platform release artifacts for Linux, Windows, and macOS
- macOS ZIP package: `demo-flutter-${version}-macos-amd64.zip` (portable app bundle)
- macOS DMG package: `demo-flutter-${version}-macos-amd64.dmg` (disk image installer)
- Professional macOS installation experience with drag-and-drop to Applications
- macOS system integration with proper .app bundle structure
- Universal compatibility for Intel Macs and Apple Silicon Macs (via Rosetta 2)

### Changed
- Expand CI/CD pipeline to support tri-platform builds (Linux + Windows + macOS)
- Update release workflow to build for Linux, Windows, and macOS platforms
- Enhance artifact naming to include platform identifier (linux/windows/macos)
- Improve cross-platform compatibility and distribution strategy
- Update documentation with macOS installation instructions and system requirements

### Technical Details
- macOS builds use `macos-latest` GitHub Actions runner (Intel-based)
- Flutter macOS desktop build with release configuration
- Automated ZIP archive creation with complete .app bundle
- Professional DMG creation with Applications folder symlink
- Consistent filename format across all platforms and package types
- Proper macOS security handling instructions for unsigned applications

## [v1.9.2] 2025-06-29
### Fixed
- Completely remove problematic Inno Setup help command execution from workflow
- Simplify Inno Setup verification to only check file existence
- Eliminate PowerShell exit code issues from external process execution
- Ensure Windows Installer build workflow completes successfully
- Remove unnecessary command validation that was causing CI/CD failures

### Technical Details
- Remove `iscc.exe /?` execution that was returning exit code 1
- Simplify verification to only use `Test-Path` for installation confirmation
- Prevent PowerShell from propagating external command exit codes
- Focus on essential validation without problematic command execution

## [v1.9.1] 2025-06-29
### Fixed
- Fix Inno Setup installation verification in Windows Installer build workflow
- Resolve "Process completed with exit code 1" error during Inno Setup validation
- Improve error handling for iscc.exe command execution in GitHub Actions
- Add proper exit code handling for Inno Setup compiler verification
- Fix LICENSE file reference issue in Inno Setup script generation

### Technical Details
- Use try-catch block for Inno Setup compiler validation to handle expected exit codes
- Remove problematic iscc.exe execution during installation verification
- Add conditional LICENSE file inclusion in Inno Setup script
- Improve GitHub Actions workflow reliability for Windows Installer generation
- Handle Inno Setup help command exit codes properly in PowerShell

## [v1.9.0] 2025-06-29
### Added
- Windows Installer package distribution format using Inno Setup
- Automated Windows Installer (.exe) build in GitHub Actions release workflow
- Professional installation experience with setup wizard and uninstaller
- Windows Installer package: `demo-flutter-${version}-windows-amd64-setup.exe`
- Desktop and Start Menu shortcuts creation during installation
- Automatic registration in Windows "Programs and Features" / "Apps & features"
- Built-in uninstaller with complete cleanup functionality
- Upgrade detection and automatic old version removal
- Multi-language support (English and Japanese) in installer
- Administrator privileges handling for system-wide installation

### Changed
- Expand Windows distribution options to include ZIP, MSIX, and Installer formats
- Enhance Windows platform support with professional installation standards
- Improve user experience with guided installation and proper integration
- Update release workflow to build comprehensive Windows package portfolio

### Technical Details
- Uses Inno Setup 6 for professional Windows installer creation
- Includes desktop shortcut creation (optional)
- Automatic uninstaller generation and registration
- Supports silent installation and uninstallation modes
- Proper Windows integration with Add/Remove Programs
- Upgrade-aware installation with automatic old version cleanup
- File association and registry cleanup on uninstall
- Multi-architecture support (x64 optimized)

## [v1.8.6] 2025-06-29
### Fixed
- Fix MSIX file location detection in Windows build workflow
- Resolve MSIX file not found error when file is created in build subdirectory
- Add intelligent MSIX file search in both root and build directories
- Handle MSIX file location in `build\windows\x64\runner\Release\` directory
- Automatically copy MSIX file from build directory to root for processing

### Technical Details
- Search for MSIX files in both root directory and `build\windows\x64\runner\Release\`
- Copy MSIX file from build directory to root directory for easier handling
- Improve file location detection logic to handle Flutter's MSIX output location
- Add detailed logging for MSIX file discovery and processing
- Ensure proper file handling regardless of MSIX creation location

## [v1.8.5] 2025-06-29
### Fixed
- Fix MSIX interactive certificate installation prompt blocking GitHub Actions workflow
- Resolve "Do you want to install the certificate" prompt causing workflow timeout
- Automatically answer 'y' to certificate installation prompt in non-interactive environment
- Fix MSIX package creation failure due to unhandled user input prompt
- Enhance MSIX file search with full path debugging output

### Technical Details
- Use `echo "y" | dart run msix:create` to automatically accept certificate installation
- Add comprehensive MSIX file location debugging with full paths
- Prevent workflow hanging on interactive prompts in GitHub Actions environment
- Resolve certificate installation blocking issue in automated builds
- Improve error diagnostics for MSIX generation troubleshooting

## [v1.8.4] 2025-06-29
### Fixed
- Fix MSIX package creation error in Windows build workflow
- Add existence check for generated MSIX file before renaming
- Resolve "type 'Null' is not a subtype of type 'FutureOr<String>'" error
- Enhance error handling and debugging output in MSIX creation step
- Prevent workflow failure when dart run msix:create doesn't generate expected file

### Technical Details
- Add file existence validation before attempting to rename MSIX package
- Include comprehensive debugging output to diagnose MSIX generation issues
- Improve error messages when MSIX file is not found after creation
- Add recursive search for MSIX files in case of unexpected location
- Enhance workflow reliability with proper null checks and error handling

## [v1.8.3] 2025-06-29
### Fixed
- Fix MSIX AppxManifest.xml invalid FileType configuration error
- Remove invalid file_extension '.' from MSIX configuration in pubspec.yaml
- Resolve "violates pattern constraint of '.[^.]+'" error in Windows MSIX build
- Ensure MSIX manifest file type entries comply with Windows App packaging requirements
- Fix uap:FileType validation issue in AppxManifest.xml generation

### Technical Details
- Remove file_extension: '' from msix_config in pubspec.yaml
- Prevent generation of invalid <uap:FileType>.</uap:FileType> entries
- Ensure MSIX manifest validation passes for Windows package deployment
- Fix AppxManifest.xml schema compliance for file associations

## [v1.8.2] 2025-06-29
### Fixed
- Fix MSIX code-signing certificate issue in Windows build
- Replace certificate store reference with self-signed certificate generation
- Resolve "certificate not found in: STORE" error in GitHub Actions workflow
- Enable MSIX packaging without requiring pre-installed certificates
- Use PowerShell New-SelfSignedCertificate for automated certificate creation

### Technical Details
- Generate self-signed certificate during GitHub Actions workflow execution
- Export certificate to .pfx file with temporary password for MSIX signing
- Update certificate_path to point to generated certificate file
- Enable development/testing MSIX packages without Microsoft Store requirements

## [v1.8.1] 2025-06-29
### Fixed
- Fix MSIX package identity_name format error in Windows build
- Change identity_name from invalid "com.example.demo_flutter" to valid "DemoFlutter.DemoFlutterApp"
- Resolve MSIX packaging workflow failure due to invalid company name format
- Ensure MSIX identity follows Microsoft's naming requirements (3-50 characters, alphanumeric/period/dash only)

### Technical Details
- MSIX identity_name must not use "com" as company prefix
- Updated to use "DemoFlutter.DemoFlutterApp" format for proper MSIX compliance
- Fixed GitHub Actions workflow error in build-windows-msix job

## [v1.8.0] 2025-06-29
### Added
- Windows MSIX package distribution format
- Automated MSIX build in GitHub Actions release workflow
- Modern Windows 10/11 native package format with enhanced security
- MSIX package: `demo-flutter-${version}-windows-amd64.msix`
- Windows application manifest for MSIX packaging
- Enhanced Windows integration with MSIX capabilities

### Changed
- Expand Windows distribution options to include both ZIP and MSIX formats
- Update release workflow to build multiple Windows package types
- Enhance Windows platform support with modern packaging standards
- Improve Windows application deployment and installation experience

### Technical Details
- MSIX builds use Flutter's built-in MSIX support via `msix` package
- Automated certificate generation for development/testing purposes
- MSIX packages support sideloading without Microsoft Store registration
- Enhanced Windows integration including file associations and notifications

## [v1.7.0] 2025-06-29
### Added
- Windows platform support with ZIP distribution format
- Automated Windows build in GitHub Actions release workflow
- Cross-platform release artifacts with unified naming convention
- Windows ZIP package: `demo-flutter-${version}-windows-amd64.zip`

### Changed
- Expand CI/CD pipeline to support multi-platform builds (Linux + Windows)
- Update release workflow to build for both Linux and Windows platforms
- Enhance artifact naming to include platform identifier (linux/windows)
- Improve cross-platform compatibility and distribution strategy

### Technical Details
- Windows builds use `windows-2022` GitHub Actions runner
- Flutter Windows desktop build with release configuration
- Automated ZIP archive creation with all necessary runtime files
- Consistent filename format across all platforms and package types

## [v1.6.9] 2025-06-29
### Changed
- Update README.md to reflect current x86_64 (amd64) architecture support only
- Remove outdated ARM64 architecture references from installation instructions
- Clarify that the application is currently built for Linux Desktop x86_64 systems only
- Update download links and package naming to reflect unified filename format

### Removed
- ARM64/aarch64 architecture references from README.md documentation
- Outdated multi-architecture installation instructions
- Legacy filename examples that don't match current release format

## [v1.6.8] 2025-06-29
### Fixed
- Fix GitHub Actions release workflow "Resource not accessible by integration" error
- Replace default GITHUB_TOKEN with Personal Access Token (PERSONAL_TOKEN) for release operations
- Resolve insufficient permissions issue when creating releases and uploading assets
- Improve reliability of automated release process

### Changed
- Update all release-related GitHub Actions steps to use PERSONAL_TOKEN instead of GITHUB_TOKEN
- Enhance release workflow security and permissions handling
- Ensure consistent release creation across all scenarios

## [v1.6.7] 2025-06-29
### Changed
- Standardize release artifact file naming to `demo-flutter-${version}-linux-amd64.*` format
- Unify naming convention across all package types (tar.gz, .deb, .rpm, .AppImage, .snap)
- Improve consistency and clarity in release artifact identification
- Update tar.gz filename from `demo-flutter-v1.6.6-linux-x64.tar.gz` to `demo-flutter-v1.6.7-linux-amd64.tar.gz`
- Update .deb filename from `demo-flutter-v1.6.6-amd64.deb` to `demo-flutter-v1.6.7-linux-amd64.deb`
- Update AppImage filename from `demo-flutter-v1.6.6-x86_64.AppImage` to `demo-flutter-v1.6.7-linux-amd64.AppImage`
- Update RPM filename from malformed path to `demo-flutter-v1.6.7-linux-amd64.rpm`
- Update Snap filename from `demo-flutter_v1.6.6_amd64.snap` to `demo-flutter-v1.6.7-linux-amd64.snap`

### Fixed
- Enhance release workflow to use consistent file naming patterns
- Ensure all generated packages follow the same naming structure
- Improve download experience with predictable file names
- Fix inconsistent architecture naming (x64, x86_64, amd64) to consistent `amd64`
- Correct RPM file path issues causing malformed filenames in releases
- Improve release artifact organization and naming consistency

## [v1.6.6] 2025-06-29
### Changed
- Temporarily remove ARM64 architecture support for better build stability
- Focus on x86_64 Linux builds for reliable CI/CD pipeline
- Simplify release workflow by removing complex multi-architecture builds

### Removed
- ARM64 build matrix and related workflow complexity
- ARM64-specific build configurations and dependencies
- Multi-architecture build strategy to ensure stable releases
- snapcraft.yaml file and snap/ directory (using manual snap creation instead)

### Fixed
- Eliminate ARM64 build failures and complex debugging requirements
- Ensure consistent and reliable x86_64 Linux desktop builds
- Improve overall CI/CD pipeline reliability and maintenance
- Remove duplicate workflow steps and matrix configurations

## [v1.6.5] 2025-06-29
### Fixed
- Simplify ARM64 builds using native GitHub Actions ARM64 runners
- Replace complex Docker/QEMU cross-compilation with native ARM64 execution
- Eliminate build complexity and potential issues from cross-compilation
- Improve build reliability and speed using native ARM64 execution
- Correct ARM64 build output paths (`build/linux/arm64/release/bundle`)
- Standardize build process across all package formats (tar.gz, .deb, .rpm, AppImage, Snap)

### Changed
- Migrate from complex Docker/QEMU cross-compilation to native ARM64 runners
- Use `ubuntu-24.04-arm64` runner for ARM64 builds instead of emulation
- Simplify Flutter setup by using `subosito/flutter-action@v2` for all architectures

### Removed
- Docker-based ARM64 cross-compilation environment
- QEMU emulation setup for ARM64 builds
- Manual Flutter SDK download and extraction for ARM64
- Complex cross-compilation environment variables and toolchain configuration
- Duplicate ARM64 build steps across different package types

## [v1.6.4] 2025-06-29
### Changed
- Temporarily disable ARM64 architecture support for better build stability
- Focus on x86_64 Linux builds for reliable CI/CD pipeline
- Remove complex ARM64 cross-compilation setup due to Flutter SDK limitations

### Fixed
- Simplify release workflow by removing problematic ARM64 builds
- Ensure stable and reproducible Linux desktop builds
- Improve overall CI/CD reliability and maintenance

## [v1.6.3] 2025-06-29
### Fixed
- Resolve ARM64 Docker build git safe directory configuration issues
- Clean up duplicate lines in snapcraft.yaml for better package integrity
- Improve ARM64 cross-compilation stability and reliability

## [v1.6.2] 2025-06-28
### Fixed
- Remove duplicate Flutter setup steps in build-and-upload job
- Fix redundant flutter pub get and flutter build commands in RPM build workflow
- Eliminate conflicting workflow steps that caused PATH resolution issues
- Streamline multi-architecture build process for better reliability

## [v1.6.1] 2025-06-28
### Fixed
- Flutter PATH configuration issues in ARM64 cross-compilation workflow
- x86_64 build Flutter SDK setup and environment variable handling
- GitHub Actions workflow steps execution order for multi-architecture builds
- AppImage build process PATH resolution for manual Flutter SDK installation

## [v1.6.0] 2025-06-28
### Added
- ARM64 (aarch64) architecture support for Linux desktop builds
- Cross-compilation support for ARM64 in GitHub Actions workflows
- ARM64 package generation for all distribution formats:
  - AppImage for ARM64 architecture
  - Debian package (.deb) for arm64
  - RPM package for aarch64
  - Tarball archive for ARM64
  - Snap package for arm64
- Matrix-based build strategy supporting both x86_64 and ARM64 architectures
- Enhanced release workflow with multi-architecture support
- ARM64-specific build dependencies and configurations

### Changed
- Updated GitHub Actions release workflow to use build matrix
- Modified package naming to include architecture suffix
- Enhanced CI/CD pipeline to build for multiple architectures
- Updated documentation with ARM64 installation instructions

## [v1.5.5] 2025-06-28
### Fixed
- Snap package file movement issue in GitHub Actions
- Prevent "same file" error when finalizing Snap package
- Improved condition checks for file location verification
- Enhanced error handling and debugging output for Snap build process

## [v1.5.4] 2025-06-28
### Changed
- Removed snapcraft.yaml file and switched to manual Snap package creation
- Simplified Snap build process to avoid Snapcraft installation issues
- Hand-crafted Snap package structure for better reliability in GitHub Actions
- Removed Snapcraft dependencies from build process

## [v1.5.3] 2025-06-28
### Fixed
- Snapcraft installation issues on Ubuntu 24.04
- Use snap install method instead of apt for snapcraft installation
- Simplified Snap build process for better reliability
- Fixed Snap package creation workflow in GitHub Actions

## [v1.5.2] 2025-06-28
### Fixed
- File path issues in RPM and Snap package upload steps
- Use absolute paths (GITHUB_WORKSPACE) for asset uploads in GitHub Actions
- Resolves "file not found" errors during release asset upload
- Enhanced debugging output for file path verification

## [v1.5.1] 2025-06-28
### Fixed
- RPM build file path issues and error handling
- Snap package build configuration and script syntax errors
- Enhanced debug output for both RPM and Snap build processes
- Improved error handling in GitHub Actions release workflow

## [v1.5.0] 2025-06-28
### Added
- [Issue #11](https://github.com/suikan4github/demo-flutter/issues/11) Add snap package to release file. 
- Snap package (.snap) distribution for universal Linux systems
- Automated Snap package creation in GitHub Actions release workflow 

## [v1.4.1] 2025-06-28
### Fixed
- RPM package build failure due to missing desktop-file-utils dependency
- Added desktop-file-utils package installation in RPM build job
- Added verification step to ensure desktop-file-install is available during RPM build

## [v1.4.0] 2025-06-28
### Added
- [Issue #10](https://github.com/suikan4github/demo-flutter/issues/10) Add RPM to release file.
- RPM package (.rpm) distribution for Red Hat/Fedora/CentOS systems
- Automated .rpm package creation in GitHub Actions release workflow


## [v1.3.0] 2025-06-28
### Added
- [Issue #9](https://github.com/suikan4github/demo-flutter/issues/9) Add tag triggered release.

## [v1.2.0] 2025-06-28

### Added
- [Issue #8](https://github.com/suikan4github/demo-flutter/issues/8) Add tag triggered release.

## [v1.2.1] 2025-06-28
### Fixed
- Fix AppImage build FUSE issue in GitHub Actions
- AppImage extraction process for avoiding FUSE dependency
- CHANGELOG formatting issues

# [v1.1.1] 2025-06-28

### Added
- [Issue #4](https://github.com/suikan4github/demo-flutter/issues/4) Add basic CI/CD pipeline.
- [Issue #5](https://github.com/suikan4github/demo-flutter/issues/5) Add GitHub Pages deployment.


## [v1.1.0] 2025-06-28
### Added
- [Issue #2](https://github.com/suikan4github/demo-flutter/issues/2) Add web support.


## [v1.0.0] 2025-06-28
Pre-release version. 

[Unreleased]: https://github.com/suikan4github/demo-flutter/compare/v1.11.1...develop
[v1.11.1]: https://github.com/suikan4github/demo-flutter/compare/v1.11.0...v1.11.1
[v1.11.0]: https://github.com/suikan4github/demo-flutter/compare/v1.10.1...v1.11.0
[v1.10.1]: https://github.com/suikan4github/demo-flutter/compare/v1.10.0...v1.10.1
[v1.10.0]: https://github.com/suikan4github/demo-flutter/compare/v1.9.2...v1.10.0
[v1.9.2]: https://github.com/suikan4github/demo-flutter/compare/v1.9.1...v1.9.2
[v1.9.1]: https://github.com/suikan4github/demo-flutter/compare/v1.9.0...v1.9.1
[v1.9.0]: https://github.com/suikan4github/demo-flutter/compare/v1.8.6...v1.9.0
[v1.8.6]: https://github.com/suikan4github/demo-flutter/compare/v1.8.5...v1.8.6
[v1.8.5]: https://github.com/suikan4github/demo-flutter/compare/v1.8.4...v1.8.5
[v1.8.4]: https://github.com/suikan4github/demo-flutter/compare/v1.8.3...v1.8.4
[v1.8.3]: https://github.com/suikan4github/demo-flutter/compare/v1.8.2...v1.8.3
[v1.8.2]: https://github.com/suikan4github/demo-flutter/compare/v1.8.1...v1.8.2
[v1.8.1]: https://github.com/suikan4github/demo-flutter/compare/v1.8.0...v1.8.1
[v1.8.0]: https://github.com/suikan4github/demo-flutter/compare/v1.7.0...v1.8.0
[v1.7.0]: https://github.com/suikan4github/demo-flutter/compare/v1.6.9...v1.7.0
[v1.6.9]: https://github.com/suikan4github/demo-flutter/compare/v1.6.8...v1.6.9
[v1.6.8]: https://github.com/suikan4github/demo-flutter/compare/v1.6.7...v1.6.8
[v1.6.7]: https://github.com/suikan4github/demo-flutter/compare/v1.6.6...v1.6.7
[v1.6.6]: https://github.com/suikan4github/demo-flutter/compare/v1.6.5...v1.6.6
[v1.6.5]: https://github.com/suikan4github/demo-flutter/compare/v1.6.4...v1.6.5
[v1.6.4]: https://github.com/suikan4github/demo-flutter/compare/v1.6.3...v1.6.4
[v1.6.3]: https://github.com/suikan4github/demo-flutter/compare/v1.6.2...v1.6.3
[v1.6.2]: https://github.com/suikan4github/demo-flutter/compare/v1.6.1...v1.6.2
[v1.6.1]: https://github.com/suikan4github/demo-flutter/compare/v1.6.0...v1.6.1
[v1.6.0]: https://github.com/suikan4github/demo-flutter/compare/v1.5.5...v1.6.0
[v1.5.5]: https://github.com/suikan4github/demo-flutter/compare/v1.5.4...v1.5.5
[v1.5.4]: https://github.com/suikan4github/demo-flutter/compare/v1.5.3...v1.5.4
[v1.5.3]: https://github.com/suikan4github/demo-flutter/compare/v1.5.2...v1.5.3
[v1.5.2]: https://github.com/suikan4github/demo-flutter/compare/v1.5.1...v1.5.2
[v1.5.1]: https://github.com/suikan4github/demo-flutter/compare/v1.5.0...v1.5.1
[v1.5.0]: https://github.com/suikan4github/demo-flutter/compare/v1.4.1...v1.5.0
[v1.4.1]: https://github.com/suikan4github/demo-flutter/compare/v1.4.0...v1.4.1
[v1.4.0]: https://github.com/suikan4github/demo-flutter/compare/v1.3.0...v1.4.0
[v1.3.0]: https://github.com/suikan4github/demo-flutter/compare/v1.2.1...v1.3.0
[v1.2.1]: https://github.com/suikan4github/demo-flutter/compare/v1.2.0...v1.2.1
[v1.2.0]: https://github.com/suikan4github/demo-flutter/compare/v1.1.1...v1.2.0
[v1.1.1]: https://github.com/suikan4github/demo-flutter/compare/v1.1.0...v1.1.1
[v1.1.0]: https://github.com/suikan4github/demo-flutter/compare/v1.0.0...v1.1.0
[v1.0.0]: https://github.com/suikan4github/demo-flutter/compare/v0.0.0...v1.0.0
