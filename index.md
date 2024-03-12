# AOSP
## 环境要求
### 硬件
处理器：2.3.x以上Android版本需要64位架构的处理器

内存：官方最低16G，谷歌推荐64G；实测虚拟机32G以下内存有概率崩溃，物理机没问题，虚拟机建议至少40G内存

硬盘：代码250G，编译再加150G，建议500G以上SSD

网络：保证网络稳定，否则检出代码很容易中断

参考：虚拟机+i5 10700 + 32G内存+SSD，检出代码约4小时，编译、链接、打包约3.5个小时

### 软件
Ubuntu 22.04 LTS x64
JDK AOSP自带
Make AOSP自带
Python 3

``` shell
sudo apt install git-core gnupg flex bison build-essential zip curl zlib1g-dev libc6-dev-i386 libncurses5 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z1-dev libgl1-mesa-dev libxml2-utils xsltproc unzip fontconfig
```

以上都是针对Android9.0及以上版本的环境配置

## 下载代码
清华源：https://mirrors.tuna.tsinghua.edu.cn/help/AOSP/

科大源：https://mirrors.ustc.edu.cn/help/aosp.html

谷歌官方的方法不适合国内，参考
https://source.android.google.cn/docs/setup/download/downloading

> 以下两种方法说明摘自清华源站：

### 方法一：
以下是推荐的国内下载代码方法

> 初始同步方法
> 
> 第一次同步数据量特别大，如果网络不稳定，中间失败就要从头再来了。所以我们提供了打包的 AOSP 镜像，为一个 tar 包，大约 200G（单文件 200G，注意你的磁盘格式要支持）。这样你 就可以通过 HTTP(S) 的方式下载，该方法支持断点续传。
> 下载地址 https://mirrors.ustc.edu.cn/aosp-monthly/, 请注意对比 checksum。
> 
> 然后根据下文，替换已有的AOSP源代码的remote 的方法更改同步地址。解压后用命令 repo sync 就可以把代码都 checkout 出来。
> 
> Note: tar 包为定时从 https://mirrors.tuna.tsinghua.edu.cn/aosp-monthly/ 下载。


### 方法二：

> 如果想用官方步骤+国内镜像地址的方法，将官方步骤中的 https://android.googlesource.com/ 全部使用 https://mirrors.tuna.tsinghua.edu.cn/git/AOSP/ 代替即可。
> 
> 由于使用 HTTPS 协议更安全，并且更便于我们灵活处理，所以强烈推荐使用 HTTPS 协议同步 AOSP 镜像。
> 
> 由于 AOSP 镜像造成CPU/内存负载过重，我们限制了并发数量，因此建议：sync的时候并发数不宜太高，否则会出现 503 错误，即-j后面的数字不能太大，建议选择4。请尽量选择流量较小时错峰同步。


### 分支选择

参考：https://source.android.google.cn/setup/start/build-numbers#source-code-tags-and-builds

