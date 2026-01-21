# Quick Start Guide

## Structure

This repo uses `.config/` and `.local/` folders:

```
dotfiles/
├── .config/     → ~/.config/
├── .local/      → ~/.local/
├── docs/
├── LICENSE
└── README.md
```

---

## Commands

### Installing Configurations

- **Install all configs**: `stow .config .local`
- **Remove all configs**: `stow -D .config .local`
- **Preview changes**: `stow -n .config` (dry run)
- **Update existing configs**: `stow -R .config` (restow)

---

## Adding Files

1. Move file to the appropriate folder:
   ```bash
   mv ~/.config/example-config ~/dotfiles/.config/
   ```

2. Install:
   ```bash
   stow .config
   ```

---

## Troubleshooting

**File already exists?**
```bash
mv ~/.config/example-config ~/.config/example-config.backup
stow .config
```

**Check symlinks:**
```bash
ls -la ~/.config
ls -la ~/.local
```
