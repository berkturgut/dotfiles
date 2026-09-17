# Dotfiles

## 🚀 Quick Start
```bash
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply <your-github-username>
```

## 📦 Packages

**Common (All OS):**
- `git`

**Fedora (fedoraremix):**
- `ghostty` (via COPR `scottames/ghostty`)

## 🛠️ Configurations Applied
- **Ghostty WSLg Integration:** Injects `XDG_RUNTIME_DIR` and `GDK_BACKEND` variables into `.bashrc` and overrides the local `.desktop` shortcut (`~/.local/share/applications/com.mitchellh.ghostty.desktop`) to resolve Wayland/X11 rendering errors when launching directly from Windows Start Menu.
