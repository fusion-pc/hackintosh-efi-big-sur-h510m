[English](./README_EN.md) | 简体中文

# Intel 安装 Hackintosh 的 OpenCore EFI 文件

OpenCore 版本: v0.6.8

macOS 版本：Big Sur(11.2.3)

![Screenshot](Screenshot.png)

## 主要规格参数

| 类型     | 型号                                                         |
| :------- | :----------------------------------------------------------- |
| 处理器   | Intel 酷睿 i3-10100F 四核八线程 @ 3.6GHz<br/>（支持 **十代酷睿** ，不支持使用 **奔腾**  ，**赛扬** ） |
| 主板     | 微星 H510M A-PRO<br/>（支持 **微星 H410M PRO-E**，需要更改网卡开关） |
| 显卡     | 华硕 Nvdia GTX 760 2G GDDR5<br/>（建议使用 **Nvdia GTX 6XX,7XX** 和 **Radeon RX 5XX** 等免驱卡） |
| 固态硬盘 | 256G 浦科特 M6S<br/>（支持 **NVMe** 硬盘，插上即用）         |
| 有线网卡 | 板载 Intel I219V V10 1G<br/>（**微星 H410M PRO-E** 板载 **Realtek RTL8111L 1G**) |

## 安装步骤

1. 制作 [macOS 启动盘](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html#downloading-macos-modern-os)

2. 为你的`config.plist`使用 [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) 生成 SMBIOS 信息

3. 根据 [Dortania's OpenCore Big Sur 安装指引](https://dortania.github.io/OpenCore-Install-Guide/extras/big-sur/#table-of-contents) 进行安装

   （config.plist 建议使用 [ProperTree ](https://github.com/corpnewt/ProperTree)，[VS Code](https://code.visualstudio.com/) 等工具编辑）

## 可用

- 板载有线网口（**绿联蓝牙适配器4.0** 可用）
- iMessage，iCloud，FaceTime，App Store，Apple Music
- 所有 USB 接口（**SSK 四口 USB3.0 高速传输分线器** 可用）
- 睡眠、唤醒

\* 有时候从长时间睡眠中唤醒后无法使用

## 不可用

- 隔空投送，Sidecar
- 使用您的 Apple Watch 解锁 App 和 Mac

\* 隔空投送，Sidecar，Apple Watch 解锁 Mac 需要加装 **博通** 芯片网卡，即可正常使用

## 常见问题

### 进入 MacOS 系统没有网络

用 [ProperTree](https://github.com/corpnewt/ProperTree) 或者 [VS Code](https://code.visualstudio.com/) 打开 /EFI/OC/ 下的 config.plist，根据你的主板相应的网卡在 Kext -> Add 下把 False 更改为 True，保存即可。

### 替换 Resources 文件，无法启用图形化界面

建议替换支持 **OpenCore 0.6.8** 的 [Resources](https://github.com/acidanthera/OcBinaryData)，具体可以参考 [设置OpenCore 的GUI](https://dortania.github.io/OpenCore-Post-Install/cosmetic/gui.html#setting-up-opencore-s-gui) 。



