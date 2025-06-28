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

[Unreleased]: https://github.com/suikan4github/demo-flutter/compare/v1.6.8...develop
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
