# 开启 MacOS 自动读写 NTFS

FUSE for OS X + NTFS-3G 的一次性解决方案

https://github.com/isaac-joe/NTFS


[繁體中文](https://github.com/isaac-joe/NTFS/blob/master/README.md) | [简体中文](https://github.com/isaac-joe/NTFS/blob/master/README-zhcn.md)


> # 开始之前

熟悉如何进入回复模式，与建立执行环境

1. 如何 进入 MacOS 回复模式 Recovery Mode   
https://support.apple.com/zh-tw/HT201314
2. 在终端机执行指令
3. 安装 Homebrew  
https://brew.sh/index_zh-cn.html

#### 开启终端机

执行指令：


```
// 安装 osxfuse
$ brew cask install osxfuse

// 安装 ntfs-3g
$ brew install ntfs-3g
```

#### 进入 Mac 回复模式

在按下电源按钮将 Mac 开机，或在 Mac 开始重新启动之后，立即按住键盘上的 Command-R 或[其他“macOS 回复”按键组合](https://support.apple.com/zh-cn/HT204904)之一。持续按住这些按键，直到出现 Apple 标志或旋转的地球。看到工具程式视窗，即表示完成启动：

![Terminal](https://github.com/isaac-joe/NTFS/blob/master/images/terminal.png?raw=true)

进入【OS X 工具程式】后，请由上方的选单列点选【工具程式】➤【终端机】

执行指令：

```
// 解除 “系统完整保护”功能
$ csrutil disable
```

重新开机 ➤ 进入正常模式 ➤ 开启终端机，执行指令：

```
// 执行后，询问并输入登入用户的密码
$ sudo mv /sbin/mount_ntfs /sbin/mount_ntfs.original

// 指令执行后，询问并输入登入用户的密码
$ sudo ln -s /usr/local/sbin/mount_ntfs /sbin/mount_ntfs
```

重新开机 ➤ 再次进入 Mac 回复模式 ➤ 开启终端机，执行指令：

```
// 开启“系统完整保护”功能
$ csrutil enable
```

结束并重新开机 ➤ 进入正常模式MacOS ➤ NTFS 读写功能已开启

## 完成！

