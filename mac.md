## mac based setup (apple silicon)

### system
    $ sudo softwareupdate --install-rosetta --agree-to-license
    $ sudo scutil --set HostName mac
    $ defaults write com.apple.screencapture type jpg
    $ defaults write com.apple.dock autohide-delay -float 0; defaults write com.apple.dock autohide-time-modifier -int 0;killall Dock
    $ zip -er project.zip ./folder_to_zip/

### app store
    - xcode
    - magnet
    - noizio
    
### from zsh to bash
    $ chsh -s /bin/bash
    $ cd && touch .hushlogin

### ~/.bash_profile
    export BASH_SILENCE_DEPRECATION_WARNING=1
    alias vpn="sudo openconnect -v --authgroup d.velop -u ekai webvpn.d-velop.de"

    export CLICOLOR=1
    alias ls='ls --color=auto'
    alias ll='ls -lah --color=auto'
    alias grep='grep --color=auto'
    
    alias fire='vlc --intf dummy ~/aa_fire.mp3 --gain=0.4'
    alias thunder='vlc --intf dummy ~/aa_thunder.mp3 --gain=0.15'

    git_branch() {
        git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
    }
    export PS1="\n\[\e[00;32m\]\u\[\e[00;32m\]@\[\e[00;32m\]\h\[\e[00;38m\] \[\e[0;33m\]\w\[\e[00;37m\] \[\033[00;35m\]\$(git_branch):\n$ \[\e[0m\]"

    alias intelbrew='arch -x86_64 /usr/local/homebrew/bin/brew'
    export PATH=/usr/local/Homebrew/bin:$PATH
    
    alias armbrew='/opt/homebrew/bin/brew'
    export PATH=/opt/homebrew/bin:$PATH
    
    export PATH="/usr/local/homebrew/opt/php@8.0/bin:$PATH"
    export PATH="~/.composer/vendor/bin:$PATH"
    export PATH="/usr/local/homebrew/opt/openjdk/bin:$PATH"
    export JAVA_HOME="/usr/local/homebrew/opt/openjdk"
    
    export PATH="$HOME/.rbenv/bin:$PATH"
    export PATH="$HOME/.nodenv/bin:$PATH"
    export PATH="$HOME/.pyenv/bin:$PATH"
    eval "$(rbenv init -)"
    eval "$(nodenv init -)"
    eval "$(pyenv init -)"
 
#### install and setup tooling
##### rbenv
    $ rbenv install 3.1.2 && rbenv global 3.1.2 && rbenv rehash
##### nodenv
    $ nodenv install 16.0.0 && nodenv global 16.0.0 && nodenv rehash
##### pyenv
    $ pyenv install 3.10.5 && pyenv global 3.10.5 && pyenv rehash
##### rails, npm libs and laravel
    $ gem install rails
    $ npm install -g nodemon @vue/cli    
    $ composer global require laravel/installer
    
