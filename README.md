# Dotfiles

Clean, minimal, declarative dotfiles managed with [chezmoi](https://www.chezmoi.io/).

## 🚀 Quick Start
```bash
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply <your-github-username>
```

## 📦 Packages

Managed centrally via `.chezmoidata/packages.yaml`:

- **Common:**
  - `git`
  - `zsh`
  - `curl`
  - `ca-certificates`

## 🛠️ Architecture & Scripts
- `run_onchange_before_10_install_apt.sh.tmpl`: Installs clean standard packages via `apt-get`.
- `run_once_before_15_install_ghostty.sh.tmpl`: Dynamically detects distribution codename (Trixie, Bookworm, Noble, etc.) and architecture (amd64, arm64) to install the exact native Ghostty build and configure WSLg Wayland sockets.
- `run_once_before_20_install_ohmyzsh.sh.tmpl`: Installs Oh-My-Zsh (unattended) and sets Zsh as the default login shell.
- **Shell:** Zsh + Oh-My-Zsh (`robbyrussell` theme)
- **Terminal:** Ghostty (GPU-accelerated via native WSLg)
