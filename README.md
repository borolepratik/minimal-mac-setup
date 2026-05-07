# minimal-mac-setup

## install software
```bash
# homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

brew install asdf btop cargo-binstall cmake coreutils fastfetch git openssl@3 pnpm readline rsync uv xz readline

brew install --cask bitwarden flameshot ghostty insomnia responsively 1password spotify slack brave-browser sublime-text localsend whatsapp gitkraken notion notion-calendar libreoffice altair-graphql-client visual-studio-code cursor antigravity discord firefox multiviewer gitbutler iina cyberduck macs-fan-control mullvad-vpn lm-studio meld

brew install jesseduffield/lazydocker/lazydocker

# rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
cargo binstall cargo-outdated

# oh my zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
- install powerlevel10k (zsh theme) - https://github.com/romkatv/powerlevel10k

```sh
# install nodejs and python via asdf
asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
asdf install nodejs 24.15.0
asdf set -u nodejs 24.15.0

asdf plugin add python https://github.com/asdf-community/asdf-python.git
asdf install python 3.14.4
asdf set -u python 3.14.4
```

- install docker desktop
- install rectangle pro, aldente pro from https://www.macbed.com/


## ghostty xterm config
add `SetEnv TERM=xterm-256color` to host config in `~/.ssh/config` for ghostty


## install omz plugins
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-completions.git ~/.oh-my-zsh/custom/plugins/zsh-completions

git clone https://github.com/zsh-users/zsh-history-substring-search.git ~/.oh-my-zsh/custom/plugins/zsh-history-substring-search
```


## add to ~/.zshrc
```zsh
plugins=(
    git
    docker
    macos
    zsh-autosuggestions
    zsh-completions
    zsh-history-substring-search
    zsh-syntax-highlighting
)

alias cls="clear"
alias brewup="brew update && brew upgrade && omz update"
alias lzd="lazydocker"
alias rsync=/opt/homebrew/bin/rsync

export PATH="$HOME/.local/bin:$PATH"

# asdf
export PATH="${ASDF_DATA_DIR:-$HOME/.asdf}/shims:$PATH"

# Cypress
export CYPRESS_CRASH_REPORTS=0

# ruby via brew
export PATH="/opt/homebrew/opt/ruby/bin:$PATH"
export PATH="/opt/homebrew/lib/ruby/gems/3.4.0/bin:$PATH"
```
