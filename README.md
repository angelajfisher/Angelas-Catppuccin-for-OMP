## Angela's Catppucin for Oh My Posh


### About

This is my personalized version of the Catppucin aesthetic for [Oh My Posh](https://github.com/JanDeDobbeleer/oh-my-posh) (OMP), tailored specifically for Windows Powershell. Using the look and palette from the official [Catppucin theme](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/catppuccin.omp.json), I customized the blocks to be more succinct while also providing more detail.

![Example1](/Screenshots/Example1.PNG)


### Highlights

- Python virtual environment support (read my installation instructions for how to remove the original (.venv) from Powershell)
- Git tracking icons to visualize pending file changes and more
- Docker support (disclaimer: currently untested, but shouldn't have issues outside of a wonky color palette if anything)
- Status code visualization to help errors go unmissed
- Transient prompts to help keep track of command history


### Installation

Install [Oh My Posh](https://github.com/JanDeDobbeleer/oh-my-posh) via its instructions.

Edit your powershell profile (`code $PROFILE`) to add the following:
```
oh-my-posh init pwsh --config 'https://gitlab.com/angelajfisher/angelas-catppucin-for-omp/-/blob/main/angelas-catppucin.omp.json' | Invoke-Expression

$env:VIRTUAL_ENV_DISABLE_PROMPT = 1
```

Alternatively, you can download the json file and point the config to your local copy. Be sure to include the virtual environment disabling line to avoid redundant (.venv) visualizationa in your prompt.

Restart powershell and then you should be go to go! Enjoy!


### Matching My look

If you install the theme and decide you want to dive even further into the Catppucin aesthetic, consider setting up [their Windows Terminal themes](https://github.com/catppuccin/windows-terminal)! The one in my screenshot is Catppuccin Macchiato. This way, your background and all of the colored text will match the OMP theme, too :)


### Making Your Own Tweaks

I know not everyone wants a heart next to their username and others may like the segments but not the color palette. Here's some quick instructions to anyone unfamiliar with OMP themes and/or json files.

To remove the heart next to the username, change line 28 to: `"template": " {{ if .SSHSession }}\ueba9 {{ end }}\u2665 {{ .UserName }} "`

To change the color palette, change the hex values in the palette section at the bottom of the file to those of your colors of choice. No need to change the color names unless you feel comfortable doing so, as the hex values are the important part. If you change the names, you will have to alter all instances of those names within the file, of course.
