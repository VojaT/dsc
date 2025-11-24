# Oh My Posh Configuration Guide

[Oh My Posh](https://ohmyposh.dev/) is a prompt theme engine for any shell. It is installed automatically as part of the `setup.winget` configuration in this project.

## 1. Install Nerd Fonts (Required for Icons)
Oh My Posh themes use special glyphs provided by [Nerd Fonts](https://ohmyposh.dev/docs/installation/fonts). To ensure your prompt displays correctly:

- Download and install the CodeNewRoman Nerd Font automatically by running the following command in PowerShell:

  ```powershell  
  oh-my-posh font install CodeNewRoman
  ```

- Alternatively, download a Nerd Font from the [Nerd Fonts download page](https://www.nerdfonts.com/font-downloads) or use the [Oh My Posh font guide](https://ohmyposh.dev/docs/installation/fonts).
- Install the font on your system.
- Set your terminal (e.g., Windows Terminal, VS Code, or PowerShell) to use the installed Nerd Font, details below.

## 2. Configure Your Windows Terminal Prompt
After installation, you need to configure your shell to use Oh My Posh. See the [official prompt setup guide](https://ohmyposh.dev/docs/installation/prompt) for detailed instructions for your shell.

### PowerShell Setup Steps
1. Run the following command in powershell
   ```powershell   
   copy .\ohmyposh.json $env:USERPROFILE\ohmyposh.json
   Set-Content -Path $PROFILE -Value 'oh-my-posh --init --shell pwsh --config ~/ohmyposh.json | Invoke-Expression'
   Install-Module -Name Terminal-Icons -Repository PSGallery -Force    
   ```
2. Configure the Windows Terminal
   In windows terminal, press ctrl +  ,
      under profiles, add the default font
      ```json
        "defaults": 
        {
            "useAtlasEngine": true,
            "font":
            {
                "face": "CodeNewRoman Nerd Font"
            }
        },
   ```
   [More Info](https://ohmyposh.dev/docs/installation/prompt)

3. Reload your profile to apply the changes:
   ```powershell
   . $PROFILE
   ```

You can choose a different theme or create your own. See [Oh My Posh themes](https://ohmyposh.dev/docs/themes) for options.

4. Verify Installation

- Restart your terminal. 
- You should see a new, styled prompt. If icons or glyphs do not appear correctly, double-check your font settings.

## 3. Configure Visual Studio Code  
   - In VS code , press  ctrl + ,
   - Goto: Users -> Features -> Terminal -> Integrated:Font family  
   - Enter "CodeNewRoman Nerd Font"


## References
- [Oh My Posh Installation: Fonts](https://ohmyposh.dev/docs/installation/fonts)
- [Oh My Posh Installation: Prompt](https://ohmyposh.dev/docs/installation/prompt)
- [Oh My Posh Themes](https://ohmyposh.dev/docs/themes)
