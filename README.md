# Gazoo Scroll Reverse

A macOS menu bar utility that gives you independent control over mouse and trackpad scrolling behavior.

![macOS](https://img.shields.io/badge/macOS-11.0+-blue)
![Platform](https://img.shields.io/badge/platform-Apple%20Silicon%20(arm64)-lightgrey)
![License](https://img.shields.io/badge/license-MIT-green)

## Why This App?

Ever switched between a MacBook trackpad and an external mouse, only to find yourself scrolling the wrong direction? macOS lets you change scroll direction globally, but what if you want **natural scrolling on your trackpad** and **traditional scrolling on your mouse**?

**Gazoo Scroll Reverse** solves this problem elegantly with independent, per-device scroll control.

## Features

✅ **Independent Device Control** - Different settings for trackpad and mouse
✅ **Independent Axis Control** - Reverse vertical and horizontal scrolling separately
✅ **Instant Changes** - No app restart needed
✅ **System-Wide** - Works in all applications
✅ **Lightweight** - Sits quietly in your menu bar
✅ **Fully Notarized** - Signed and notarized by Apple

## Download

**[Download GazooScrollReverse-1.0.dmg](https://github.com/AnxietyLab/gazoo-scroll-reverse/releases/latest)**

### System Requirements

- macOS 11.0 (Big Sur) or later
- **Apple Silicon (M1/M2/M3/M4) Mac only** - arm64 architecture
- Accessibility permission (requested on first launch)

> ⚠️ **Note:** This version is compiled for Apple Silicon only. Intel Mac users need to run under Rosetta or request a universal binary.

## Installation

1. **Download** the DMG file from the link above
2. **Open** the DMG and drag `GazooScrollReverse.app` to your Applications folder
3. **Launch** the app from Applications
4. **Grant Accessibility permission** when prompted (required for scroll interception)
5. **Configure** your preferences from the menu bar icon

### First Launch

When you first open the app, macOS will request Accessibility permission. This is required for the app to intercept and modify scroll events system-wide.

**To grant permission:**
1. Click "Open System Settings" in the prompt
2. Toggle `GazooScrollReverse` ON in Privacy & Security → Accessibility
3. The app will automatically activate once permission is granted

## Usage

Click the ⟲ icon in your menu bar to access settings:

### Options

- **Reverse Vertical** (`⌘V`) - Flip vertical scroll direction
- **Reverse Horizontal** (`⌘H`) - Flip horizontal scroll direction
- **Reverse Trackpad** (`⌘T`) - Apply reversal to trackpad
- **Reverse Mouse** (`⌘M`) - Apply reversal to mouse

### Common Configurations

**Natural trackpad, traditional mouse:**
- ✅ Reverse Trackpad
- ⬜ Reverse Mouse
- ✅ Reverse Vertical

**Traditional trackpad, natural mouse:**
- ⬜ Reverse Trackpad
- ✅ Reverse Mouse
- ✅ Reverse Vertical

All settings save automatically and persist between launches.

## How It Works

Gazoo Scroll Reverse uses Apple's **CGEventTap API** to intercept scroll events at the system level. When you scroll:

1. The app captures the scroll event before it reaches applications
2. Checks device type (trackpad vs mouse) and your preferences
3. Reverses the scroll direction if configured
4. Passes the modified event to the application

This approach works system-wide in all applications without requiring per-app configuration.

## Troubleshooting

### "The application cannot be opened"

This shouldn't happen with the notarized DMG. If you see this error:

```bash
xattr -cr ~/Downloads/GazooScrollReverse-1.0.dmg
```

Then try opening the DMG again.

### Scrolling not being reversed

1. **Check Accessibility permission:**
   - Open System Settings → Privacy & Security → Accessibility
   - Ensure `GazooScrollReverse` is enabled

2. **Restart the app:**
   - Quit from menu bar (Quit option)
   - Relaunch from Applications

3. **Toggle settings:**
   - Sometimes toggling the setting off and on helps
   - Try `⌘V` twice from the menu

4. **Check menu bar status:**
   - The menu should show "Status: Active ✓"
   - If it shows an error, accessibility permission may not be granted

### Settings not saving

Settings are stored in macOS UserDefaults and should persist automatically. If they don't:
- Check that the app has proper file system permissions
- Try deleting the app and reinstalling from the DMG

### Multiple instances running

The app doesn't prevent multiple instances. If scrolling behaves oddly:
```bash
killall GazooScrollReverse
```
Then relaunch from Applications.

## Privacy & Security

- **No network access** - App runs entirely offline
- **No data collection** - Zero analytics or telemetry
- **Open source** - Audit the code if desired (source available on request)
- **Notarized by Apple** - Verified malware-free

The Accessibility permission is used solely to intercept scroll events. The app does not access keyboard input, screen recording, or any other sensitive data.

## Uninstall

To completely remove the app:

```bash
# Quit the app
killall GazooScrollReverse

# Remove app bundle
rm -rf /Applications/GazooScrollReverse.app

# Remove preferences (optional)
defaults delete com.gazoo.scroll-reverse
```

## Version History

### v1.0 (2025-10-30)
- Initial release
- Independent trackpad/mouse control
- Per-axis reversal (vertical/horizontal)
- Fully notarized and stapled

## FAQ

**Q: Does this work with Bluetooth mice?**
A: Yes, any mouse recognized by macOS works.

**Q: Can I reverse horizontal scrolling only?**
A: Yes, toggle "Reverse Vertical" off and "Reverse Horizontal" on.

**Q: Will this affect gaming or other apps?**
A: Yes, it's system-wide. You may want to quit the app while gaming if the reversal interferes.

**Q: Does this drain battery?**
A: No, the app is extremely lightweight and uses negligible CPU/memory.

**Q: Is this better than System Settings scroll direction?**
A: Yes, if you use both trackpad and mouse. macOS only has a global toggle, this gives per-device control.

## Support

Found a bug or have a feature request? [Open an issue](https://github.com/AnxietyLab/gazoo-scroll-reverse/issues).

## License

MIT License - Free to use, modify, and distribute.

---

**Made with ❤️ for anyone tired of fighting with scroll direction.**
