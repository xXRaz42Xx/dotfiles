# Dotfiles

Welcome to my dotfiles repository! This collection contains my personal configuration files for various tools and applications, organized for easy deployment across different systems using GNU Stow.

## Overview

This repository stores my personal configuration files (dotfiles) in a structured way to make it easy to deploy them across different machines. The configurations are organized in the standard XDG directory structure with `.config/` and `.local/` folders.

## Structure

```
dotfiles/
├── .config/     → ~/.config/
├── .local/      → ~/.local/
├── docs/
├── LICENSE
└── README.md
```

## Prerequisites

Before using these dotfiles, ensure you have [GNU Stow](https://www.gnu.org/software/stow/) installed:

- On macOS: `brew install stow`
- On Ubuntu/Debian: `sudo apt-get install stow`
- On Arch Linux: `sudo pacman -S stow`
- On FreeBSD: `pkg install stow`

## Installation

To install all configurations:

```bash
cd ~/dotfiles
stow .config .local
```

This will create symbolic links from the files in this repository to their appropriate locations in your home directory.


## Adding New Configurations

1. Move the configuration file/folder to the appropriate location:
   ```bash
   mv ~/.config/example-config ~/dotfiles/.config/
   ```

2. Install using stow:
   ```bash
   cd ~/dotfiles
   stow .config
   ```

## Git Workflow

This repository follows a branching workflow for safer experimentation:

- **Main branch (`main`)**: Contains stable, tested configurations ready for use
- **Feature branches**: Used for experimenting with new configurations
- **Tags**: Used for major configuration milestones

For more detailed information about the git workflow, see [docs/GIT_WORKFLOW.md](docs/GIT_WORKFLOW.md).

## Troubleshooting

**If a file already exists:**
```bash
mv ~/.config/example-config ~/.config/example-config.backup
stow .config
```

**To check if symlinks were created properly:**
```bash
ls -la ~/.config
ls -la ~/.local
```

For more troubleshooting tips, see [docs/QUICKSTART.md](docs/QUICKSTART.md).

## License

See [LICENSE](LICENSE) for licensing information.
