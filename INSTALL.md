# Installing earsynth 1.01

Close your DAW before installation. The factory bank is built into the plugin; no separate preset import is required.

## macOS

Requires macOS 12 or later. The Universal build supports Apple Silicon, including M1, and Intel.

1. Download and open the DMG.
2. Open **Install earsynth.pkg** inside the image and follow the macOS installation wizard.
3. Wait for the installation to finish, then reopen your DAW.

The installer places the ready-built plugins and bank automatically for all users, with administrator approval. Terminal, Python and compilation are not required. Installer revision 3 replaces old copies, including copies blocked by the previous installer, and keeps them in the Backups folder.

| Item | Location |
| --- | --- |
| VST3 | `/Library/Audio/Plug-Ins/VST3/Alex Ears/earsynth.vst3` |
| AU | `/Library/Audio/Plug-Ins/Components/earsynth.component` |
| Standalone | `/Applications/Alex Ears/earsynth.app` |
| User presets | `~/Library/Application Support/Alex Ears/earsynth/Presets` |
| Previous user installations | `~/Library/Application Support/Alex Ears/earsynth/Backups` |
| Previous system installations | `/Library/Application Support/Alex Ears/earsynth/Backups` |

The audio bundles use ad hoc signing. The PKG is unsigned and the release is not notarized. If macOS blocks the installer, open **System Settings → Privacy & Security → Open Anyway** for this download and confirm. Do not disable Gatekeeper globally.

If your DAW previously blocked earsynth, close it before reinstalling with this DMG. After installation, reset the earsynth entry in the DAW's plugin manager and scan again if it remains in the blocked list. This installer refreshes the Audio Unit directory after replacement.

## Windows

Requires Windows 10/11 x64.

1. Download and run **Alex_Ears_earsynth_1.01_Windows_x64_Setup.exe**.
2. Follow the setup wizard and approve the administrator prompt.
3. Reopen your DAW and rescan VST3 plugins if necessary.

| Item | Location |
| --- | --- |
| VST3 | `C:\Program Files\Common Files\VST3\Alex Ears\earsynth.vst3` |
| Standalone | `C:\Program Files\Alex Ears\earsynth\earsynth.exe` |
| User presets | `%APPDATA%\Alex Ears\earsynth\Presets` |

The installer is unsigned, so SmartScreen may show a prompt. After checking that the file came from this release, choose **More info → Run anyway** if offered. The C++ runtime is linked statically; a separate Visual C++ runtime installer is not required.

A portable ZIP is also available in the release assets. Use either the installer or the portable copy to avoid duplicate plugins. Remove an installed version through Windows **Installed apps**; user presets are preserved.

## Linux

Requires Linux x86_64, Ubuntu 22.04 or a compatible distribution.

For Debian/Ubuntu, install the `.deb` with your package manager:

```bash
sudo apt install ./Alex_Ears_earsynth_1.01_Linux_amd64.deb
```

For a per-user installation, extract the `.tar.gz`, enter its folder and run:

```bash
bash install.sh
```

| Item | DEB | tar.gz |
| --- | --- | --- |
| VST3 | `/usr/lib/vst3/Alex Ears/earsynth.vst3` | `~/.vst3/Alex Ears/earsynth.vst3` |
| Standalone | `/usr/bin/earsynth` | `~/.local/bin/earsynth` |

Use one installation method. User presets are stored in `~/.config/Alex Ears/earsynth/Presets`. The `.deb` can be removed with `sudo apt remove earsynth`; user presets are preserved.

## Checksums

`SHA256SUMS.txt` in the release lists the installer and archive checksums. On macOS use `shasum -a 256 <filename>`; on Linux use `sha256sum <filename>`; on Windows PowerShell use `Get-FileHash <filename> -Algorithm SHA256`.
