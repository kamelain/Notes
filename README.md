# Mac Setting 
## Terminal Setting with ZSH, Oh My Zsh and Powerlevel10k
### Zsh + iTerm2 + Powerlevel10k
> [簡單快速的 Zsh + iTerm2 + Powerlevel10k 設定教學](https://jumping-code.com/2024/04/30/mac-terminal-settings/) (簡化指令, VSCode 問題排除)
> [Apple Silicon MacOS 開發者環境設置流程](https://shuwn.dev/2022/12/13/apple_silicon_macos_開發者環境設置流程/#google_vignette) (圖示安裝詳解)
#### 簡介
- Why use these? 方便、美觀
- ZSH（Z Shell）
    - 是一種 Unix Shell，提供了比傳統的 Bash Shell 更豐富的功能
    - 功能：自動補全、命令歷史管理、主題支持，允許自定義環境、支持多種插件和擴展
- Oh My Zsh
    - 用於管理 ZSH 配置
    - 提供了插件和主題，簡化了 ZSH 配置過程
- iTerm2
    - macOS 上的一款終端模擬器，提供了比內建終端更多的功能
    - 功能：分割窗格、標籤頁、顏色主題、字體，允許自定義選項，包括對顯示圖標和字體
- Powerlevel10k (ZSH 主題)
    - 速度、美觀
    - 自定義提示符的外觀，包括顯示 Git 狀態、當前目錄等信息

#### 安裝
- 預備環境：MacOS with Homebrew, Git
- Install
```
# zsh
brew install zsh

# oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# iterm2
brew install iterm2

# Poserlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
- Setting
```
# open .zshrc, edit zsh theme
vi ~/.zshrc
(vi) ZSH_THEME="powerlevel10k/powerlevel10k"

# restart shell
exec $SHELL

# setup p10k configure at first time, or by manual as below
p10k configure
```
- Plugins Install
```
# zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh-z
git clone https://github.com/agkozak/zsh-z $ZSH_CUSTOM/plugins/zsh-z
```
- Plugins Setting
```
# open .zshrc, edit zsh theme
vi ~/.zshrc
(vi) plugins=(git zsh-autosuggestions zsh-syntax-highlighting zsh-z) 
(vi)bindkey '^I' autosuggest-accept

# restart shell
exec $SHELL
```
