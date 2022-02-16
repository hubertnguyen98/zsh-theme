# zsh-theme
PROJECTS LINKS I USED
1. https://github.com/robbyrussell/oh-my-zsh
2. https://github.com/bhilburn/powerlevel9k
3. https://github.com/ryanoasis/nerd-fonts
4. http://bluejamesbond.github.io/CharacterMap/

# Install ZSH!
PowerLevel9k is a prompt theme for ZSH, so we need that first!
`>_ sudo dnf install zsh`
After that, we normally want to set ZSH as our default Shell, with
`>_ chsh -s /usr/bin/zsh #SKIP THAT!`
But we don’t really need it, since Oh-My-ZSH will do it anyway!
# Install Oh-My-ZSH!
Hey, I will give the commands just for reference, but please don’t copy them! Follow the documentation on original project pages!
`>_ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
Oh-My-Zsh on Github
This will do three things
It will write on $HOME/.zshrc
It will set ZSH as default Shell
It will create $HOME/.oh-my-zsh directory that contains OMZ scripts and plugins!
Note that OMZ will ask you for auto-updates every while, so you dont really to worry about that! Also you can force to check for updates by
`>_ upgrade_oh_my_zsh`
Install PowerLevel9k!
Then it’s time to install PowerLevel9k using the OMZ way!
`>_ git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k`
PowerLevel9k on Github
Then we set it on $HOME/.zshrc. Open a text editor and set:
ZSH_THEME="powerlevel9k/powerlevel9k"
Install Nerd Fonts!
PowerLevel9k accepts lots of fonts, but Nerds are the most complete set with lots of glyphs! Get whatever font you like, but on the video above I picked Hack
Install them with GNOME Fonts App, that basically moves them on $HOME/.local/share/fonts , pick them on Tilix, and on .zshrc add:
POWERLEVEL9K_MODE="nerdfont-complete"
Customize the Prompt a Bit!
PowerLevel9k has crazy customization options, so you need to check on their wiki, but for the video I went just with:
`POWERLEVEL9K_DISABLE_RPROMPT=true
POWERLEVEL9K_PROMPT_ON_NEWLINE=true
POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="▶ "
POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX=""`
Which is very explanatory, what each option does!
A Hint!
To see fonts glyphs and Unicodes this is a very nice webApp! Im using it on video at 5:04
Create a Custom Segment!
PowerLevel9k has an insane lots out of box segments, but if we want to add a custom one, in this case just our distro logo we can do
`POWERLEVEL9K_CUSTOM_FEDORA_ICON="echo <unicode logo icon> "
POWERLEVEL9K_CUSTOM_FEDORA_ICON_BACKGROUND=069
POWERLEVEL9K_CUSTOM_FEDORA_ICON_FOREGROUND=015`
And then add the segment on the prompt
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(custom_fedora_icon context dir vcs)
$CONTEXT displays username/hostname
$DIR displays the current working directory, that we can even trim path if we want!
$VCS displays the Git status in case we are inside a Git repository
For the context there are segments like {battery, background_jobs, ip and lots more}
To check for available colors (background/foreground)
>_ for code ({000..255}) print -P -- "$code: %F{$code}This is how your text would look like%f"
We can colorize any segment we want, and we can even override any icons we want! anyway, check on their Github!
