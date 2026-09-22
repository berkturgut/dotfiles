# Dotfiles

Clean, minimal, declarative dotfiles managed with [chezmoi](https://www.chezmoi.io/).

## 🚀 Quick Start
```bash
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply <your-github-username>
```

## 📦 Packages & Tools

### System Packages (via `.chezmoidata/packages.yaml`)
- `git`
- `zsh`
- `curl`
- `ca-certificates`

### Dynamic / Standalone Tools (via Dedicated Scripts)
- `ghostty`: GPU-accelerated terminal emulator (dynamically matched to distro codename & architecture)
- `oh-my-zsh`: Community-driven Zsh configuration framework

## 🛠️ Architecture & Scripts
- `run_onchange_before_10_install_apt.sh.tmpl`: Automatically installs standard APT packages defined in `packages.yaml`.
- `run_once_before_15_install_ghostty.sh.tmpl`: Detects OS codename (Trixie, Bookworm, Noble, etc.) and architecture (amd64, arm64), downloads the matching native Ghostty `.deb`, and configures WSLg Wayland sockets.
- `run_once_before_20_install_ohmyzsh.sh.tmpl`: Installs Oh-My-Zsh unattended and sets Zsh as the default login shell.

## 🖥️ GUI & WSLg Configuration
When running inside WSL2, shell profiles (`~/.zshrc` and `~/.bashrc`) automatically detect `/mnt/wslg` and export the required Wayland/X11 environment variables:
- `XDG_RUNTIME_DIR=/mnt/wslg/runtime-dir`
- `WAYLAND_DISPLAY=wayland-0`
- `DISPLAY=:0`

This ensures native hardware-accelerated GUI applications like Ghostty launch seamlessly under WSLg without display socket errors.

## 💻 Environment & Stack
- **OS:** Debian / Ubuntu (WSL2)
- **Shell:** Zsh + Oh-My-Zsh (`robbyrussell` theme)
- **Terminal:** Ghostty (Hardware-accelerated via native WSLg)
