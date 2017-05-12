# Mac

How I setup a new Mac.

## 1. Install brew

```console
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## 2. Install deps

```console
brew bundle <( curl -fsSL https://raw.githubusercontent.com/caarlos0/mac/master/Brewfile )
```

## 3. Install dotfiles

```console
git clone https://github.com/caarlos0/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
./script/bootstrap
zsh
```

## 4. Reboot

```console
reboot
```

## 5. Profit!

:beers:
