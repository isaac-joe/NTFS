# 启用 MacOS 自动读写 NTFS

FUSE for OS X + NTFS-3G 的一次性解決方案

https://github.com/isaac-joe/NTFS


[繁體中文](https://github.com/isaac-joe/NTFS/blob/master/README-zhcn.md) | [简体中文](https://github.com/isaac-joe/NTFS/blob/master/README-zhcn.md)



### 适用 MacOS 版本
OS X 10.11 El Capitan, macOS 10.12 Sierra 以及
 macOS 10.13 High Sierra.

###开始之前
你需要的熟练的技术有

1. Recovery Mode 回复模式，学习连结：
https://support.apple.com/zh-cn/HT201314

2. 执行终端机指令
3. 安装 Homebrew ，学习连结：
https://brew.sh/index_zh-cn.html

若上述步骤无法完成，或者并非 100% 确定；
请直接放弃，并招唤工具国 🤹‍♂️
让工具人一起为您的 Mac 健康把关！


 #就是好工具 #就是好工具 #就是好工具

> # 开始


#### 1. 安装 FUSE for OS X + NTFS-3G

终端机执行 2 个指令：

`
brew cask install osxfuse
brew install ntfs-3g
`

#### 2. 解除 “系统完整保护”，开启NTFS 读写能力 

Rovery Mode 终端机指令：

`csrutil disable`

正常开机，终端机指令：
`
sudo mv /sbin/mount_ntfs /sbin/mount_ntfs.original
sudo ln -s /usr/local/sbin/mount_ntfs /sbin/mount_ntfs
`
再到 Rovery Mode 终端机指令：

`csrutil enable`

关闭视窗后重新开机，便开启 NTFS 读写功能。

