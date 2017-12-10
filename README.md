# 開啟 MacOS 自動讀寫 NTFS

FUSE for OS X + NTFS-3G 的一次性解決方案

https://github.com/isaac-joe/NTFS


[繁體中文](https://github.com/isaac-joe/NTFS/blob/master/README-zhcn.md) | [简体中文](https://github.com/isaac-joe/NTFS/blob/master/README-zhcn.md)



###開始之前 你需要的熟練的技術有

1. Recovery Mode 回復模式  
https://support.apple.com/zh-tw/HT201314
2. 執行終端機指令
3. 安裝 Homebrew  
https://brew.sh/index_zh-tw.html

若上述步驟無法完成，或者並非 100% 確定； 
請直接放棄，並招喚工具國 🤹‍♂️ 
讓工具人一起為您的 Mac 健康把關！

#就是好工具 #就是好工具 #就是好工具

> # 開始

#### 1. 安裝 FUSE for OS X + NTFS-3G

終端機執行 2 個指令：

brew cask install osxfuse brew install ntfs-3g

#### 2. 解除 「系統完整保護」，開啓NTFS 讀寫能力 

Rovery Mode 終端機指令：

`csrutil disable`

正常開機，終端機指令：
`
sudo mv /sbin/mount_ntfs /sbin/mount_ntfs.original
sudo ln -s /usr/local/sbin/mount_ntfs /sbin/mount_ntfs
`
再到 Rovery Mode 終端機指令：

`csrutil enable`

關閉視窗後重新開機，便開啓 NTFS 讀寫功能。

