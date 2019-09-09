<h1>Configuring a VM for Haskell Development</h1>

*September 2019*

I followed these instructions to configure a virtual machine running on virtual box on my windows machine for Haskell development.

- [Virtual Box](#virtual-box)
- [Haskell Platform](#haskell-platform)
- [ZSH](#zsh)
- [VS Code](#vs-code)
- [Configure the VS Code Terminal to Work with ZSH](#configure-the-vs-code-terminal-to-work-with-zsh)
- [Haskell Extensions for VS Code](#haskell-extensions-for-vs-code)
- [Configure Git](#configure-git)

## Virtual Box
Configure a Ubuntu instance of at least 16 gigabytes in size. 

## Haskell Platform

```bash
sudo apt-get install haskell-platform
```

This doesn't seem to come with stack on Linux, it does on windows. Install stack manually:

```bash
curl -sSL https://get.haskellstack.org/ | sh
```

## ZSH
```bash
sudo apt-get install zsh
```
https://github.com/robbyrussell/oh-my-zsh

Make zsh the default shell by adding this to your `~/.bashrc`: 
```bash
# Switch to ZSH shell
if test -t 1; then
    exec zsh
fi
```

In `~/.zshrc` change the theme from `robbyrussel` to `agnoster`. Also add `DEFAULT_USER=$USER` in order to remove the main user from always appearing in the prompt.

For this theme to render properly, install powerline fonts: 

```bash
sudo apt-get install fonts-powerline
```

## VS Code
```bash
sudo apt-get install code 
```
## Configure the VS Code Terminal to Work with ZSH
Add the following to settings.json 
```bash
"terminal.integrated.fontFamily": "'Ubuntu Mono', 'PowerlineSymbols'",
"workbench.colorCustomizations": {
        "terminal.background":"#000000",
}
```

## Haskell Extensions for VS Code 
Install [Simple GHC](https://github.com/dramforever/vscode-ghc-simple), [Haskell Language Server](https://marketplace.visualstudio.com/items?itemName=alanz.vscode-hie-server), and [haskell-ghcid](https://marketplace.visualstudio.com/items?itemName=ndmitchell.haskell-ghcid) by following each of their instructions. 

## Configure Git
We need to setup git to work with our repositories. 