# Oh My Posh Configuration Guide

[Oh My Posh](https://ohmyposh.dev/) is a prompt theme engine for any shell. It is installed automatically as part of the `tools.winget` configuration in this project.

## 1. Install Nerd Fonts (Required for Icons)
Oh My Posh themes use special glyphs provided by [Nerd Fonts](https://ohmyposh.dev/docs/installation/fonts). To ensure your prompt displays correctly:

- Download and install the Meslo Nerd Font automatically by running the following command in PowerShell:

  ```powershell
  oh-my-posh font install Meslo
  ```

- Alternatively, download a Nerd Font from the [Nerd Fonts download page](https://www.nerdfonts.com/font-downloads) or use the [Oh My Posh font guide](https://ohmyposh.dev/docs/installation/fonts).
- Install the font on your system.
- Set your terminal (e.g., Windows Terminal, VS Code, or PowerShell) to use the installed Nerd Font.

## 2. Configure Your Shell Prompt
After installation, you need to configure your shell to use Oh My Posh. See the [official prompt setup guide](https://ohmyposh.dev/docs/installation/prompt) for detailed instructions for your shell.

### PowerShell Setup Steps
1. Open your PowerShell profile in Notepad (this will create the file if it does not exist):
   ```powershell
   notepad $PROFILE
   ```
2. Add the following line to the profile file, then save and exit Notepad:
   ```powershell
   oh-my-posh init pwsh --config ~/jandedobbeleer.omp.json | Invoke-Expression
   ```
3. In Windows Terminal, select a Nerd Font you have installed (such as Meslo) for your PowerShell profile.
4. Reload your profile to apply the changes:
   ```powershell
   . $PROFILE
   ```

You can choose a different theme or create your own. See [Oh My Posh themes](https://ohmyposh.dev/docs/themes) for options.

## 3. Verify Installation
Restart your terminal. You should see a new, styled prompt. If icons or glyphs do not appear correctly, double-check your font settings.

## References
- [Oh My Posh Installation: Fonts](https://ohmyposh.dev/docs/installation/fonts)
- [Oh My Posh Installation: Prompt](https://ohmyposh.dev/docs/installation/prompt)
- [Oh My Posh Themes](https://ohmyposh.dev/docs/themes)
