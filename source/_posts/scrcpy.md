---
title: Scrcpy Android投屏神器
date: 2022-03-02 15:57:07
categories: 好软件
tags: ['软件', '投屏', '手机投屏']
---

`Scrcpy` 是免费开源的投屏软件，支持将安卓手机屏幕投放在 `Windows`、`macOS`、`GNU/Linux` 上，并可直接借助鼠标在投屏窗口中进行交互和录制。市面上主流的多屏协同软件都是基于 `Scrcpy` 套层皮，推荐直接使用 `Scrcpy`。

## 安装
Mac 用户需要使用 HomeBrew 命令进行安装。其实 HomeBrew 的功能很实用，它可以帮助你非常简单地一键安装/卸载各种软件，包括 Scrcpy。

<!-- more -->

1、安装 homebrew： 通过命令行 (Terminal) 执行 ，如已安装可跳过
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
2、安装 Scrcpy
```bash
brew install scrcpy
```

3、安装 ADB：如果你没有安装 ADB 命令行工具，那么也可以用 brew 来安装
```bash
brew cask install android-platform-tools
```

## Scrcpy的命令参数

描述 | 命令(说明)
---|---
关闭手机屏幕 | `scrcpy -S`
限制画面分辨率 | `scrcpy -m 1024` (比如限制为 1024)
修改视频码率 | `scrcpy -b 4M` (默认 8Mbps，改成 4Mbps)
裁剪画面 | `scrcpy -c 1224:1440:0:0` 表示分辨率 1224x1440 并且偏移坐标为 (0,0)
多设备切换 | `scrcpy -s 设备ID` (使用 `adb devices` 命令查看设备ID)
窗口置顶 | `scrcpy -T`
显示触摸点击 | `scrcpy -t` 在演示或录制教程时，可在画面上对应显示出点击动作
全屏显示 | `scrcpy -f`
文件传输默认路径 | `scrcpy --push-target /你的/目录` 将文件拖放到 scrcpy 可以传输文件，此命令指定默认保存目录
只读模式(仅显示不控制) | `scrcpy -n`
屏幕录像 | `scrcpy -r 视频文件名.mp4` 或 `.mkv`
屏幕录像 (禁用电脑显示) | `scrcpy -Nr 文件名.mkv`
设置窗口标题 | `scrcpy --window-title '异次元好棒！'`


## Scrcpy 快捷键
描述 | 快捷键
---|---
切换全屏模式 | `Ctrl` + `F`
将窗口调整为1：1（完美像素） | `Ctrl` + `G`
调整窗口大小以删除黑色边框 | `Ctrl` + `X` 或 双击黑色背景
设备 `HOME` 键 | `Ctrl` + `H` 或 鼠标中键
设备 `BACK` 键 | `Ctrl` + `B` 或 鼠标右键
设备 `任务管理` 键 (切换APP) | `Ctrl` + `S`
设备 `菜单` 键 | `Ctrl` + `M`
设备 `音量+` 键 | `Ctrl` + `↑`
设备 `音量-` 键 | `Ctrl` + `↓`
设备电源键 | `Ctrl` + `P`
点亮手机屏幕 | `鼠标右键`
复制内容到设备 | `Ctrl` + `V`
启用/禁用 FPS 计数器（stdout） | `Ctrl` + `i`
安装APK | 将 apk 文件拖入投屏
传输文件到设备 | 将文件拖入投屏（非apk）
 
## 参考链接
https://www.iplaysoft.com/scrcpy.html
