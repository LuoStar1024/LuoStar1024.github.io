---
title: LFramework解析：开篇
date: 2024-10-09 22:42:51
tags:
    - Unity
    - LFramework
categories:
    - 客户端
    - LFramework
---

## 绪论

目前其实已经有很多客户端框架了，但每个人对不同的框架有不同的看法，所以打算整合不同框架中认为更好模块。也是为了整理目前所学的所有知识吧。

本LFramework框架使用GameFramework框架的架构，即框架分成纯C#部分LFramework实现核心逻辑，并对外提供接口。LFrameworkUnity负责实现接口并提供Unity编辑器扩展。战斗部分目前不了解，先按我的理解划分一下LFramework，层层递进。

### 非热更新

#### LFramework

框架的最底层，纯C#实现。分为Core和Manager两部分。

##### LFramework.Core

这部分是与引擎无关的模块核心。包括：事件、引用池、定时器、有限状态机、数据节点、数据表、日志。

##### LFramework.Manager

这部分将Core里的模块进行实例化并是其他所有模块的纯C#部分，并抛出需要实现的接口。其他模块包括：调试器、本地化、对象池、资源、场景、配置、声音、界面、流程

#### LFrameworkUnity

负责将Core中的模块进行实例化、抛出实例化接口，实现Manager中的接口。提供Unity编辑器扩展。

#### GameMain

负责对LFrameworkUnity进行初始化和游戏开始流程。

### 热更新

战斗部分仅仅是进行划分，具体实现不在本系列当中。

#### LFrameworkBattle

独立的战斗框架，负责将Core中的模块进行实例化，提供一个战斗框架。与LFrameworkUnity算是同级。只是战斗部分会放到服务器上运行，所以不能与Unity关联。

#### GameView

游戏中通过Unity显示的部分，只会通过GameMain进行框架的接口调用，不与其他非热更新模块关联。

#### BattleLogic

游戏中的战斗模块，提供战斗的初始化和推进，可直接运行在服务器上。表现上，通过GameView进行表现？

#### Config、Proto

目前暂不知道如何划分。

## 目录

- LFramework解析：事件（Event）

- LFramework解析：引用池（Reference Pool）

- LFramework解析：定时器（Timer）

- LFramework解析：有限状态机（Fsm）

- LFramework解析：数据节点（Data Node）

- LFramework解析：数据表（Data Table）

- LFramework解析：日志（Log）

- LFramework解析：调试器（Debugger）

- LFramework解析：本地化（Localization）

- LFramework解析：对象池（Object Pool）

- LFramework解析：资源（Resources）

- LFramework解析：场景（Scene）

- LFramework解析：配置（Setting）

- LFramework解析：声音（Sound）

- LFramework解析：界面（UI）

- LFramework解析：流程（Procedure）
