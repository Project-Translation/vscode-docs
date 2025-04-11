---
Order: 4
Area: copilot
TOCTitle: 快速入门
ContentId: 37fd3bd2-4209-49f6-bec5-c544d6b1b289
PageTitle: GitHub Copilot 快速入门
DateApproved: 2025/03/05
MetaDescription: 在 Visual Studio Code 中开始使用 GitHub Copilot，并在编辑器中创建您的第一个 AI 驱动的建议。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中开始使用 GitHub Copilot

本教程将引导您了解 GitHub Copilot 在 Visual Studio Code 中的关键功能。了解如何开始使用 [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) 扩展程序，在编辑器中获取 AI 驱动的代码建议，使用聊天对话重构您的代码，并通过智能操作修复代码错误。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup) 免费使用 Copilot，并获得每月的完成和聊天交互限制。

虽然本教程使用 TypeScript，但请注意，Copilot 还接受了许多其他语言和各种框架的训练。

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/2q0BoioYSxQ" title="GitHub Copilot 最佳实践（不该做什么）" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 先决条件

要在 VS Code 中使用 GitHub Copilot，您需要具备以下条件：

* 访问 GitHub Copilot
* 在 VS Code 中安装 GitHub Copilot 扩展程序

按照 [GitHub Copilot 设置指南](/i18n/zh-cn/docs/copilot/setup.md) 中的步骤获取 GitHub Copilot 的访问权限，并在 VS Code 中安装 Copilot 扩展程序。

## 获取您的第一个代码建议

要在 VS Code 中开始使用 GitHub Copilot，您无需做任何特殊操作。当您在编辑器中输入代码时，Copilot 会自动在编辑器中为您提供代码建议，以帮助您更高效地编写代码。

1. 打开 Visual Studio Code 并创建一个新的 JavaScript 文件 `calculator.js`。

1. 在 JavaScript 文件中，开始输入以下代码：

    ```javascript
    class Calculator
    ```

    Copilot 会自动为我们的 `Calculator` 类建议一个方法，以灰色模糊文本（幽灵文本）显示。在我们的示例中，建议了 `add` 和 `subtract` 方法。您收到的确切建议可能会有所不同。

    ![VS Code 编辑器的屏幕截图，显示 Copilot 在 `Calculator` 类中建议 `add` 方法。](./images/getting-started/copilot-code-completion.png)

1. 要接受建议，请按 `kbstyle(Tab)` 键。

    恭喜！您刚刚接受了您的第一个 AI 驱动的内联建议。随着您继续输入，Copilot 会相应地更新内联建议。

1. 对于任何给定的输入，可能会有多个建议。在类中输入以下代码以添加 `factorial` 方法：

    ```javascript
    factorial(n) {
    ```

1. 将鼠标悬停在编辑器中的建议上，您会注意到有多个建议。

    ![VS Code 编辑器的屏幕截图，显示 Copilot 在悬停时为 `factorial` 提供多个建议。](./images/getting-started/copilot-code-completion-multiple.png)
您可以使用箭头控件或使用键盘快捷键来显示下一个（`kb(editor.action.inlineSuggest.showNext)`）或上一个（`kb(editor.action.inlineSuggest.showPrevious)`）建议。

AI 驱动的代码补全可以帮助您生成样板或重复的代码，让您保持开发流程，并专注于更复杂的编码任务。

## 使用内联聊天生成基本的 Web 服务器

使用 Copilot Chat，您可以在 VS Code 中与 Copilot 开始聊天对话，使用自然语言询问关于您的代码的具体任务。

让我们使用 **内联聊天** 来帮助生成一个基本的 Express Web 服务器。

1. 首先，在您的工作区中添加一个新的 TypeScript 文件 `server.ts`。

1. 现在，按下 `kb(inlinechat.start)` 键盘快捷键，调出 Copilot 内联聊天。

    Copilot 内联聊天为您提供了一个聊天界面，让您可以询问关于活动编辑器中代码的问题。

    ![VS Code 编辑器的屏幕截图，显示 Copilot 内联聊天控件。](./images/getting-started/copilot-inline-chat.png)

1. 在聊天输入框中输入“添加一个简单的 Express Web 服务器”，然后按 `kbstyle(Enter)` 发送提示给 Copilot。

    请注意，Copilot 在编辑器中返回一个流式响应。响应是一个简单的 Node.js Express Web 服务器的实现。

    ![VS Code 编辑器的屏幕截图，显示 Copilot 内联聊天对添加 Express Web 服务器的响应。](./images/getting-started/copilot-inline-chat-express-server.png)

1. 选择 **接受** 或按 `kb(inlineChat.acceptChanges)` 应用提议的代码更改。

    恭喜您！您已经使用 Copilot Chat 通过聊天和自然语言生成了代码。

## 通过 AI 聊天重构您的代码

您还可以使用内联聊天来重构或改进编辑器中的现有代码。

请注意，我们的 Web 服务器目前使用的是静态端口号 `3000`。让我们将其更改为使用环境变量来设置端口号。

1. 在编辑器中，选择 `server.ts` 文件中的 `3000` 端口号，然后按 `kb(inlinechat.start)` 启动内联聊天。

1. 在聊天输入框中输入“使用环境变量设置端口号”，然后按 `kbstyle(Enter)` 发送聊天请求或提示。

    请注意 Copilot 是如何更新现有代码以使用环境变量设置端口号的。

    ![VS Code 编辑器的屏幕截图，显示使用环境变量设置端口号的内联聊天。](./images/getting-started/copilot-inline-chat-refactor-port.png)

1. 选择 **接受** 或按 `kb(inlineChat.acceptChanges)` 应用提议的代码更改。

1. 如果您对提议的更改不满意，您可以修改提示，并要求 Copilot 提供不同的解决方案。

    例如，您可以要求 Copilot 使用不同的环境变量名称来设置端口号。

## 使用 Copilot Chat 解决一般编程问题

当您在一个新的代码库中工作，或探索一种新的编程语言时，可能会遇到更多的一般性编码问题。Copilot Chat 允许您在侧边打开一个聊天对话，并跟踪您的问题历史。

1. 从命令中心的 Copilot 菜单中打开聊天视图，或按 `kb(workbench.action.chat.open)`。
![VS Code编辑器的屏幕截图，显示Copilot聊天视图，突出显示命令中心中的Copilot菜单。](./images/getting-started/copilot-chat-menu-command-center.png)

> [!TIP]
> 您可以随时从命令中心菜单访问不同的Copilot功能。

1. 在聊天输入字段中输入“什么是递归？”并按`kb(workbench.action.chat.submit)`发送请求给Copilot。

    ![VS Code编辑器的屏幕截图，显示包含递归是什么答案的Copilot聊天视图。结果包含文本和代码块。](./images/getting-started/copilot-chat-view-recursion.png)

    请注意聊天响应包含丰富的结果，由文本和代码块组成。聊天响应中的代码块支持IntelliSense，允许您通过悬停在方法和符号上获取信息，或跳转到它们的定义。

1. 按照[Copilot聊天教程](/i18n/zh-cn/docs/copilot/getting-started-chat.md)中的步骤学习如何使用Copilot聊天询问您特定代码库的问题。

## 使用Copilot Edits跨多个文件进行编辑

较大的代码更改可能涉及对多个文件进行编辑。使用Copilot Edits，您可以在编辑器中内联获取AI驱动的建议，跨工作区的多个文件。Copilot Edits不仅仅是应用单个代码块，它会在您的工作区中进行编辑。

让我们使用Copilot Edits在Web服务器响应中返回HTML文件的内容。

1. 从命令中心的Copilot菜单中选择**打开Copilot Edits**，或按`kb(workbench.action.chat.openEditSession)`。

    ![屏幕截图显示命令中心中的Copilot菜单，突出显示打开编辑会话项目](images/copilot-edits/copilot-command-center-open-edit-session.png)

1. 打开了Copilot Edits视图。请注意，`server.ts`文件已添加到提示中。

    Copilot会自动将活动编辑器添加到提示中。如果文件未添加，请使用**添加文件...**手动将文件添加到提示中。

    ![Copilot Edits视图的屏幕截图，显示带有`server.ts`文件的提示输入字段。](./images/getting-started/copilot-edits-working-set.png)

1. 在聊天输入字段中输入*返回一个静态HTML页面作为主页并实现它。*并按`kbstyle(Enter)`开始一个新的编辑会话。

    请注意，Copilot Edits进行了多次编辑：它更新了`server.ts`文件以返回一个静态HTML页面，并且还添加了一个新的文件`index.html`。

    ![VS Code编辑器的屏幕截图，显示在Web服务器响应中返回静态HTML页面的Copilot Edits响应。](./images/getting-started/copilot-edits-html-response.png)

1. 如果您对结果满意，请选择**保留**以应用所有建议的更改。

    您还可以使用编辑器覆盖控件在不同编辑的文件之间导航，并接受/拒绝它们。

    ![Copilot Edits视图的屏幕截图，突出显示应用更改的保留按钮。](./images/getting-started/copilot-edits-accept.png)

## 使用Copilot修复编码错误
除了内联完成和聊天对话外，GitHub Copilot 在 VS Code 中不同的地方和整个开发流程中都可用。你可能会通过 VS Code 用户界面中的*闪光*图标注意到 Copilot 功能的存在。

其中一个地方是在编辑器中出现编译错误的红色波浪线时，Copilot 的编码操作。让我们看看 Copilot 如何帮助解决编码错误。

1. 在编辑器中打开你之前创建的 `server.ts` TypeScript 文件。

    请注意，`import express from 'express';` 语句包含一个红色波浪线。如果你将光标放在红色波浪线上，你会看到 Copilot 的闪光图标出现。

    ![VS Code 编辑器的屏幕截图，显示由于 express 导入语句错误而出现的 Copilot 闪光图标。](./images/getting-started/copilot-code-action-sparkle.png)

1. 选择闪光图标查看 Copilot 代码操作，然后选择**使用 Copilot 修复**。

    ![VS Code 编辑器的屏幕截图，显示 Copilot 代码操作，高亮显示`使用 Copilot 修复`。](./images/getting-started/copilot-code-action-fix.png)

1. 请注意，Copilot 内联聊天会出现，预填充了错误消息和解决问题的方案。

    ![VS Code 编辑器的屏幕截图，显示 Copilot 内联聊天建议安装 express npm 包来解决问题。](./images/getting-started/copilot-code-action-fix-result.png)

    直接从聊天响应中，你可以选择**插入到终端**按钮，将建议的命令复制到你的终端中。

## 下一步

恭喜你，现在你已经使用人工智能来增强你的编码！在本教程中，你成功地在 VS Code 中设置了 Copilot，并使用了 Copilot 代码完成、Copilot 聊天和代码操作来帮助你更高效地编码。

* 要了解更多关于 Copilot 聊天的信息，请继续阅读 [Copilot 聊天教程](/i18n/zh-cn/docs/copilot/getting-started-chat.md)。

* 要了解更多关于 Copilot 编辑的信息，请继续阅读 [Copilot 编辑](/i18n/zh-cn/docs/copilot/copilot-edits.md)文档。

## 相关资源

查看我们在 YouTube 上的[高级功能](https://www.youtube.com/watch?v=SLMfhuptCo8)视频，深入了解使用 Copilot 进行重构、基于上下文的建议、单元测试等。