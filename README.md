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

Not so-sensible defaults:

```console
./macos/set-defaults
```

## 4. Setup SSH keys

Create a new SSH key or copy the previous one into `~/.ssh`. That should be
it.

Also fix perms:

```console
$ chmod 0600 ~/.ssh/id_rsa
```

## 5. Setup GPG signing

Create default config files:

```console
gpg --list-keys
```

Setup pinentry:

```console
$ brew install pinentry-mac
$ echo "pinentry-program /usr/local/bin/pinentry-mac" >> ~/.gnupg/gpg-agent.conf
$ killall gpg-agent
```

Import the key:

```console
$ export GPG_TTY=$(tty)
$ keybase pgp export -q C14AB940 | gpg --import
$ keybase pgp export -q C14AB940 --secret | gpg --import --allow-secret-key-import
```

> Change C14AB940 with your key id.

Setup git:

```console
$ git config --global gpg.program $(which gpg)
$ git config --global user.signingkey C14AB940
$ git config --global commit.gpgsign true
```

> Change C14AB940 with your key id.

Test it:

```console
$ mkdir -p /tmp/test
$ cd $_
$ git init
$ git commit --allow-empty -m 'signsss'
$ git log --show-signature
```

That's it!


## 6. Reboot

```console
sudo reboot
```

## 7. Profit!

:beers:
