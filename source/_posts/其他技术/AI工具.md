---
title: AI 工具
author: 落星
tags:
  - AI
categories:
  - 其他技术
date: 2026-04-18 17:42:52
---

最近 AI 发展迅猛，使用 AI 来写代码，是提高效率的不二之选。写本篇文章只是记录一下使用到的工具，方便后续自己查找资料。

## 终端 CLI

目前使用较多的终端 CLI 大概有以下几个：

- Claude Code
  
  ```
  # Windows PowerShell
  irm https://claude.ai/install.ps1 | iex
  # 版本
  claude --version
  ```
  
  如果不能直接启动，或许需要添加环境变量：
  
  {% asset_img Claude环境变量.png %}

- Codex
  
  ```
  # Windows
  npm install -g @openai/codex
  # 版本
  codex --version
  ```

- Gemini
  
  ```
  # Windows
  npm install -g @google/gemini-cli
  ```

- Droid
  
  ```
  # Windows PowerShell
  irm https://app.factory.ai/cli/windows | iex
  ```

- OpenCode
  
  ```
  # Windows
  curl -fsSL https://opencode.ai/install | bash
  npm i -g opencode-ai
  ```

## 扩展工具

### 嵌入编辑器中

- VS Code：安装对应 CLI 的插件。

- Rider：安装 CC GUI 插件。这个插件目前支持 Claude Code 和 Codex。非常推荐。

### 代理工具

- CC Switch：管理多个终端 CLI 工具。

### 其他

- OpenSpec：规范驱动的变更管理工具。

- 提示词优化：https://github.com/linshenkx/prompt-optimizer

## 中转站

敬请期待。
