# MAC常用的操作学习



### 1. mac安装brew

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
#安装brew cask
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" < /dev/null 2> /dev/null ; brew install caskroom/cask/brew-cask 2> /dev/null
```

### 2. Chrome常用快捷键

- 开启开发者模式 option + command + I
- 强制刷新 command + shift + r
- 清理缓存 command + shift + del

### 3. 安装redis相关

```shell
#安装redis
brew install redis
#安装redis-manage
brew cask install rdm
```

### 4. dock栏隐藏和弹出动画速度修改

```shell
#修改Dock动画速度到0.5秒:
defaults write com.apple.dock autohide-time-modifier -float 0.5;killall Dock
#恢复默认设置:
defaults delete com.apple.dock autohide-time-modifier;killall Dock
```

### 5. 访达显示完整路径

```shell
# 修改显示方式
defaults write com.apple.finder _FXShowPosixPathInTitle -bool TRUE;killall Finder
# 恢复默认显示方式：
defaults delete com.apple.finder _FXShowPosixPathInTitle;killall Finder
```

### 6. 完美软件推荐

- Alfred

  蝙蝠侠的完美助手。

- Snipaste 「截图贴图软件」

  截图、贴图、取色不要太好用。

- Magnet「桌面窗口整理软件」

  > ​	有没有这样的场景，同时打开多个窗口，左上角是idea，右上角是网页预览，左下角API，右下角再来个音乐，窗口需要拖拽到合适大小和位置。
  >
  > ​	这块软件就是管理窗口的，几个快捷键可以轻松完成上述功能，无需再拖来拖去，费时费力。

- Keka「解压软件」

  - 不仅可以压缩还可以解压；

  + 压缩和解压支持多种格式，常见zip，7z，tar等均支持

  + 压缩时可以设置排除mac下默认的.Dsg资源文件。windows下解压后会干净很多。

- IINA「超好用的播放器软件」

  + 一款各种格式视频都能播放的纯粹软件，界面干净清爽。

  + 可以支持网页流媒体播放。

- Downie3「从数千个不同的站点轻松下载视频」

- cheat shit 「快捷键软件」

- Bob「完美的翻译软件，支持截图直接翻译」

### 7. MAC录屏

​	CMD+SHIFT+5 启动quicktime进行录屏

