---
Order: 6
Area: copilot
TOCTitle: Copilot 聊天
ContentId: 130ecf6c-6f06-4ddd-8b1d-f85f023af77b
PageTitle: 使用 GitHub Copilot 进行 AI 驱动的聊天对话
DateApproved: 03/05/2025
MetaDescription: 在 VS Code 中通过 AI 驱动的聊天对话与 GitHub Copilot 互动，以生成代码、增强代码理解，甚至配置您的编辑器。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中使用 Copilot 聊天

在 Visual Studio Code 中使用 Copilot 聊天，您可以通过聊天提问来获取代码建议、增强代码理解，甚至配置您的编辑器。与其在文档或在线论坛中搜索答案，不如直接在 VS Code 中询问 Copilot，并立即将建议应用到您的代码库中。

除了通过聊天获取建议外，Copilot 还可以直接在您的项目中跨多个文件进行编辑。在这种情况下，您可以考虑使用 [Copilot 编辑](/i18n/zh-cn/docs/copilot/copilot-edits.md)。您可以轻松地将现有的聊天对话转移到 [Copilot 编辑](/i18n/zh-cn/docs/copilot/copilot-edits.md#send-a-chat-request-to-copilot-edits)。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup)来免费使用 Copilot，并获得每月的完成和聊天互动限制。

## 在 VS Code 中访问 Copilot 聊天

您可以根据您的工作流程，以多种方式向 VS Code 中的 Copilot 提交提示。

* [**聊天视图**](#chat-view)：在侧边有一个 AI 助手来帮助回答问题并提供代码建议 (`kb(workbench.action.chat.open)`)。
* [**内联聊天**](#inline-chat)：直接从编辑器或集成终端开始内联聊天对话，以在原地获取建议 (`kb(workbench.action.terminal.chat.start)`)。
* [**快速聊天**](#quick-chat)：快速提问并返回到您正在做的事情 (`kb(workbench.action.quickchat.toggle)`)。

要访问聊天体验，请使用相应的键盘快捷键或使用 VS Code 标题栏中的 Copilot 菜单。

![VS Code 命令中心中 Copilot 聊天菜单的屏幕截图](images/copilot-chat/copilot-chat-menu-command-center.png)

## 提交您的第一个提示

您可以要求 Copilot 聊天提供代码建议、增强代码理解、为您的项目设置调试，或帮助配置 VS Code。

1. 使用 (`kb(workbench.action.chat.open)`) 键盘快捷键打开聊天视图，或在标题栏中的 Copilot 菜单中选择 **打开聊天**。

    如果您想使用聊天直接在活动编辑器中进行编辑，请改用 [内联聊天](#inline-chat) (`kb(workbench.action.terminal.chat.start)`)。

1. 在聊天输入字段中输入您的提示，或选择提示建议之一。

    一些示例提示：
* 询问有关编码和技术概念的问题（_"什么是链表？"_, _"十大流行网络框架"_)
* 针对如何最佳解决编码问题进行头脑风暴（_"如何为我的项目添加身份验证？"_)
* 解释一段代码（_"@workspace /explain"_, _"这段代码做什么？"_)
* 提出代码修复建议（_"@workspace /fix"_, _"这个方法会引发FileNotFoundException"_)
* 生成单元测试用例或代码文档（_"@workspace /tests"_, _"@workspace /doc"_)
* 询问VS Code设置（_@vscode 如何禁用小地图？_）

有关更多提示示例，请参阅GitHub文档中的[Copilot聊天食谱](https://docs.github.com/en/copilot/example-prompts-for-github-copilot-chat)。

1. 审查Copilot的响应。

    响应可能包含文本、代码块、按钮、指向代码符号的链接、文件树或其他丰富内容。了解如何[将代码建议应用](#apply-a-code-block-from-chat)到您的代码库中。

    要查看Copilot用于响应的资源，请在聊天响应中选择**使用了n个资源**下拉菜单。通过[向您的聊天提示添加上下文](#add-context-to-your-chat-prompt)，您可以帮助Copilot提供更相关的答案。

1. 可选地，提出后续问题以完善响应。

    随着对话的继续，Copilot会维护[您的聊天消息和响应的历史记录](#chat-history)。

    要开始新的聊天会话，请在聊天视图中使用**新聊天**（`kbstyle(+)`）按钮（`kb(workbench.action.chat.newChat)`）。

> [!TIP]
> 在聊天输入字段中输入`/help`，获取有关GitHub Copilot以及如何与Copilot聊天交互的帮助。

## 更改AI模型

不同的超大规模语言模型（LLM）在不同的数据上进行训练，可能具有不同的能力和优势。使用Copilot，您可以选择不同的模型，以获得最适合您需求的结果。

使用聊天输入字段中的模型选择器来更改Copilot用于生成响应的模型。

可用的模型列表可能因您的Copilot订阅而异，并且可能会随时间变化。有关[可用的语言模型](https://docs.github.com/en/copilot/using-github-copilot/ai-models/changing-the-ai-model-for-copilot-chat?tool=vscode)的更多信息，请参阅GitHub Copilot文档。

## 向您的聊天提示添加上下文

Copilot会根据您的自然语言聊天提示来确定您的问题的意图和范围。在聊天响应中，选择**使用了n个资源**下拉菜单，以查看Copilot用于生成响应的资源。

为了帮助Copilot为您提供最佳和最相关的答案，请向您的聊天提示添加上下文。例如，附加特定文件、特定代码符号、当前编辑器选择等。获取有关[向您的聊天提示添加上下文](/i18n/zh-cn/docs/copilot/copilot-chat-context.md)的更多详细信息。

> [!TIP]
> 通过在提示中添加`#codebase`，让Copilot自动查找正确的文件。确保启用`setting(github.copilot.chat.codesearch.enabled)`（预览）设置，以获得最佳结果。

## 聊天参与者
_聊天参与者_ 就像具有特定专长的领域专家，他们可以帮助您。您可以通过在聊天输入框中输入 '@' 符号，后跟参与者名称来调用聊天参与者。有几个内置的聊天参与者，扩展也可以贡献聊天参与者。

要列出所有已安装的聊天参与者，请在聊天输入框中输入 `@`。

| 内置参与者 | 描述 |
|------------|-----|
| `@workspace` | 了解您的工作区中的代码。使用它来导航您的代码库，查找相关的类、文件等。<br/><br/>**示例提示：**<br/><ul><li>`@workspace 通知是如何调度的？`</li><li>`@workspace 添加表单验证，类似于新闻通讯页面`</li></ul> |
| `@vscode` | 了解 VS Code 的功能、设置和 API。<br/><br/>**示例提示：**<br/><ul><li>`@vscode 当 vscode 假打开文件时那个东西的名称是什么？如何禁用它？`</li></ul> |
| `@terminal` | 了解集成终端 shell 及其内容。<br/><br/>**示例提示：**<br/><ul><li>`@terminal 如何撤销最后一次提交`</li><li>`@terminal 帮助处理 #terminalLastCommand`</li></ul> |
| `@github` | 了解并具备 GitHub 仓库问题、PR 等的技能。还可以使用 Bing API 进行网络搜索。获取更多关于[使用 GitHub 技能](https://docs.github.com/en/copilot/using-github-copilot/asking-github-copilot-questions-in-your-ide#using-github-skills-for-copilot)的信息。<br/><br/>**示例提示：**<br/><ul><li>`@github 分配给我的所有开放 PR 是什么？`</li><li>`@github #web 最新的 VS Code 版本是什么`</li></ul> |

### 扩展贡献的聊天参与者

您可以从 [Visual Studio Code Marketplace](https://marketplace.visualstudio.com/search?term=tag%3Achat-participant&target=VSCode&category=All%20categories&sortBy=Relevance) 或 [GitHub Marketplace](https://github.com/marketplace) 安装额外的聊天参与者。

通过 VS Code 扩展贡献的聊天参与者是 _客户端_ 扩展，它们可以完全访问 VS Code 扩展 API 表面。

通过 GitHub App 贡献的聊天参与者不会在您的本地机器上运行，并且必须明确请求访问您的本地编辑器上下文。在您安装一个贡献聊天参与者的 GitHub App 后，您第一次在 VS Code 中 `@-提及` 该参与者时，会被要求授权其访问您的本地编辑器上下文。

> [!NOTE]
> 为了保护您的隐私，您与来自 GitHub App 的聊天参与者共享编辑器上下文的偏好是按工作区保存的，除非您选择“允许所有工作区”。

这些是贡献聊天参与者的 VS Code 扩展的一些示例。请访问 [Marketplace](https://marketplace.visualstudio.com/search?term=tag%3Achat-participant&target=VSCode&category=All%20categories&sortBy=Relevance) 或使用集成的扩展视图 (`kb(workbench.view.extensions)`) 并按标签 `chat-participant` (`tag:chat-participant`) 搜索。

<div class="marketplace-extensions-chat"></div>

## 斜杠命令

_斜杠命令_ 提供了一种快捷方式，可以避免您编写复杂的提示。要在您的提示中使用斜杠命令，请输入 `/` 字符，后跟一个命令。聊天参与者可以贡献自己的斜杠命令。
例如，`@workspace /new Express app with pug and typescript` 是一个快捷方式，用于生成一个新的工作区并搭建一个使用 Pug 视图引擎的 TypeScript Express 应用程序。

一些常见的内置斜杠命令包括：

* `/clear`：开始一个新的聊天会话
* `/help`：获取关于使用 GitHub Copilot 的帮助
* `@workspace /explain`（或 `/explain`）：解释所选代码的工作原理
* `@workspace /fix`（或 `/fix`）：为所选代码中的问题提出修复建议
* `@workspace /new`（或 `/new`）：为新工作区或新文件搭建代码

要列出所有可用的斜杠命令，请在聊天输入框中输入 `/`。

## 聊天变量

使用聊天变量在提示中包含特定上下文。要使用聊天变量，请在聊天提示框中输入 `#`，然后输入聊天变量。例如，`#codebase` 让 Copilot 查找相关文件以添加为上下文，或 `#selection` 将当前编辑器选择添加到您的聊天提示中。

获取更多关于[向聊天提示添加上下文](/i18n/zh-cn/docs/copilot/copilot-chat-context.md)的信息。

## 内联聊天

要直接在编辑器中进行编辑，请使用内联聊天提交提示。Copilot 在编辑器中与您的代码一起提供代码建议。如果您在编辑器中选择了一块代码，Copilot 会将您的问题限定在该选择范围内。

![Copilot 内联聊天请求不要使用递归来计算阶乘函数。](images/copilot-chat/inline-chat-no-recursion.png)

要调出编辑器内联聊天：

* 在任何文件中，使用 `kb(inlinechat.start)` 键盘快捷键。
* 或者，打开一个文件，然后从标题栏中的 Copilot 菜单中选择 **编辑器内联聊天**。

在接收到代码建议后，您可以接受（`kb(inlineChat.acceptChanges)`）或丢弃（`kb(inlineChat.close)`）更改。如果您对建议不满意，输入一个新的提示，Copilot 将提供新的建议。

您不仅限于请求代码更改。使用内联聊天来提出在处理代码库时出现的更多探索性问题。例如，使用提示如“解释这段代码”，或“如何添加功能来做 X？”。
> [!TIP]
> 将上下文附加到您的内联聊天提示中，以包括相关文件、代码符号或其他上下文。了解更多关于[向聊天提示添加上下文](/i18n/zh-cn/docs/copilot/copilot-chat-context.md)的信息。

## 聊天视图

聊天视图是一个专用视图，在您处理代码时保持打开非常有用，您可以在此与 Copilot 进行多轮对话。

![Copilot 聊天视图在次要侧边栏和资源管理器视图在主要侧边栏中。](images/copilot-chat/copilot-chat-view.png)

要打开聊天视图：

* 使用 `kb(workbench.action.chat.open)` 键盘快捷键。
* 或者，在标题栏中的 Copilot 菜单中选择 **打开聊天**。

默认情况下，聊天视图位于次要侧边栏。[次要侧边栏](/i18n/zh-cn/docs/configure/custom-layout.md#secondary-side-bar)总是位于与主要侧边栏相对的位置，因此您可以同时打开聊天视图和资源管理器、源代码控制或主要侧边栏中的其他视图。

> [!TIP]
> 您可以随时拖动聊天视图到其他位置，甚至将其作为编辑器打开。了解更多关于[VS Code 中的自定义布局](/i18n/zh-cn/docs/configure/custom-layout.md)的信息。

### 从聊天中应用代码块
聊天响应可能包含一个或多个代码块。根据语言扩展，聊天响应中的代码块可能支持 IntelliSense，这使您可以通过悬停在方法和符号上获取有关它们的信息，或跳转到它们的定义。

要将代码块应用到您的代码库中，请悬停在代码块上并选择**应用到编辑器**按钮。Copilot 会尝试将提议的更改应用到您现有的代码中。

![Copilot 聊天代码块响应的屏幕截图，突出显示应用更改的操作。](images/copilot-chat/copilot-chat-view-code-block-actions.png)

代码块可用的其他操作包括：

* 在当前光标位置插入代码块
* 将代码块复制到剪贴板
* 将代码块插入到集成终端中
* 将代码块插入到新文件中

如果 Copilot 聊天检测到代码块包含 shell 命令，您可以使用**插入到终端**（`kb(workbench.action.chat.runInTerminal)`）直接在集成终端中运行它。此选项会创建或打开活动终端，并插入命令文本，准备您运行。

![Copilot 聊天代码块列出文件，显示插入到终端选项](images/copilot-chat/run-in-terminal.png)

> [!TIP]
> 使用**聊天：下一个代码块**（`kb(workbench.action.chat.nextCodeBlock)`）和**聊天：前一个代码块**（`kb(workbench.action.chat.previousCodeBlock)`）在代码块之间导航。

您可以使用以下设置控制聊天中代码块的字体：

* `setting(chat.editor.fontFamily)`
* `setting(chat.editor.fontSize)`
* `setting(chat.editor.fontWeight)`
* `setting(chat.editor.lineHeight)`

### 聊天历史

在任何时候，您都可以使用聊天视图中的**新聊天**按钮（`kb(workbench.action.chat.newChat)`）开始一个新的聊天会话。这对于询问 Copilot 关于不同主题的问题并避免之前的上下文和历史记录很有用。

Copilot 聊天维护您之前聊天会话的历史记录，您可以通过聊天视图中的**显示聊天...**按钮或在命令面板中使用**聊天：显示聊天...**命令来访问这些历史记录。

快速选择会显示按最近排序的之前聊天的列表。您可以选择一个聊天在聊天视图中打开它。

![聊天视图的屏幕截图，突出显示显示聊天...按钮](images/copilot-chat/copilot-chat-view-show-chats.png)

在聊天会话中，您可以从该会话的对话历史中删除特定的提示和相应的响应。悬停在提示上并选择**x**控件。删除一个或多个提示可能有助于获得更相关的响应。

![聊天视图中显示多个提示，突出显示删除聊天提示和响应的'x'控件。](images/copilot-chat/copilot-chat-delete-prompt.png)

您可以使用命令面板中的**聊天：导出聊天...**命令将聊天会话的所有提示和响应导出到 JSON 文件中。

## 快速聊天

如果您想向 Copilot 快速提问，而不想开始一个完整的聊天视图会话或在编辑器中打开内联聊天，您可以使用快速聊天下拉菜单。

![快速聊天下拉菜单](images/copilot-chat/quick-chat-dropdown.png)
按键盘上的 `kb(workbench.action.quickchat.toggle)` 可以调出快速聊天。或者，在标题栏的 Copilot 菜单中选择 **快速聊天**。

如果您想继续对话，可以通过下拉菜单右上角的 **在聊天视图中打开** 按钮，将快速聊天对话提升为完整的聊天视图会话。

![快速聊天在聊天视图中打开按钮](images/copilot-chat/open-in-chat-view.png)

## 终端内联聊天

类似于[编辑器中的内联聊天](#inline-chat)，您可以在终端中调出 Copilot 内联聊天，以帮助您回答与终端和 shell 命令相关的问题。

终端内联聊天使用 `@terminal` [聊天参与者](#chat-participants)，它具有关于集成终端的 shell 及其内容的上下文。例如，您可以询问“如何安装 npm 包”，或“列出 src 目录中最大的 5 个文件”。

要在终端中启动内联聊天，请在终端中按 `kb(inlinechat.start)` 键盘快捷键。

![显示您可以询问复杂问题如“列出 src 目录中最大的 5 个文件”的截图](images/copilot-chat/terminal-chat-2.png)

一旦建议了一个命令，使用 **运行** (`kb(workbench.action.terminal.chat.runCommand)`) 在终端中运行该命令，或使用 **插入** (`kb(workbench.action.terminal.chat.insertCommand)`) 将命令插入到终端中。

## 智能操作

对于几种常见场景，您可以使用 _智能操作_ 来获取 Copilot 的帮助，而无需编写提示。例如，这些智能操作适用于生成提交消息、生成文档、修复代码、解释代码或审查代码更改等任务。

这些智能操作在 VS Code UI 中随处可用。例如，您可以通过编辑器上下文菜单或通过快速修复操作访问 Copilot 智能操作。

在编辑器中，您可以通过选择一段代码，右键点击，然后选择 **Copilot** 来访问智能操作。

![编辑器上下文菜单中展开的 Copilot 菜单组](images/copilot-chat/copilot-smart-action-menu.png)

最强大的智能操作是 **修复** 操作，它帮助您纠正编码问题。选择编辑器中的 _闪光_ 图标，然后选择 **使用 Copilot 修复**。对应有 `/fix` 斜杠命令。

![通过使用 Copilot 智能操作快速修复类型不匹配错误](images/copilot-chat/smart-action-fix-with-copilot.png)

同样，有一个 **Copilot** > **生成文档** 智能操作（`/doc` 斜杠命令）来为您的代码生成文档。

## 使用语音交互

通过 [VS Code Speech](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-speech) 扩展提供的 VS Code 语音控制功能，您可以使用语音启动聊天对话：

* 使用语音口述您的聊天提示
* 使用“Hey Code”语音命令启动与 Copilot Chat 的语音会话
* 通过使用“按住说话”模式加速聊天语音输入

了解更多关于如何[在 VS Code 中使用语音交互](/i18n/zh-cn/docs/configure/accessibility/voice.md)。

## 隐私和透明度
要为私有仓库启用更多工作区搜索功能，我们需要额外的权限。如果我们检测到尚未拥有这些权限，我们将在启动时请求这些权限。一旦获得授权，我们将安全地存储会话以备将来使用。

![请求私有仓库额外身份验证的模态窗口。](images/copilot-chat/authentication.png)

了解更多关于安全性、隐私和透明度的信息，请访问 [GitHub Copilot 信任中心](https://resources.github.com/copilot-trust-center/)。

## 常见问题

### 如何在 Copilot Edits、Inline Chat、Chat view 和 Quick Chat 之间进行选择？

下表提供了每个界面的功能比较。

| 功能                   | Copilot Edits | Chat view | Inline Chat | Quick Chat |
|------------------------------|:-------------:|:---------:|:-----------:|:----------:|
| 接收代码建议     | ✅ | ✅ | ✅ | ✅  |
| 多文件编辑             | ✅ | ✅* |    | ✅* |
| 在编辑器中预览代码编辑 | ✅ |     | ✅ |     |
| 代码审查流程             | ✅ |     |    |      |
| 回滚更改            | ✅ |     |    |      |
| 附加上下文               | ✅ | ✅ | ✅ | ✅  |
| 使用参与者和命令  |    | ✅  |    | ✅  |
| 生成 shell 命令      |    | ✅  |    | ✅  |
| 通用聊天         |    | ✅  | ✅ | ✅  |

\* _代码块包含在聊天对话中，需要手动应用到正确的文件_

## 其他资源

您可以阅读更多关于 [GitHub Copilot](https://github.com/features/copilot) 的信息，以及如何在 VS Code 中使用它的 [GitHub Copilot 文档](https://docs.github.com/copilot/getting-started-with-github-copilot?tool=vscode)。

或者查看 YouTube 上的 [VS Code Copilot 系列](https://www.youtube.com/playlist?list=PLj6YeMhvp2S5_hvBl2SE-7YCHYlLQ0bPt)，您可以找到更多介绍内容和使用 Copilot 与 [Python](https://www.youtube.com/watch?v=DSHfHT5qnGc)、[C#](https://www.youtube.com/watch?v=VsUQlSyQn1E)、[Java](https://www.youtube.com/watch?v=zhCB95cE0HY)、[PowerShell](https://www.youtube.com/watch?v=EwtRzAFiXEM)、[C++](https://www.youtube.com/watch?v=ZfT2CXY5-Dc) 等编程语言的特定视频。

## 下一步

* 开始使用介绍性的 [Copilot Chat 教程](/i18n/zh-cn/docs/copilot/getting-started-chat.md)。

* 使用 [Copilot Edits](/i18n/zh-cn/docs/copilot/copilot-edits.md) 跨多个文件进行编辑。