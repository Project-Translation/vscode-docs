---
ContentId: 5d8a707d-a239-4cc7-92ee-ccc763e8eb9c
DateApproved: 2025/03/05
MetaDescription: 在 VS Code 中通过 AI 驱动的聊天对话与 GitHub Copilot 互动，以生成代码、增强代码理解，甚至配置您的编辑器。
MetaSocialImage: images/shared/github-copilot-social.png
---
# Copilot 聊天上下文

本文介绍如何在 Visual Studio Code 中为您的 Copilot 聊天提示添加上下文，以帮助 Copilot 提供最佳和最相关的回答。Copilot 支持不同[类型的上下文](#chat-context-types)，包括文件、符号、终端命令输出等。

Copilot 会根据您的自然语言聊天提示来确定您的问题的意图和范围。为了帮助 Copilot 提供最佳和最相关的回答，[为您的聊天提示添加上下文](#add-context-to-your-chat-prompt)或[让 Copilot 自动查找正确的文件](#let-copilot-find-the-right-files-automatically)。

## 为您的聊天提示添加上下文

有几种方法可以为您的聊天提示添加上下文：

* VS Code 会自动将当前活动的编辑器作为上下文添加。如果您在编辑器中选择了一个代码块，则仅该选择会被添加为上下文。

    您可以通过选择上下文项目旁边的禁用（眼睛）图标来禁用当前请求的活动编辑器添加。使用 `setting(chat.implicitContext.enabled)` 设置来配置是否应为所有请求自动添加活动编辑器。

    ![VS Code Copilot 聊天视图的屏幕截图，显示当前编辑器选择作为上下文。](./images/copilot-chat/copilot-chat-view-selection-context.png)

* 选择 **附加上下文**（回形针）图标（Copilot 聊天）或 **添加文件**按钮（Copilot 编辑），然后从快速选择中选择一种上下文类型。

    ![VS Code Copilot 聊天视图的屏幕截图，显示附加上下文按钮和上下文快速选择。](./images/copilot-chat/copilot-chat-view-attach-context.png)

    您可以附加预定义的上下文类型，例如 **代码库** 或 **终端选择**，或者从工作区中选择文件、文件夹或符号。

    > [!TIP]
    > 要从附件快速选择中快速添加多个项目，请使用 `kbstyle(Up)` 和 `kbstyle(Down)` 键导航列表，使用 `kbstyle(Right)` 键将项目添加为上下文，然后对其他项目重复此操作。

* 在资源管理器或搜索视图中对文件使用上下文菜单 **Copilot** > **将文件添加到聊天**，或对编辑器中的文本选择使用 **将选择添加到聊天**。

* 在您的聊天提示中输入 `#` 字符，以使用聊天变量引用上下文。

    例如，使用 `#selection` 将当前编辑器选择添加到您的聊天提示中，使用 `#file` 添加工作区文件，或使用 `#sym` 添加工作区中的符号。

    ![VS Code Copilot 聊天视图的屏幕截图，显示聊天变量选择器。](./images/copilot-chat/copilot-chat-view-chat-variables.png)

    > [!TIP]
    > 输入 `#` 并将其用作 IntelliSense 触发器，以选择文件或符号。

* 将编辑器标签页、或来自资源管理器视图、搜索视图或编辑器面包屑的文件或文件夹拖放到聊天视图中。

    <video src="images/copilot-chat/copilot-attach-dnd.mp4" title="将文件和编辑器拖放到聊天中" autoplay loop controls muted></video>
> [!NOTE]
> 如果可能，附件文件时将包含文件的全部内容。如果文件内容太大无法放入上下文窗口中，将包含一个包括函数及其描述（不含实现）的文件大纲。如果大纲也太大，则文件不会包含在提示中。

## 让 Copilot 自动查找合适的文件

您可以让 Copilot 从您的代码库中自动查找合适的文件，而不必手动添加单个文件。当您不知道哪些文件与您的问题相关时，这会很有用。

要让 Copilot 自动查找合适的文件，请在提示中添加 `#codebase`，或从上下文类型列表中选择 **代码库**。

请确保启用 `setting(github.copilot.chat.codesearch.enabled)` _(预览版)_ 设置，以获得最佳结果。

## 为解决问题添加上下文

当您在代码中遇到问题，或在运行测试时失败时，您可以向聊天提示中添加特定上下文，以帮助 Copilot 提供最佳答案。

* 从 **问题** 面板中拖放项目，以将相应的问题作为上下文附加到您的提示中。

    或者，从上下文类型列表中选择 **问题...**，然后从快速选择中选择一个具体的问题。

    ![将问题从问题面板拖放到聊天输入字段的聊天视图截图，显示了附加问题的效果。](./images/copilot-chat/copilot-chat-attach-problem.png)

* 选择 **测试失败** 上下文类型，将测试失败的详细信息作为上下文添加到您的提示中。

* 从上下文类型列表中选择 **终端最后命令** 或输入 `#terminalLastCommand`，以附加在终端中运行的最后命令的输出。

## 聊天上下文类型

Copilot 支持以下上下文类型：

* 文件 - 在提示中包含工作区中的特定文件
* 文件夹 - 添加一个文件夹以在提示中包含该文件夹中的文件
* 符号 - 从工作区中添加一个符号到提示中
* 代码库 - 让 Copilot 自动查找合适的文件
* 编辑器或终端选择 - 在提示中包含来自编辑器或终端的文本选择
* 终端命令输出 - 在提示中包含在终端中运行的最后命令的输出
* 问题 - 在提示中包含来自问题面板的特定代码问题
* 测试失败 - 在提示中包含测试失败的详细信息

## 相关资源

* 使用 [Copilot 聊天](/i18n/zh-cn/docs/copilot/copilot-chat.md) 与 Copilot 互动。
* 使用 [Copilot 编辑](/i18n/zh-cn/docs/copilot/copilot-edits.md) 在多个文件中进行编辑。