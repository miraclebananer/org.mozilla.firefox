# Firefox Web Browser Flatpak

Flatpak package for Mozilla Firefox web browser 

## Status: Ready to Build

This flatpak downloads official Firefox binaries from Mozilla and repackages them as a flatpak.

## Installation

```bash
git clone git@github.com:MrMEEE/org.mozilla.firefox.git
cd org.mozilla.firefox
flatpak-builder --user --install --ccache builddir org.mozilla.firefox.yaml
```

## Usage

```bash
flatpak run org.mozilla.firefox
```

## Build Approach

This flatpak uses the binary distribution approach:

1. **Download official binaries**: Gets Firefox from Mozilla's CDN
2. **Extract and install**: Unpacks to `/app/lib/firefox`
3. **Create wrapper**: Simple shell script to launch Firefox
4. **Install desktop integration**: Icons, desktop file, metainfo

## Features

- Full Firefox feature set
- Hardware acceleration support
- Wayland support
- Audio/video playback
- WebGL support
- File downloads to ~/Downloads
- Integration with system notifications
- MPRIS media controls

## Permissions

The flatpak has comprehensive permissions for full browser functionality:

- **Network access**: Required for web browsing
- **Graphics**: X11, Wayland, DRI for hardware acceleration
- **Audio**: PulseAudio for media playback
- **File access**: Downloads, documents (read-only), pictures, videos, music
- **D-Bus**: Notifications, file manager, screen saver, secrets
- **Hardware**: All devices (for webcam, USB, etc.)
- **Printing**: CUPS socket for printing support

## Technical Details

- **Runtime**: org.freedesktop.Platform 25.08
- **SDK**: org.freedesktop.Sdk 25.08
- **Architecture**: x86_64
- **Locale**: en-US

## Note About Official Version

Firefox is officially available on Flathub as `org.mozilla.firefox`. This custom build
is for educational purposes and development testing. For production use, consider using
the official Flathub version which includes:

- Automatic updates through Flathub
- Community support
- Regular security updates
- Additional locale support

## Repository

https://github.com/MrMEEE/org.mozilla.firefox

## Resources

- Firefox homepage: https://www.mozilla.org/firefox/
- Firefox support: https://support.mozilla.org/
- Download page: https://www.mozilla.org/firefox/download/
- Mozilla CDN: https://download-installer.cdn.mozilla.net/
