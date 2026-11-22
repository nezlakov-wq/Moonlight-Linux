# Moonlight Linux

A lightweight Debian Live system for x86-64. Desktop: Openbox + Tint2 + Conky + PCManFM.

## Desktop layout
- No Moonlight title/logo on the desktop.
- Large digital clock and date at the top center.
- Full-width taskbar along the bottom edge.
- Minimal dark blue moon wallpaper.

## Build in the cloud
1. Push these files to the default branch (normally `main`).
2. Open the repository's **Actions** tab.
3. Select **Build Moonlight Linux ISO**.
4. Click **Run workflow** and confirm.
5. Wait for the workflow to finish successfully.
6. Open the completed run and download the `Moonlight-Linux-ISO` artifact.

The workflow builds a Debian Live hybrid ISO using a Debian Trixie container and stores it as a GitHub Actions artifact for 7 days.

## Target hardware
- amd64 / x86-64
- 1 GB RAM is the design target; actual performance depends on hardware and applications.
- No installer is included in this initial live image.

## Important
This repository contains the build recipe. An ISO only exists after a successful Actions run. Test the downloaded ISO in a virtual machine before writing it to USB or using it on a physical computer. Writing an ISO to a USB drive erases that drive.
