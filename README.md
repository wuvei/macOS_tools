# macOS_tools
Few useful tools for macOS

## Open iTerm2 or Terminal in current Folder

- Open the Script - either [open_terminal.scpt](open_iterm2_terminal/open_terminal.scpt) or [open_iTerm2.scpt](open_iterm2_terminal/open_iTerm2.scpt) , and then choose **File** -> **Export**

  ![open_script](images/open_iterm2_terminal/open_script.png)

- Choose export as **Application**, and put it anywhere you like. Then **Save**.

  ![export_as_app](images/open_iterm2_terminal/export_as_app.png)

- (Optional) You can change the icon of your app: Find your app, then right click on it and choose **Show Package Contents**. Go into Contents/ , and use a text editor to open info.plist, you can find the item with icon name. Then you can edit it and put yours in the **Resources** directory, or you can just place yours in it and rename it as **[applet.icns](/images/open_iterm2_terminal/appleticns)**.

  ![edit_icon_name](images/open_iterm2_terminal/edit_icon_name.png)

- Finally, find your app, then press and hold the **Command** key, drag your app to the tool bar. Then we're done! Whenever you want to open iTerm2 or Terminal in the current directory, just click on it.

  ![place_on_bar](images/open_iterm2_terminal/place_on_bar.gif)

## Keyboard Mapping: Karabiner-Elements
Karabiner-Elements is a powerful utility for keyboard customization on macOS Sierra (10.12) or later. Since programmers prefer machanical keyboards and most of those keyboards are for windows, Karaviner-Elements becomes a great software solution.

[official site](https://pqrs.org/osx/karabiner/)

[github](https://github.com/tekezo/Karabiner-Elements)

## Remove Java JDK and Install via brew cask
###Remove:
Refer to the [Link](https://stackoverflow.com/questions/19039752/removing-java-8-jdk-from-mac)
Run this command to just remove the JDK:
```
sudo rm -rf /Library/Java/JavaVirtualMachines/jdk<version>.jdk
```
Run these commands if you want to remove plugins:
```
sudo rm -rf /Library/PreferencePanes/JavaControlPanel.prefPane
sudo rm -rf /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin
sudo rm -rf /Library/LaunchAgents/com.oracle.java.Java-Updater.plist
sudo rm -rf /Library/PrivilegedHelperTools/com.oracle.java.JavaUpdateHelper
sudo rm -rf /Library/LaunchDaemons/com.oracle.java.Helper-Tool.plist
sudo rm -rf /Library/Preferences/com.oracle.java.Helper-Tool.plist
```
### Install Java JDK via brew cask
Refer to this [Link](https://stackoverflow.com/questions/24342886/how-to-install-java-8-on-mac)
```
brew tap caskroom/versions
brew cask install java8
```
To get a list of all older versions of java: `brew tap caskroom/versions` and then use `brew search java`.



## Latex

If you do not want to install 3G MacTex, you could:
### Install BasicTex
Download BasicTex From [official site](http://www.tug.org/mactex/morepackages.html)
Or
```
brew cask install basictex
```
### Install MacTex-without-gui
If you install BasicTex, you would be bothered by having to install dependency packages when needed. Or you can
```
brew cask install mactex-no-gui
```

After that, you should add it to the `path`
```
export PATH=/usr/local/texlive/2017basic/bin/x86_64-darwin:$PATH
```
### Update and Install Packages
```
sudo tlmgr update --self --repository http://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/tlnet
sudo tlmgr install latexmk --repository http://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/tlnet

```

[Reference](https://www.ouyangsong.com/posts/57080/)