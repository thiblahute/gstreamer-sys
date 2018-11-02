# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html),
specifically the [variant used by Rust](http://doc.crates.io/manifest.html#the-version-field).

## [0.6.0] - 2018-09-08
### Changed
- Updated everything to GStreamer 1.14.2
- Various fixes to how the code generator is used
- Regenerate with latest GIR code generator

### Fixed
- WebRTCICETransport and WebRTCDTLSTransport have the correct parent class
  struct
- gstreamer-webrtc-sys correctly depends/links to gstreamer-sys
- Removed unneeded dependencies from the code generator configuration files

## [0.5.0] - 2018-03-20
### Changed
- Updated everything to GStreamer 1.14.0

### Added
- GstSdp, GstRtsp, GstRtspServer and GstWebRTC bindings

### Fixed
- Use external_libraries feature of gir to require less manual editing
- Remove some unused crates from dependencies
- Disale print_system_libs in calls to pkg-config to work better with
  non-system installs of GStreamer

## [0.4.1] - 2018-02-18
### Fixed
- Fix native library name of GstNet bindings

## [0.4.0] - 2017-12-23
### Added
- GstNet bindings
- Debug impls for basically every type
- Script to automatically regenerate everything

### Changed
- gst_player_[sg]et_multiview_mode() argument types were changed from
  GstMultiviewMode to GstMultiviewFramePacking, which is the correct subset
  of the former that is allowed here
- gst_plugin_add_dependency() takes *mut *mut c_char as argument type instead
  of *mut *const c_char

## [0.3.0] - 2017-11-26
### Added
- GstMpegTs bindings

### Changed
- GstDebugColorFlags from an enum to a bitfield
- Updated to bitflags 1.0
- Added support for the "dox" feature to generate documentation for all
  possible versions
- Depend on glib-sys/gobject-sys 0.5

### Fixes
- GstStackTraceFlags, gst_flow_combiner_ref/unref are only available since
  1.12 and 1.12.1 respectively
- All C enums are represented as integers + constants now to prevent undefined
  behaviour when out-of-range values are received

## [0.2.1] - 2017-09-10
### Changed
- Add README.md to all crates directly

### Fixed
- Fix various compiler warnings
- Fix versioning/feature mess. Now each library has features for all major
  versions and for the correct minor versions that added API.
- Removed Cargo.lock from GIT

## [0.2.0] - 2017-08-28
### Added
- Add GstPlayer bindings

### Changed
- Depend on bitflags 0.9
- Update GIR files to 1.12.1 release
- Fix various errors in the GIR files, backported from GStreamer GIT master
- Depend on gobject-sys/glib-sys 0.4.0 for various improvements
- Regenerated everything with latest GIR

## [0.1.1] - 2017-05-10
### Added
- Add GstTag and GstApp bindings
- Add lots of missing fields to all the structs thanks to GIR improvements

### Changed
- Update GIR files to 1.12.0 release
- Depend on gobject-sys/glib-sys 0.3.4 release for more complete structs
- Regenerated everything with latest GIR

## [0.1.0] - 2017-04-09

- Initial release of the autogenerated GStreamer FFI bindings.

[Unreleased]: https://github.com/sdroege/gstreamer-sys/compare/0.6.0...HEAD
[0.6.0]: https://github.com/sdroege/gstreamer-sys/compare/0.5.0...0.6.0
[0.5.0]: https://github.com/sdroege/gstreamer-sys/compare/0.4.1...0.5.0
[0.4.1]: https://github.com/sdroege/gstreamer-sys/compare/0.4.0...0.4.1
[0.4.0]: https://github.com/sdroege/gstreamer-sys/compare/0.3.0...0.4.0
[0.3.0]: https://github.com/sdroege/gstreamer-sys/compare/0.2.1...0.3.0
[0.2.1]: https://github.com/sdroege/gstreamer-sys/compare/0.2.0...0.2.1
[0.2.0]: https://github.com/sdroege/gstreamer-sys/compare/0.1.1...0.2.0
[0.1.1]: https://github.com/sdroege/gstreamer-sys/compare/0.1.0...0.1.1