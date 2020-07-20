# dotfiles!!!!

## mac applications
- [Alfred](https://www.alfredapp.com/)
- [ShiftIt](https://github.com/fikovnik/ShiftIt) - Keyboard shortcuts for window sizes
- [CopyClip](https://itunes.apple.com/us/app/copyclip-clipboard-history/id595191960?mt=12) - Clipboard History Manager
- [new chrome window](https://github.com/rileynwong/dotfiles-old/blob/master/chrome-new-window.scpt)
  - open in applescript editor, save as application
- [remap cmd. and cmd/ to move left/right desktop](https://apple.stackexchange.com/questions/347239/change-keyboard-shorcut-for-switching-desktop-workspaces#:~:text=As%20you%20said%2C%20you%20can,new%20shortcut%20to%20record%20it)


## mac settings
- [map caps lock to esc](https://stackoverflow.com/questions/127591/using-caps-lock-as-esc-in-mac-os-x/40254864#40254864)


## vim
Should be able to just clone from this repo, but in case you have to do it from scratch:
- [Vimrc](https://github.com/amix/vimrc)
- [gruvbox vim color scheme](https://github.com/morhetz/gruvbox), [install](https://github.com/morhetz/gruvbox/wiki/Installation)
- [minimap](https://github.com/severin-lemaignan/vim-minimap)
- [nerdtree](https://github.com/preservim/nerdtree)


## shell
- [iTerm](https://www.iterm2.com/downloads.html)
  - [iTerm color schemes](https://github.com/mbadolato/iTerm2-Color-Schemes/tree/master/schemes)
  - treehouse, urple ... 
- [tmux](https://github.com/tmux/tmux) (tmx2): `$ brew install tmux`
- [Zsh](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH)
- [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)


## misc
- [Remote pbcopy over SSH (e.g. Mac sshing into Linux)](https://seancoates.com/blogs/remote-pbcopy/)
  - on mac:
    - Put the following in ~/Library/LaunchAgents/pbcopy.plist:
    ```
      <?xml version="1.0" encoding="UTF-8"?> <!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> <plist version="1.0"> <dict> <key>Label</key> <string>localhost.pbcopy</string> <key>ProgramArguments</key> <array> <string>/usr/bin/pbcopy</string> </array> <key>inetdCompatibility</key> <dict> <key>Wait</key> <false/> </dict> <key>Sockets</key> <dict> <key>Listeners</key> <dict> <key>SockServiceName</key> <string>2224</string> <key>SockNodeName</key> <string>127.0.0.1</string> </dict> </dict> </dict> </plist>
      ```
    - run: ` $ launchctl load ~/Library/LaunchAgents/pbcopy.plist`
    - can test with: `$ telnet 127.0.0.1 2224`
      - type 'hello' and exit, then try pasting.
    - On local machine, add `RemoteForward 2224 127.0.0.1:2224` to `~/.ssh/config`
  - on linux:
    - On remote, add `cat | nc -q1 localhost 2224` to `/usr/local/bin/pbcopy`
  
- [dotfiles management](https://www.atlassian.com/git/tutorials/dotfiles)
