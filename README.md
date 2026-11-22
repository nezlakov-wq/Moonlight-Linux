# Moonlight Linux

A lightweight Debian Live system for x86-64, built around Openbox, Tint2, Conky and PCManFM.

## Desktop design
- Minimal dark-blue moon wallpapers; no desktop logo or title.
- Large digital clock and date at the top center, with a tiny CPU/RAM readout.
- Full-width bottom panel with Start and Settings launchers, tasks and system tray.
- Lightweight Openbox session rather than a full desktop environment.

## Included features
- **Start menu and search:** jgmenu plus dmenu application search (Super+D).
- **Control Center:** Moonlight Settings opens appearance, wallpaper, display, input, sound, network, quick toggles, power settings, software center, system monitor, file manager and screenshot tools.
- **Screen lock:** i3lock, available with Super+L.
- **Screenshots:** maim capture of a selected region or full screen; saved under Pictures/Screenshots. Print Screen opens the capture tool.
- **Clipboard history:** Parcellite tray applet, started in the background.
- **Quick toggles:** Wi-Fi, Bluetooth, sound and supported brightness controls.
- **Power saving:** display blanking presets and TLP laptop power management.
- **Welcome screen:** one-time first-session guide with keyboard shortcuts.
- **Themes and wallpapers:** LXAppearance plus three bundled vector wallpapers.
- **System monitor:** Conky CPU/RAM indicator and lxtask process monitor.
- **Login screen:** dark Moonlight LightDM GTK greeter; the live session autologs in after a short delay.
- **File manager:** PCManFM with GVFS and removable-drive support.
- **Notifications:** Dunst.
- **Built-in apps:** Mousepad, Galculator, Xarchiver, GPicView, LXTerminal, PCManFM and screenshot utility.
- **Software center:** Synaptic package manager (administrator authorization required).\n- **Driver Manager:** detects common Intel, AMD, NVIDIA, Realtek, Qualcomm/Atheros, Broadcom and MediaTek hardware; after internet is available, it downloads only the matching Debian firmware packages on demand. It does not run in the background.
- **Browser:** Opera GX Stable, installed during the ISO build from Opera's official signed Debian repository. It is available from the application menu and does not start automatically.
- **Low-memory support:** zram-tools with zstd compression and earlyoom as a last-resort memory-pressure safeguard.

## Keyboard shortcuts
- Super+L: lock screen.
- Super+D: search and launch an application.
- Super+S: open Moonlight Settings.
- Super+Q: quick toggles.
- Print Screen: screenshot capture.

## Memory-conscious design
- No GNOME, KDE, compositing effects or Electron desktop applications.
- Lightweight tools are used for locking, search, screenshots and clipboard history.
- Parcellite and a few small helpers run in the background; no heavy indexing service is used.
- TLP is enabled for laptop power management; display timeout can be adjusted from Settings.
- Opera GX is a Chromium-based browser and can consume substantial memory; on 1 GB RAM, keep only a few tabs open and close it when not browsing.
- Compressed RAM swap is configured for up to 50% of physical RAM.
- earlyoom helps avoid a complete system freeze under severe memory pressure.
- 1 GB RAM is a design target, not a guarantee: browser tabs, hardware, graphics drivers and user applications affect real usage. A browser may be too heavy for comfortable use at this memory size.

## Build in the cloud
1. Push these files to the default branch (normally `main`).
2. Open the repository's **Actions** tab.
3. Select **Build Moonlight Linux ISO**.
4. Click **Run workflow** and confirm.
5. Wait for the workflow to finish successfully.
6. Open the completed run and download the `Moonlight-Linux-ISO` artifact.

The workflow builds a Debian Live hybrid ISO in a Debian Trixie container and stores it as a GitHub Actions artifact for 7 days.

## Target hardware and limitations
- amd64 / x86-64.
- 1 GB RAM target; actual performance must be measured on real hardware.
- This is a live image recipe. It does not yet include a graphical installer or a persistent installation wizard.
- Test the ISO in a virtual machine before writing it to USB or using it on a physical computer. Writing an ISO to a USB drive erases that drive.
