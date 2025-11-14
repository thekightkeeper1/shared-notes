# Shell vs terminal
A shell is a program on your computer that executes commands. A terminal is a program that opens up a gui which interacts with the shell. A shell can tell your terminal to display a color by returing a string with special formatting characters:
```bash
echo -e "\e[31mThis text is red.\e[0m"
echo -e "\e[32mThis text is green and \e[1mbold.\e[0m"
```

But if the terminal does not support colors, then the text will be plain white.  You can do `echo $TERM` to see what terminal you are using. It should also have `256color` somehwhere in the name, which programs can actually use that variable name to detect whether or not the terminal (gui)

As a terminal I run whatever the default linux mint one is. Idk what its called tbh. But then inside of that i run a second terminal called tmux. Tmux lets you have mutiple windows and panes, and lets you do lots of multitasking so thats why i use it.

`bash` is the default shell for like every linux system on earth. `zsh` has more configuration options, and `oh-my-zsh` is a way to automatically configure all of those settings with themes and configuration files


## Editing configuration
Everything shell-configuation wise starts with a file endinng in `rc`. For bash this is `.bashrc`. For z-shell it is `.zshrc`.  All configuration could technically be done in this one file, things are broken off into other files just for modularity.

The `.zshrc` file can be modified to change your prompt, for example. ![[Pasted image 20251114124209.png]]
The above was obtained by editing
```bash
# Set name of the theme to load --- if set to "random", it will
# load a random theme each time Oh My Zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="random"
```
Since it was random it will just do any random one

[Here](https://dev.to/cassidoo/customizing-my-zsh-prompt-3417) is a link to a guide to customizing your own prompt. There are probably way more things that you can do but that is a start

