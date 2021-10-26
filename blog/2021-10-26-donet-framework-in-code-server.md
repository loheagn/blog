---
title: 在code-server中查看C# .NET Framework 项目
authors: loheagn
---

本文没有干货

<!-- truncate -->

## 背景

最近接手了实验室一批“陈旧”的C#项目，用的还是.NET Framework，只能在Windows上开发。但我并没有Windows机器，有需要的话只能在本地Windows虚拟机中搞。加上我本身是个C#小白，整体体验可以说很糟糕了。

前段时间在某位同学的推动下，重新用起了[code-server](https://github.com/cdr/code-server)（之所以说是重新，是因为我之前在大二尝试过这个工具——当时也同样是为了摆脱Windows，在Windows上使用Linux的工具链——体验可以说比较糟糕，当时甚至安装插件都只能手动下载vsix文件后手动安装），发现竟然变得意外的好用，延迟比vscode的ssh-remote不知道低到哪里去了。于是，萌生了在实验室的Windows虚拟机上安装code-server后，然后本地通过Chrome远程开发的想法——这样起码快捷键不会太别扭。

## 着手做

### 安装code-server

没啥好说的，按照官方Guide中的[yarn-npm](https://coder.com/docs/code-server/latest/install#yarn-npm)部分的指导来就行。安装前一定要注意查看是否满足官方给出的前置条件。

另外，在Windows中安装时，最好用Bash，比如git-bash。在安装过程中可能会有一段时间stdout上没有输出，耐心等待就好。

安装完成后，可能还需要将yarn的bin目录放到`Path`环境变量中。

### 配置打开C# .NET Framework 项目

1. 在code-server中安装C#插件，重启coder-server服务。

2. 在Windows机器中，用Visual Studio打开项目中的`.csproj`文件（而不是直接打开整个文件夹）。这样，Visual Studio会将其识别为一个解决方案。待加载完成后，用NuGget重新安装一遍项目的依赖，待没有文件标红即为成功。然后，关闭Visual Studio。

3. 在code-server中打开项目文件夹。此时，将可以正常编写代码、跳转定义等等。

## 总结

Windows真难用，我不适合它。