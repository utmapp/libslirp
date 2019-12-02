# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [4.1.0] - 2019-12-02

### Added

 - The `slirp_new()` API, simpler and more extensible than `slirp_init()`.
 - Allow custom MTU configuration.
 - Option to disable host loopback connections.
 - CI now runs scan-build too.

### Changed

 - Disable `tcp_emu()` by default. `tcp_emu()` is known to have caused
   several CVEs, and not useful today in most cases. The feature can
   be still enabled by setting `SlirpConfig.enable_emu` to true.
 - meson build system is now `subproject()` friendly.
 - Replace remaining `malloc()`/`free()` with glib (which aborts on OOM)
 - Various code cleanups.

### Deprecated

 - The `slirp_init()` API.

### Fixed

 - `getpeername()` error after `shutdown(SHUT_WR)`.
 - Exec forward: correctly parse command lines that contain spaces.
 - Allow 0.0.0.0 destination address.
 - Make host receive broadcast packets.
 - Various memory related fixes (heap overflow, leaks, NULL
   dereference).
 - Compilation warnings, dead code.

## [4.0.0] - 2019-05-24

### Added

 - Installable as a shared library.
 - meson build system
   (& make build system for in-tree QEMU integration)

### Changed

 - Standalone project, removing any QEMU dependency.
 - License clarifications.

[unreleased]: https://gitlab.freedesktop.org/slirp/libslirp/compare/v4.1.0...master
[4.1.0]: https://gitlab.freedesktop.org/slirp/libslirp/compare/v4.0.0...v4.1.0
[4.0.0]: https://gitlab.freedesktop.org/slirp/libslirp/commits/v4.0.0
