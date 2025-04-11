---
Order: 7
Area: copilot
TOCTitle: Copilot 聊天教程
ContentId: ae1f36a9-7597-425f-97fc-49bd51c153a3
PageTitle: 开始使用 Copilot 聊天
DateApproved: 2025/03/05
MetaDescription: 在 Visual Studio Code 中开始使用由 AI 驱动的聊天对话，与 GitHub Copilot 进行内联聊天，或在单独的聊天视图中进行。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中开始使用 Copilot 聊天

本教程将引导您使用 [GitHub Copilot 聊天](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat) 扩展在 Visual Studio Code 中进行操作。您可以使用 AI 驱动的聊天对话来帮助重构代码，提高代码理解，并找到配置 VS Code 的方法。

如果您是首次在 VS Code 中使用 GitHub Copilot，请参阅 [GitHub Copilot 概述](/i18n/zh-cn/docs/copilot/overview.md)，或者通过 [GitHub Copilot 入门教程](/i18n/zh-cn/docs/copilot/getting-started.md) 设置并发现其关键功能。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup) 来免费使用 Copilot，并获得每月的完成和聊天互动限制。

## 先决条件

要在 VS Code 中使用 GitHub Copilot，您需要具备以下条件：

* 访问 GitHub Copilot
* 在 VS Code 中安装 GitHub Copilot 扩展

请按照 [GitHub Copilot 设置指南](/i18n/zh-cn/docs/copilot/setup.md) 中的步骤获取 GitHub Copilot 的访问权限，并在 VS Code 中安装 Copilot 扩展。

## 开始您的第一次 Copilot 聊天对话

Copilot 聊天是一个聊天界面，让您可以与 GitHub Copilot 互动，提出和接收与编码相关的问题。聊天界面提供了访问编码信息和支持的途径，无需您浏览文档或在线搜索论坛。

在本教程中，您将创建一个简单的 Node.js Web 应用程序。

1. 从命令中心的聊天菜单打开聊天视图，或按 `kb(workbench.action.chat.open)`。

    ![VS Code 编辑器的屏幕截图，显示 Copilot 聊天视图，突出显示命令中心中的聊天菜单。](./images/getting-started-chat/copilot-chat-menu-command-center.png)

    > [!TIP]
    > 您可以随时从命令中心菜单访问不同的 Copilot 功能。

1. 在聊天输入字段中输入 "@workspace /new express with typescript and pug"，然后按 `kb(workbench.action.chat.submit)` 发送请求。

    请注意这个聊天提示是如何构建的，以向 Copilot 提供清晰简洁的指令。让我们分解一下：

    * `@workspace` 是一个 *聊天参与者*，这些是可以在特定领域执行任务或回答问题的领域专家。在这种情况下，`@workspace` 了解 VS Code 工作区和您的代码库。

    * `/new` 是一个 *斜杠命令*，告诉 `@workspace` 参与者您想要创建一个新的工作区。斜杠命令是常用指令的简写。您可以在聊天输入中输入 `/` 符号以获取支持的命令列表。

1. Copilot 返回一个表示新工作区文件的文件树，以及一个创建工作区的按钮。
![VS Code Copilot Chat视图的屏幕截图，显示了一个新工作区的文件树和“创建工作区”按钮。](./images/getting-started-chat/copilot-chat-view-workspace-file-tree.png)

您可以在文件树中选择任何文件来预览内容，在文件实际创建之前。如果您对生成的文件不满意，或者想要不同的内容，您可以提出后续问题，例如“@workspace use ejs”来使用EJS而不是Pug。

1. 选择**创建工作区**来创建一个新工作区，并选择磁盘上的一个文件夹作为工作区的创建位置。

    当工作区创建完成后，VS Code将重新加载新工作区。

祝贺您！您刚刚使用Copilot Chat通过自然语言创建了一个工作区。这种方法的优势在于您可以根据需要调整请求。也许您更喜欢使用Express.js和EJS，或者根本不使用Express.js而使用纯Node.js和Bootstrap。选择您最喜欢的选项！

## 使用聊天参与者

之前，您使用了`@workspace`聊天参与者来生成一个新工作区，但您也可以使用它来询问工作区中实际代码的问题。

让我们对生成的Express应用进行迭代，并添加一个新页面。

1. 在聊天视图中，输入“@workspace how to add a new page?”

    ![VS Code Copilot Chat视图的屏幕截图，显示添加页面的结果。](./images/getting-started-chat/copilot-chat-view-add-page.png)

    Copilot返回了添加新页面的逐步说明，这些说明是针对您的代码的。这是因为您在聊天提示中添加了`@workspace`，它具有关于您特定工作区内容的上下文。如果您不包含`@workspace`，您将获得更通用的说明。

1. 可选地，按照说明在您的应用中添加一个新页面。

    > [!TIP]
    > 您可以添加更多关于您想要添加的页面类型的详细信息，例如主页、联系页面或产品页面。

1. 还有更多聊天参与者可供您使用，每个参与者都有其特定领域的专业知识。选择`@`图标或在聊天视图中直接输入`@`以获取可用聊天参与者的列表。

    ![VS Code Copilot Chat视图的屏幕截图，显示聊天参与者的列表。](./images/getting-started-chat/copilot-chat-view-participants.png)

    > [!NOTE]
    > 扩展程序也可以贡献聊天参与者，因此列表可能会根据您在VS Code中安装的扩展程序而有所不同。

1. 让我们使用`@vscode`来设置调试。在聊天输入字段中输入“@vscode /startDebugging”。

    您将获得关于如何在VS Code中调试Node.js应用的说明，并且还会得到一个按钮，直接访问相应的VS Code功能。

    ![VS Code Copilot Chat视图的屏幕截图，显示结果和一个打开VS Code命令面板的按钮。](./images/getting-started-chat/copilot-chat-view-node-debugging.png)

## 使用内联聊天保持流程

虽然聊天视图对于与Copilot保持对话非常有用，但在某些特定场景下，直接从编辑器访问聊天可能会更有效。例如，在审查代码更改、编写单元测试或重构代码时。

让我们看看如何使用聊天进行代码重构。
1. 在编辑器中打开 `app.ts` 文件，并将光标放在设置端口号的行上（`const port = 3000`）。

    对于更复杂的代码更改，您可以选择一个代码块，为 Copilot 提供更多关于您想要更改的内容的上下文。

1. 按下 `kb(inlinechat.start)` 键盘快捷键调出 Copilot 内联聊天，或者右键点击并选择 **Copilot** > **在编辑器中启动**。

    Copilot 内联聊天使您能够直接从编辑器中向 Copilot 提问。

    ![VS Code 编辑器的屏幕截图，突出显示内联聊天弹出控件。](./images/getting-started-chat/copilot-inline-chat-popup.png)

    现在让我们请求 Copilot 重构代码，使端口号可配置。

1. 在聊天输入框中输入 *使其可配置* 并按下 `kbstyle(Enter)`。

    注意 Copilot 如何更新选定的代码并建议从环境变量中读取端口号。

    ![VS Code 编辑器的屏幕截图，显示建议的代码更改。](./images/getting-started-chat/copilot-inline-chat-configurable-port.png)

    您可以通过选择 **更多操作** > **切换更改** 来查看应用的更改。

    ![VS Code 内联聊天的屏幕截图，突出显示“更多操作”控件和差异编辑器。](./images/getting-started-chat/copilot-inline-chat-show-changes.png)

1. 选择 **接受** 或 **关闭** 来应用或忽略更改。

    如果您对建议的代码更改不满意，可以选择 **重新运行请求** 按钮以获取另一个建议。

祝贺您在编辑器中使用 Copilot 内联聊天来帮助您进行代码重构！

## 使用智能操作

在一些常见场景中，您可能直接调用 Copilot，而无需输入聊天提示。例如，Copilot 可以帮助添加代码文档、生成单元测试，或帮助您修复编码错误。

让我们看看如何使用智能操作来修复编码错误。

1. 打开 `app.ts` 文件并选择一个带有红色波浪线的符号。

1. 选择闪光图标查看 Copilot 代码操作，然后选择 **使用 Copilot 修复**。

    ![VS Code 的屏幕截图，突出显示闪光图标和 Copilot 智能操作上下文菜单。](./images/getting-started-chat/copilot-smart-action-fix.png)

1. Copilot 内联聊天会弹出，预填充了错误消息，并提供解决问题的建议。

    ![VS Code 内联聊天的屏幕截图，显示修复智能操作的结果。](./images/getting-started-chat/copilot-smart-action-fix-suggestion.png)

    注意 Copilot 如何使用 `/fix` 斜杠命令，后跟错误消息。您也可以直接在聊天输入框中使用 `/fix` 命令来获取修复编码错误的帮助。

除了 **修复** 之外，Copilot 还提供了更多的智能代码操作，例如 **解释**（/explain）、**生成文档**（`/doc`）和 **生成测试**（`/tests`）。您可以通过编辑器上下文菜单访问这些操作，然后选择 **Copilot**。

![VS Code Copilot 智能操作上下文菜单的屏幕截图。](./images/getting-started-chat/copilot-smart-action-menu.png)

如果您遇到一些不清楚的代码块，只需选择它并使用 `/explain` 来让 Copilot 为您提供解释并帮助提高您的代码理解。

## 添加聊天上下文
以前，您使用 `@workspace` 来询问有关工作区的问题。如果您想向 Copilot 询问特定内容，比如某个特定文件或代码中的某个符号，您该如何提供这些上下文信息，而不必在自然语言中详细描述一切呢？

让我们向 Copilot 询问工作区中某个特定文件的用途。

1. 从命令中心的聊天菜单中打开聊天视图，或按 `kb(workbench.action.chat.open)`。

1. 选择聊天输入字段旁边的 **附加上下文** 按钮，打开上下文快速选择。

    ![VS Code Copilot 聊天视图的截图，显示附加上下文按钮和上下文快速选择。](./images/getting-started-chat/copilot-chat-view-attach-context.png)

    在上下文快速选择中，您可以选择添加到聊天提示的不同类型的上下文，例如工作区中的文件、符号、当前选择等。

1. 在上下文快速选择中，开始输入 `index.ts`，然后选择 `src\types\index.ts` 文件。

    ![VS Code 上下文快速选择的截图，突出显示选中的 'index.ts' 文件。](./images/getting-started-chat/copilot-chat-view-attach-context-file.png)

    选择文件后，请注意文件已添加到聊天视图中。您可以选择添加更多文件或其他类型的上下文到您的聊天提示中。

1. 现在在聊天输入字段中输入以下提示："@workspace 这是做什么用的？"。然后，按 `kbstyle(Enter)` 发送请求。

    ![VS Code Copilot 聊天视图的截图，显示附加文件上下文的聊天提示。](./images/getting-started-chat/copilot-chat-view-context-prompt.png)

    Copilot 现在会返回关于所选文件中代码用途的解释。

1. 除了使用 **附加上下文** 控件外，您还可以通过在聊天输入字段中输入 `#` 来直接引用不同类型的上下文。

    > [!TIP]
    > 添加 `#codebase` 以将整个工作区作为上下文添加到您的聊天提示中。这在您想询问与项目不同区域相关的问题时非常有用。

1. 要快速将文件作为聊天提示的上下文附加，您可以从资源管理器视图中拖放文件到聊天视图。如果文件在编辑器中打开，您还可以将编辑器标签拖放到聊天视图中以附加文件。

    <video src="images/copilot-chat/copilot-attach-dnd.mp4" title="将文件和编辑器拖放到聊天中" autoplay loop controls muted></video>

## 祝贺

祝贺您成功使用 [GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat) 扩展进行 AI 驱动的对话，以帮助重构您的代码、解决问题或提高代码理解。

## 其他资源

* 了解 [VS Code 中的 Copilot Chat](/i18n/zh-cn/docs/copilot/copilot-chat.md) 的概览
* 通过 [提示制作和上下文设置](/i18n/zh-cn/docs/copilot/prompt-crafting.md) 优化您的 Copilot 体验