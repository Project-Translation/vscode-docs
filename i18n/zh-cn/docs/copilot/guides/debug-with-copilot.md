---
ContentId: 2f21c45a-8931-4da2-a921-af23a3b92949
DateApproved: 2025/03/05
MetaDescription: 了解如何在 Visual Studio Code 中使用 GitHub Copilot 设置调试配置并在调试过程中解决问题。
---

# 使用 GitHub Copilot 进行调试

GitHub Copilot 可以帮助您在 Visual Studio Code 中改进调试工作流程。Copilot 可以协助设置项目的调试配置，并在调试过程中提供修复问题的建议。本文概述了如何在 VS Code 中使用 Copilot 调试应用程序。

Copilot 可以帮助完成以下调试任务：

* **配置调试设置**：为您的项目生成和自定义启动配置。
* **启动调试会话**：使用 `copilot-debug` 从终端启动调试会话。
* **修复问题**：在调试过程中接收修复问题的建议。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup) 免费使用 Copilot，并获得每月的完成和聊天交互限制。

## 使用 Copilot 设置调试配置

VS Code 使用 `launch.json` 文件来存储[调试配置](/i18n/zh-cn/docs/debugtest/debugging-configuration.md)。Copilot 可以帮助您创建和自定义此文件，以为您的项目设置调试。

1. 打开聊天视图 (`kb(workbench.action.chat.open)`)。
1. 输入 `/startDebugging` 命令。
1. 按照 Copilot 的指导为您的项目设置调试。

或者，您可以使用自然语言提示，例如：

* "为 Django 应用创建调试配置"
* "为 React Native 应用设置调试"
* "为 Flask 应用程序配置调试"

## 使用 Copilot 启动调试

`copilot-debug` 终端命令简化了配置和启动调试会话的过程。在您的应用程序启动命令前加上 `copilot-debug`，Copilot 将自动配置并启动调试会话。

1. 打开集成终端 (`kb(workbench.action.terminal.toggleTerminal)`)。

1. 输入 `copilot-debug` 后跟您的应用程序启动命令。例如：

    ```bash
    copilot-debug node app.js
    ```

    或

    ```bash
    copilot-debug python manage.py
    ```

1. Copilot 为您的应用程序启动调试会话。现在您可以使用 VS Code 中的内置调试功能。

了解更多关于[在 VS Code 中调试](/i18n/zh-cn/docs/debugtest/debugging.md)的信息。

## 使用 Copilot 修复代码问题

您可以使用 Copilot Chat 帮助您修复代码问题或改进代码。

### 使用聊天提示

1. 打开您的应用程序代码文件。

1. 打开以下视图之一：
    * Copilot 编辑 (`kb(workbench.action.chat.openEditSession)`)
    * 聊天视图 (`kb(workbench.action.chat.open)`)
    * 内联聊天 (`kb(inlineChat.start)`)

1. 输入以下提示之一：
    * "/fix"
    * "修复此 #selection"
    * "验证此函数的输入"
    * "重构此代码"
    * "提高此代码的性能"

了解更多关于在 VS Code 中使用 [Copilot Chat](/i18n/zh-cn/docs/copilot/copilot-chat.md) 和 [Copilot 编辑](/i18n/zh-cn/docs/copilot/copilot-edits.md) 的信息。

### 使用编辑器智能操作
要在不编写提示的情况下修复应用程序代码中的编码问题，您可以使用编辑器的智能操作。

1. 打开您的应用程序代码文件。
1. 选择您要修复的代码。
1. 右键点击并选择 **Copilot** > **修复**。

    Copilot 会提供一个修复代码的建议。

1. 可选地，通过在聊天提示中提供额外的上下文来优化生成的代码。

## 后续步骤

* 探索 [VS Code 中的常规调试功能](/i18n/zh-cn/docs/debugtest/debugging.md)。
* 了解更多关于 [VS Code 中的 Copilot](/i18n/zh-cn/docs/copilot/overview.md)。