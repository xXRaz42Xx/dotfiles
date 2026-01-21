# Git Workflow for Dotfiles

### Main Branch (`main`)
- Contains stable, tested configurations
- Ready-to-use setup for new machines
- Only merge here after testing

### Feature Branches
- Create temporary branches for experiments:
  ```bash
  git checkout -b add-new-editor-config
  ```
- Try new configurations safely
- Easy to discard if things don't work out

### Typical Workflow

1. **Experiment with new configs:**
   ```bash
   git checkout -b try-new-zsh-theme
   # Make changes to zsh configs
   git add . && git commit -m "Try new zsh theme"
   ```

2. **Test the changes:**
   ```bash
   # Use your configs for a few days
   # See if everything works as expected
   ```

3. **Merge or discard:**
   ```bash
   # If it works, merge back:
   git checkout main
   git merge try-new-zsh-theme
   git branch -d try-new-zsh-theme
   
   # If not, just delete the branch:
   git branch -D try-new-zsh-theme
   ```

### Direct Commits to Main
- Small, tested changes can go directly to `main`
- Things you're confident about (typos, minor adjustments)

### Tags for Milestones
- Use tags for major configuration milestones:
  ```bash
  git tag -a v1.0 -m "Stable desktop setup"
  git push origin v1.0
  ```
