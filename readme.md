# 开始使用 deepin

准备使用 deepin 了，特来记录一下。

# 关于环境变量的配置

在 home/[Username] 下 可以找到 .bashrc / .profile 

![profile文件](https://i.loli.net/2019/02/23/5c70af946af58.png)

参照之前的内容，将JDK和Node和SSr配置好即可。

配置好ssr之后在系统全局代理中可以启动它。

那么如何在终端中启动ss代理呢？

# 终端中启动ss代理

![bashrc文件](https://i.loli.net/2019/02/23/5c70b0232d5c3.png)

下面这条语句添加到 .bashrc 中即可

每次修改终端的配置 需要 source ./[bashrc文件,profile文件] 

# 软件安装

软件安装分为三种

1. apt-get install 桌面版的linux不推荐，linux桌面版以用户为基本单位，所有操作均是在用户目录下执行，而apt默认需要sudo权限。

2. 二进制安装包 不推荐 理由同上 需要sudo权限，不适合用户操作

3. 二进制代码包 推荐 解压到home下，需要使用时不需要sudo权限，需要手动建立desktop文件到启动器。

以idea为例子

```
[Desktop Entry]
Version=1.0
Type=Application
Name=IntelliJ IDEA
Icon=/home/no99in/idea-IU-183.5429.30/bin/idea.svg
Exec="/home/no99in/idea-IU-183.5429.30/bin/idea.sh" %f
Comment=Capable and Ergonomic IDE for JVM
Categories=Development;IDE;
Terminal=false
StartupWMClass=jetbrains-idea
```

放在 /home/[username]/.local/share/applications 下

# 环境配置 

以Java为例，下载官网二进制代码包，解压至home下，在profile文件中写入

```sh
# set PATH so it includes JDK11 bin if it exists
if [ -d "$HOME/jdk-11.0.2/bin" ] ; then
    PATH="$HOME/jdk-11.0.2/bin:$PATH"
fi
```

终端执行 source ./.profile 输入 Java 即可看到效果

![Java](https://i.loli.net/2019/02/23/5c70b2440e8ad.png)

# 字体 

中文 ： noto sans  
等宽 ： monaco

之前我终端字体就是 monaco

