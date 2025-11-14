 ### Download a better [shell](https://github.com/ohmyzsh/ohmyzsh)
 You will have to follow steps to download `zsh`, then you can install `oh-my-zsh`.

If yo u want to learn about what a shell is an what a terminal is i wrote a [[Shell configuration|blurb about it]]. Mostly all you need to know is that to edit any setting you just need to edit the `~/.zshrc` file.

## Use a custom path for the tmux config file
```zsh
alias tmux='tmux -f ~/.config/tmux/tmux.conf'
```

## Setting up sshd to autostart on home networks
I like to do this so that i can easily tranferfiles from my desktop pc to my other one, or just test linux commands or whatever
[[auto-sshd]]
