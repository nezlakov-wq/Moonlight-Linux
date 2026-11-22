# Moonlight Linux

A lightweight Debian Live system for x86-64, built around Openbox, Tint2, Conky and PCManFM.

## Desktop design
- Minimal dark-blue moon wallpapers; no desktop logo or title.
- Large digital clock and date at the top center, with a tiny CPU/RAM readout.
- Full-width bottom panel with Start and Settings launchers, tasks and system tray.
- Lightweight Openbox session rather than a full desktop environment.

## Included features
- **Start menu:** jgmenu, opened from the Start launcher on the bottom panel.
- **Control Center:** Moonlight Settings opens appearance, wallpaper, display, input, sound, network, system monitor and file manager tools.
- **Themes and wallpapers:** LXAppearance plus three bundled vector wallpapers.
- **System monitor:** Conky CPU/RAM indicator and lxtask process monitor.
- **Login screen:** dark Moonlight LightDM GTK greeter; the live session autologs in after a short delay.
- **File manager:** PCManFM with GVFS and removable-drive support.
- **Notifications:** Dunst.
- **Built-in apps:** Mousepad, Galculator, Xarchiver, GPicView, LXTerminal, PCManFM and screenshot utility.
- **Browser:** Opera GX Stable, installed during the ISO build from Opera's official signed Debian repository. It is available from the application menu and does not start automatically.
- **Low-memory support:** zram-tools with zstd compression and earlyoom as a last-resort memory-pressure safeguard.

## Memory-conscious design
- No GNOME, KDE, compositing effects or Electron desktop applications.
- Opera GX is a Chromium-based browser and can consume substantial memory; on 1 GB RAM, keep only a few tabs open and close it when not browsing.
- Notifications and desktop widgets use small background services.
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

