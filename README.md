# Nightfall 🌙

**Less glare. More focus.**

Nightfall is a privacy-first dark-mode extension for Firefox, powered by **DarX 1.0 RC2**. Built with older hardware in mind, it combines dark mode, custom atmospheres and practical reading tools.

**Current release:** Nightfall RC2

## Features

### Dark mode
- Automatic detection of websites with existing dark themes
- Protection for images, videos and diagrams
- Per-site on/off preferences
- BRUTE FORCE mode for stubborn pages

### Your preferred atmosphere
Choose from four presets:
- **Original** — charcoal
- **Moon** — cool blue
- **Ember** — warm tones
- **Moss** — quiet green

Adjust brightness, contrast, warmth, sepia and greyscale. Brightness and contrast are also available directly in the popup, with a button to reset both to 100%.

### Automatic activation
- Manual control
- Follow your system theme
- Custom time schedule
- Sunrise/sunset activation using manually entered coordinates and NOAA solar calculations

### Reading tools
- **Reading rail** — helps you follow the current line on light or dark pages
- **Quiet motion** — reduces page motion while dark mode is active
- **Peek original** — briefly view the page without Nightfall
- **Temporary pause** — pause Nightfall without losing preferences

### Local preferences
- Saved site preferences and atmosphere overrides
- JSON settings export and reviewed import
- Dedicated settings page
- **Alt + Shift + D** to toggle global dark mode
- **Alt + Shift + N** to open Nightfall

Keyboard shortcuts can be changed in Firefox’s extension shortcut settings.

## Installation

**Requires Firefox 140 or later.**

1. Download the Mozilla-signed `.xpi` from this repository’s Releases page.
2. Open Firefox’s Add-ons Manager (`about:addons`).
3. Click the gear icon → **Install Add-on From File**.
4. Select the downloaded `.xpi` and confirm installation.

Use the signed `.xpi` release asset. GitHub’s automatically generated source archives are not installable signed extensions.

## How DarX works

DarX uses a page-level darkening filter with selective protection for media and existing dark regions. Regional processing refines mixed light and dark pages.

Atmospheres apply additional filter presets rather than replacing every webpage colour with a fixed palette. Appearance adjustments can therefore change accent and media colours.

## Privacy

Nightfall stores preferences locally on your device.

- No telemetry
- No analytics
- No external network requests from the extension
- No account required
- No automatic location lookup

Coordinates are entered manually for sunrise/sunset automation. Settings exports omit coordinates and saved site preferences unless you choose to include them.

Nightfall requests access to HTTP and HTTPS websites so it can apply dark styling. Firefox restricts extensions from modifying certain protected pages.

## Release candidate status

Nightfall RC2 is still being tested.

- Complex websites may show colour inconsistencies.
- Heavy pages can take time to settle.
- Performance varies by website, browser and hardware.
- Image and diagram protection is not a guarantee of pixel-identical output.
- Browser-protected pages cannot be themed.

Nightfall has been used on an older 12-inch MacBook running Windows. Broader hardware performance comparisons have not yet been established.

## Reporting bugs

Please open an issue with:

- Firefox version
- Operating system
- Affected website URL
- Steps to reproduce
- Expected and actual behaviour
- Screenshots, where useful
- Whether disabling Nightfall resolves the issue

Remove private information from screenshots and URLs. Never share passwords, session tokens, private schoolwork or account details.

## Development

Nightfall uses plain JavaScript, HTML, CSS and SVG, with no build step or runtime dependencies.

To load it temporarily:

1. Open `about:debugging#/runtime/this-firefox`.
2. Click **Load Temporary Add-on**.
3. Select the project’s `manifest.json`.

Temporary installations are removed when Firefox restarts.

Run the automated checks with:

    node tests/run.cjs

The automated suite covers settings, imports, message validation, rendering logic and lifecycle cleanup. These checks do not replace live Firefox visual and performance testing.

## Contributing

Bug reports, reproducible test cases and focused improvements are welcome.

Please describe substantial changes in an issue before starting work. Compatibility, responsiveness and privacy take priority over adding features.
