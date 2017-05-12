# Mac

How I setup a new Mac.

## 1. Install brew

```console
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## 2. Install deps

```console
git clone https://github.com/caarlos0/mac.git
cd mac
brew bundle
```

## 3. Install dotfiles

```console
git clone https://github.com/caarlos0/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
./script/bootstrap
zsh
```

## 4. Setup SSH keys

Create a new SSH key or copy the previous one into `~/.ssh`. That should be
it.

## 5. Setup GPG signing

Follow [this tutorial](https://github.com/pstadler/keybase-gpg-github)
and you should be fine.

## 6. Reboot

```console
sudo reboot
```

## 7. Profit!

:beers:
