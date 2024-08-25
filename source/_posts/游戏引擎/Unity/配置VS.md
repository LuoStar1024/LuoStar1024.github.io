---
title: Unity配置VS Code
date: 2024-08-25 10:57:29
tags:
    - Unity
categories:
    - 游戏引擎
    - Unity
---

## 配置C#运行环境

#### 下载.NET SDK并安装 https://dotnet.microsoft.com/zh-cn/download

{% asset_img 1_1.png %}

#### 验证

通过win + R，输入cmd打开命令提示符，输入

```
dotnet --info
```

可以查看当前电脑上的.NET SDK 信息。如果没有信息，说明没有安装。

{% asset_img 1_2.png %}

## 在VS Code中配置C#和Unity开发环境

#### 安装插件

在VS Code提供了对Unity的支持后，只需要安装两个插件，一个是Unity，一个Unity Code Snippets。

其中.NET Install Tool、C#、C# Dev Kit依赖于Unity插件，会被自动安装。

{% asset_img 2_1.png %}

#### 配置插件

有时候插件会识别不到本地已经安装的.NET SDK，所以可以直接通过配置文件指定.NET SDK的位置。

按ctrl + shift + p，然后在输入框中输入settings.json，打开用户设置

{% asset_img 2_2.png %}

然后在json文件中加入配置项，path是安装目录。

```
"dotnetAcquisitionExtension.existingDotnetPath": [
    {
        "extensionId": "ms-dotnettools.csharp",
        "path": "C:\\Program Files\\dotnet\\dotnet.exe"
    },
    {
        "extensionId": "ms-dotnettools.csdevkit",
        "path": "C:\\Program Files\\dotnet\\dotnet.exe"
    },
    {
        "extensionId": "visualstudiotoolsforunity.vstuc",
        "path": "C:\\Program Files\\dotnet\\dotnet.exe"
    },
    {
        "extensionId": "msazurermtools.azurerm-vscode-tools",
        "path": "C:\\Program Files\\dotnet\\dotnet.exe"
    }
],
```

## 在Unity中将VS Code设置为默认编辑器

#### 更新插件

点击Window / Package Manage打开界面，找到Visual Studio Editor并将其更新到最新版本。

{% asset_img 3_1.png %}

#### 修改默认编辑器

点击Edit / Preferences 打开界面，再选择External Tools选项，修改脚本编辑器为VS Code。

{% asset_img 3_2.png %}

## 使用断点调试

#### 在VS Code中启动

{% asset_img 4_1.png %}

#### 在Unity中同意启用

{% asset_img 4_2.png %}

#### 打断点。鼠标放到代码的最左边单击出现红点表示成功。

{% asset_img 4_3.png %}

#### 最后运行Unity就行，程序会停在断点处。

{% asset_img 4_4.png %}

左上可以查看当前所有的局部变量信息。

中上可以控制程序走向。

鼠标直接放到变量上可以直接显示该变量的信息。
