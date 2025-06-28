# Change log
History of the project development

## [Unreleased] yyyy-mm-zz

### Added
### Changed
### Deprecated
### Removed
### Fixed
### Security
### Known Issue

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

[Unreleased]: https://github.com/suikan4github/demo-flutter/compare/v1.6.3...develop
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
