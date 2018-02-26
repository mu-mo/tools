# Ubuntu 美化笔记

参考：http://www.jianshu.com/p/4bd2d9b1af41

## 主题美化篇

美化效果如图：

![Imgur](https://camo.githubusercontent.com/86bb278f4b6dd119f904884fd7a47b1a7367a91a/687474703a2f2f692e696d6775722e636f6d2f4d3579786767512e706e673f31)

1. 安装unity-tweak-tool
   *相信很多人都已经看出来了, 我肯定是要借助unity-tweak-tool来进行设置的*

   ```
   sudo apt-get install unity-tweak-tool
   或者
   wget -q -O - http://archive.getdeb.net/getdeb-archive.key | sudo apt-key add -
   sudo sh -c 'echo "deb http://archive.getdeb.net/ubuntu xenial-getdeb apps" >> /etc/apt/sources.list.d/getdeb.list'
   sudo apt-get update
   sudo apt-get install ubuntu-tweak
   ```

   > **顺带装一下优化工具gnome-tweak-tool**
   > *gnome-tweak-tool的话主要是用来设置开机自启, 当然它还有很多其它作用, 顺带一提Flatabulous的黑色主题可以在这里开启*

   ```
   sudo apt-get install gnome-tweak-tool
   ```

2. **Flatabulous**

   **一个久负盛名的扁平化主题**

   1. Using the .deb file for Debian, Ubuntu and derivatives (Recommended)

   Download the .deb file from [here](https://github.com/anmoljagetia/Flatabulous/releases/latest), double click to open with Ubuntu Software Center and click on install. Then, install the theme using ubuntu-tweak.

   2. Using the noobslab PPA

      ```
      sudo add-apt-repository ppa:noobslab/themes
      sudo apt-get update
      sudo apt-get install flatabulous-theme
      ```

3. numix-gtk-theme

   ```
   sudo add-apt-repository ppa:numix/ppa
   sudo apt-get update
   sudo apt-get install numix-gtk-theme numix-icon-theme-circle
   ```

4. Flat Icons

   For icons, I use the ultra-flat-icons theme. It is available in blue (recommended), orange and mint green colors. To install this, you can run the following commands

   ```
   sudo add-apt-repository ppa:noobslab/icons
   sudo apt-get update
   sudo apt-get install ultra-flat-icons
   ```

   Alternatively, you could also run `sudo apt-get install ultra-flat-icons-orange` OR `sudo apt-get install ultra-flat-icons-green`.

   ​

   安装完成后，打开unity-tweak-tool软件，修改主题和图标：

   进入Theme，修改为Flatabulous

   ![主题](https://ww3.sinaimg.cn/large/006tNc79gw1fbkgfuq6wej30op04q74o.jpg)

   ​

   ![图标](https://ww3.sinaimg.cn/large/006tNc79gw1fbkgfz2yl3j30oj0bwq3n.jpg)

   ​

   #### [Ultra-Flat主题中显示搜狗拼音托盘图标](http://www.itwendao.com/article/detail/394911.html)

5. 字体

   ubuntu自带的字体不太好看，所以采用文泉译微米黑字体替代，效果会比较好，毕竟是国产字体！

   ```
   sudo apt-get install ttf-wqy-microhei
   ```

   然后通过unity-tweak-tool来替换字体：

   ![替换字体](https://ww2.sinaimg.cn/large/006tNc79gw1fbkgfy0a7ij30oh0i375e.jpg)

6. cairo dock

   TODO

   ​

## 终端篇

1. zsh

   终端采用zsh和oh-my-zsh，既美观又简单易用，主要是能提高你的逼格

   zsh: https://github.com/robbyrussell/oh-my-zsh

   效果：

   ![img](http://www.linuxidc.com/upload/2016_09/160913082516472.png)

   1. 安装zsh：

      ```
      sudo apt-get install zsh
      ```

   2. 下载 oh-my-zsh 项目来帮我们配置 zsh

      ```
      sudo wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
      ```

   3. 切换到 zsh 模式

      ```
      chsh -s /bin/zsh
      ```

   4. 修改配色

      ![img](http://www.linuxidc.com/upload/2016_09/160913082516471.png)

      其中，文字和背景采用系统主题，透明度设为10%，下面的palette样式采用Tango

      ​

      Zsh安装配置指南 <http://www.linuxidc.com/Linux/2013-09/90377.htm>

      使用 Zsh 的九个理由 <http://www.linuxidc.com/Linux/2013-05/84191.htm>

      Zsh使用心得三则 <http://www.linuxidc.com/Linux/2012-08/67735.htm>

      Linux下安装终极Shell Zsh <http://www.linuxidc.com/Linux/2012-08/67734.htm>

2. fish

   github: https://github.com/oh-my-fish/oh-my-fish

   1. 安装fish

      Ubuntu 安装fish 并且设为默认shell

      ```
      sudo apt install fish
      chsh -s $(which fish)
      ```

      **解释:**

      chsh -s 后面加路径 ： 设置当前用户默认shell
      which fish ：查看fish程序的路径
      chsh -s $(which fish) : 设置fish为当前用户默认shell

   2. 安装oh my fish

      ```
      curl -L https://github.com/bpinto/oh-my-fish/raw/master/tools/install.sh | sh
      ```

      theme: https://github.com/oh-my-fish/oh-my-fish/blob/master/docs/Themes.md
      个人使用： robbyrussell

   **注：你在bash里面配置的环境变量可能会失效，这时候要在～/.config/fish文件夹下的修改config.fish文件，config.fish就相当于bash下的.bashrc。**

   eg: 配置golang环境变量

   ​     bash下：.bashrc 最后一行加上  `export PATH=$PATH:/usr/local/go/bin`

   ​     fish下：config.fish最后一行加上  `set -x PATH {$PATH}/usr/local/go/bin`

## Vim篇

https://github.com/amix/vimrc