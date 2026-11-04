# AeroDrive – Functional Android Car Launcher

AeroDrive is a landscape Android HOME launcher for 1280×800 head units. It preserves the original dashboard image supplied by the user and adds interactive touch areas and live data overlays.

## Included
- Personal on-screen greeting: **Hi Azaam** in the top-left dashboard greeting area.

- Exact supplied dashboard artwork as the screen background.
- Live device clock and date.
- GPS speed in km/h, trip distance accumulated while the app is running, and compass heading.
- Live weather from Open-Meteo using current GPS coordinates (no API key required).
- Navigation, dialer, music/video/radio app shortcuts, Wi-Fi, settings, installed-app picker.
- Media play/pause, next and previous key events routed to the active Android media session where supported.
- Full-screen immersive landscape launcher and GitHub Actions APK build.

## Build APK with GitHub
1. Create a GitHub repository called `AeroDrive`.
2. Upload the contents of this project to the repository root (not the ZIP itself).
3. Open **Actions** → **Build AeroDrive APK** → **Run workflow**.
4. Download the `AeroDrive-debug-apk` artifact from the completed workflow.
5. Extract it and install `app-debug.apk` on the head unit.
6. Press Home and choose **AeroDrive** as the default Home app.

## First-run setup
- Allow location permission when Android asks.
- Enable GPS/location and internet for live speed/weather.
- To use media transport keys, start a music player first. Whether the keys control it depends on the player's media-session support and head-unit firmware.

## Important accuracy / hardware notes
- GPS speed is not ECU speed. It can be delayed or inaccurate indoors, in tunnels, or with weak satellite reception. For actual vehicle speed, integrate the specific head unit CAN/MCU protocol or a compatible OBD-II adapter.
- Trip distance accumulates only while AeroDrive is running and receiving location updates; it is not saved across app restarts in this starter build.
- Weather comes from Open-Meteo and requires internet. If unavailable, the original dashboard artwork remains visible under the overlay.
- The original image contains static labels and decorative artwork. Dynamic values are layered over the changing fields without changing the overall design.
- The exact original background artwork is stretched to the screen ratio to fill 1280×800, as requested.

## Compatibility
Android 6.0+ (API 23+), with a modern Android WebView. Actual app shortcuts depend on which apps are installed by the head-unit manufacturer.

## Target head unit
Prepared for the Philips Android 9 head unit shown by the user: 1280×800 display, 2 GB RAM, 64 GB storage, CVD1810-WJ MCU. The app uses the touchscreen and standard Android intents; it does not change factory/CAN settings.
