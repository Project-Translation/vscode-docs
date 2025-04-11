---
Order: 2
Area: copilot
TOCTitle: Copilot 速查表
ContentId: de6f9f68-7dd5-4de3-a210-3db57882384b
PageTitle: 在 VS Code 中使用 GitHub Copilot 的速查表
DateApproved: 2025/03/05
MetaDescription: 快速了解 Visual Studio Code 中 GitHub Copilot 的功能。GitHub Copilot 提供 AI 驱动的功能，帮助您更快、更轻松地编写代码。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中使用 GitHub Copilot 的速查表

在 Visual Studio Code 中，GitHub Copilot 提供 AI 驱动的功能，帮助您更快、更轻松地编写代码。本速查表提供了在 Visual Studio Code 中使用 GitHub Copilot 的功能概览。

您可以通过聊天视图、直接在编辑器中、从集成终端以及通过 VS Code 用户界面的 AI 增强功能访问 GitHub Copilot。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup)免费使用 Copilot，并获得每月的完成和聊天互动限制。

团队正在持续改进 VS Code 中的 Copilot 并添加新功能。有些功能仍处于实验阶段。试用它们并在 [我们的问题](https://github.com/microsoft/vscode-copilot-release/issues) 中分享您的反馈。

## 与 GitHub Copilot 聊天

使用自然语言与 GitHub Copilot 聊天，获取编程任务的帮助。例如，询问 Copilot 解释一段代码或一个编程概念。获取更多关于使用 [Copilot 聊天](/i18n/zh-cn/docs/copilot/copilot-chat.md) 的信息。

| 操作 | 描述 |
|--------|-------------|
| `kb(workbench.action.chat.open)` | 打开 **聊天视图** 并使用自然语言开始与 Copilot 的聊天对话。 |
| `kb(workbench.action.chat.openEditSession)` | 打开 **Copilot 编辑视图** 并开始跨多个文件的代码编辑会话。 |
| `kb(workbench.action.quickchat.toggle)` | 打开 **快速聊天** 并向 Copilot 提问。 |
| `kb(inlinechat.start)` | 启动 **内联聊天**，直接从编辑器向 Copilot 发送聊天请求。使用自然语言或使用 `/` 命令向 Copilot 发出指令。 |
| <i class="codicon codicon-mention"></i> | 在聊天中输入 `@` 或选择 <i class="codicon codicon-mention"></i> 查看 *聊天参与者* 列表，这些参与者是可以在特定领域帮助您的领域专家。扩展也可以贡献额外的参与者。<br/>示例：`@workspace 如何实现身份验证？` |
| 参与者检测 _(实验性)_ | Copilot 聊天还可以自动将您的问题路由到适当的参与者。 [获取更多信息](https://code.visualstudio.com/updates/v1_93#_automatic-chat-participant-detection-in-chat-view-experimental)。 |
| `/` | 调用 *斜杠命令* 提示常用操作，例如解释一段代码、生成测试或文档。 |
| `/explain` | 要求 Copilot 解释一段代码或一个编程概念。 |
| <i class="codicon codicon-history"></i> | 在聊天视图中选择此图标以访问您的聊天会话历史记录。 |
| <i class="codicon codicon-mic"></i> | 使用语音（语音聊天）输入聊天提示。聊天响应将被朗读。 |
> **提示**
>
> - 使用 `/` 命令和 `@` 参与者以获得更精确和相关的回答。
> - 具体明确，保持简单，并提出后续问题以获得最佳结果。
> - 通过附加文件、符号或选择来为您的聊天提示提供上下文。

## 代码编辑会话

使用 Copilot Edits 开始一个代码编辑会话，您可以在其中快速迭代 AI 生成的代码编辑，这些编辑将直接应用于工作区中的多个文件。

| 操作 | 描述 |
|------|------|
| `kb(workbench.action.chat.openEditSession)` | 打开 **Copilot Edits 视图** 并开始跨多个文件的代码编辑会话。 |
| <i class="codicon codicon-plus"></i> | 开始一个新的编辑会话。 |
| 编辑/代理模式 | 在编辑模式和 [代理模式（预览版）](/i18n/zh-cn/docs/copilot/copilot-edits.md#use-agent-mode-preview) 之间切换以使用 Copilot Edits。 |
| `添加文件...` | 附加文件作为编辑的上下文。 |
| `接受` | 接受所有当前编辑。 |
| `丢弃` | 丢弃所有当前编辑。 |
| <i class="codicon codicon-diff-multiple"></i> | 在多文件差异编辑器中查看所有编辑。 |
| <i class="codicon codicon-discard"></i> | 撤销最后一次编辑。 |
| <i class="codicon codicon-redo"></i> | 重做最后一次编辑。 |
| <i class="codicon codicon-eye"></i> | 启用/禁用将活动编辑器作为上下文附加。 |

> **提示**
>
> - 将您希望获取编辑的所有文件添加到您的提示中。
> - 关于您希望 Copilot Edits 进行的更改，请具体且精确。
> - 如果您有一个较大的任务，请将其分解为较小的任务并经常迭代。

## 从聊天生成代码

Copilot 可以根据您的聊天提示生成代码块。快速将生成的代码应用到您的项目中或将其插入到新文件中。例如，请求 Copilot 优化您代码中的算法。

| 操作 | 描述 |
|------|------|
| <i class="codicon codicon-git-pull-request-go-to-changes"></i> | 在活动编辑器中智能应用生成的代码块。 |
| <i class="codicon codicon-insert"></i> | 在光标处插入生成的代码块。 |
| <i class="codicon codicon-copy"></i> | 将生成的代码块复制到剪贴板。 |
| <i class="codicon codicon-terminal"></i> | 将生成的代码块作为 shell 命令插入到终端中。 |
| `插入到新文件` | 将生成的代码块插入到新文件中。 |

> **提示**
>
> - 提供有关要使用的框架或库的详细信息。
> - 考虑创建 [自定义代码生成指令](#customize-ai-code-generation)。

## 将上下文附加到您的提示

当您向 Copilot 发送聊天提示时，您可以附加上下文以帮助 Copilot 更好地理解您的问题。例如，将当前编辑器选择、文件或符号添加到您的聊天提示中。获取更多关于 [使用 Copilot 的最佳实践](/i18n/zh-cn/docs/copilot/prompt-crafting.md) 的信息。
| 操作 | 描述 |
|------|------|
| 附件 <i class="codicon codicon-attach"></i> (`kb(workbench.action.chat.attachContext)`) | 打开快速选择以选择与您的聊天提示相关的上下文。可以从不同的上下文类型中选择，例如工作区文件、符号、当前编辑器选择、终端选择等。 |
| <i class="codicon codicon-eye"></i> | 启用/禁用将活动编辑器作为上下文附加。 |
| `Prompts...` _(实验性)_ | 将可重用的提示指令添加到您的请求中。获取有关[提示文件](/i18n/zh-cn/docs/copilot/copilot-customization.md#reusable-prompt-files-experimental)的更多信息。 |
| 拖放文件 | 将文件或编辑器标签拖放到聊天中，以将文件作为上下文附加。 |
| 拖放文件夹 | 将文件夹拖放到聊天中，以将其中的文件作为上下文附加。 |
| 拖放问题 | 从**问题**面板中拖放项目，以将其作为上下文附加。 |
| 最近文件 _(实验性)_ | 自动在您的聊天提示中包含最近打开和编辑的文件。获取更多信息[获取更多信息](https://code.visualstudio.com/updates/v1_93#_use-recent-coding-files-as-inline-chat-context-experimental)。 |

### 聊天变量

在您的聊天提示中使用聊天变量来引用与您的问题相关的内容。

| 聊天变量 | 描述 |
|----------|------|
| `#changes` | 源代码控制更改列表。 |
| `#codebase` | 将相关的工作区内容作为上下文添加到您的提示中。 |
| `#editor` | 将活动编辑器的可见内容作为上下文添加到您的提示中。 |
| `#file` | 打开快速选择，从您的工作区中选择一个文件并将其作为上下文添加到您的提示中。 |
| `#<filename>` | 输入 `#`，后跟文件名，以获取工作区文件的文件名建议并作为上下文附加。 |
| `#folder` | 输入 `#folder:`，后跟文件夹名称，从您的工作区中选择一个文件夹并将其作为上下文添加到您的提示中。添加文件夹会将其中所有文件作为上下文添加。 |
| `#problems` | 将工作区问题和来自**问题**面板的问题作为上下文添加。在修复代码或调试时很有用。 |
| `#selection` | 将当前编辑器选择作为上下文添加到您的提示中。 |
| `#sym` | 打开快速选择，从您的工作区中选择一个符号并将其作为上下文添加到您的提示中。 |
| `#<symbol>` | 输入 `#`，后跟符号名称，以获取工作区文件的符号建议并作为上下文附加。 |
| `#terminalSelection` | 将当前终端选择作为上下文添加到您的聊天提示中。 |
| `#terminalLastCommand` | 将最近运行的终端命令作为上下文添加到您的聊天提示中。 |
| `#testFailure` | 将测试失败信息作为上下文添加。在运行和诊断[测试](/i18n/zh-cn/docs/debugtest/testing.md)时很有用。 |
| `#VSCodeAPI` | 将 VS Code API 作为上下文添加到您的提示中，以询问与 VS Code 扩展开发相关的问题。 |

## 编辑器中的 Copilot

当您在编辑器中编写代码时，您可以使用 Copilot 来生成代码补全。调用内联聊天来提问并从 Copilot 获得帮助，同时保持编写代码的流程。例如，请求 Copilot 为函数或方法生成单元测试。获取有关[代码补全](/i18n/zh-cn/docs/copilot/ai-powered-suggestions.md)和[内联聊天](/i18n/zh-cn/docs/copilot/copilot-chat.md#inline-chat)的更多信息。
| 操作 | 描述 |
|------|------|
| 代码补全 | 在编辑器中开始输入，Copilot 会根据您的编码风格和现有代码提供代码建议。 |
| 代码注释 | 通过在代码注释中编写指令，向 Copilot 提供代码补全提示。<br/>示例：`# 编写一个计算器类，包含加、减、乘的方法。使用静态方法。` |
| 下一个编辑建议 _(预览版)_ | 使用 Copilot 下一个编辑建议预测您的下一个代码编辑。通过 `setting(github.copilot.nextEditSuggestions.enabled)` 设置启用 Copilot NES。了解如何开始使用 [Copilot NES](/i18n/zh-cn/docs/copilot/ai-powered-suggestions.md#next-edit-suggestions-preview)。 |
| `kb(inlinechat.start)` | 启动 **内联聊天**，直接从编辑器向 Copilot 发送聊天请求。使用自然语言或使用 `/` 命令向 Copilot 发出指令。 |
| 从编辑器提示 _(实验性)_ | 直接在代码中输入自然语言，Copilot 会检测到您不是在编写代码而是在提示，并会自动启动内联聊天以处理您的提示。 |
| `kb(editor.action.rename)` | 在重命名代码中的符号时获取 AI 驱动的建议。 |

> **提示**
>
> - 使用有意义的方法或函数名称可以更快地获得更好的代码补全。
> - 选择代码块以限定您的内联聊天提示，或通过附加文件或符号来附加相关上下文。
> - 使用编辑器上下文菜单选项，直接从编辑器访问常用的 Copilot 操作。

## 自定义 AI 代码生成

定义 [自定义指令](/i18n/zh-cn/docs/copilot/copilot-customization.md#custom-instructions)，帮助 Copilot 生成或审查符合您的团队或项目编码风格、工具和开发者工作流程的代码。

通过可重用的提示文件，您可以在 Markdown 文件 (`*.prompt.md`) 中指定常见的提示指令和相关内容，然后在您的聊天提示中重用这些文件。
| 操作 | 描述 |
|------|------|
| 文件基础指令 | 在工作区的 `.github/copilot-instructions.md` 文件中定义代码生成的共享指令。这些常用指令补充您自己的个人代码生成指令。 |
| 代码审查指令 _(预览版)_ | 在设置中或从文件导入，定义使用 Copilot 审查编辑器选定内容的指令。您可以定义特定语言的指令。 |
| 代码生成指令 _(实验性)_ | 在设置中或从文件导入，定义使用 GitHub Copilot 进行代码生成的指令。您可以定义特定语言的指令。 |
| 测试生成指令 _(实验性)_ | 在设置中或从文件导入，定义使用 GitHub Copilot 进行测试生成的指令。您可以定义特定语言的指令。 |
| 提交消息生成指令 _(实验性)_ | 在设置中或从文件导入，定义使用 GitHub Copilot 生成提交消息的指令。您可以定义特定语言的指令。 |
| 拉取请求标题和描述生成指令 _(实验性)_ | 在设置中或从文件导入，定义使用 GitHub Copilot 生成拉取请求标题和描述的指令。您可以定义特定语言的指令。 |
| 可重用提示文件 _(预览版)_ | 在 Markdown 文件中定义带有额外上下文的可重用提示指令，并在聊天提示中使用它们。了解如何[创建可重用提示文件](/i18n/zh-cn/docs/copilot/copilot-customization.md#reusable-prompt-files-preview)。 |

> **提示**
>
> - 定义特定语言的指令，以获得每种语言更准确的生成代码。
> - 将您的指令存储在文件中，以便轻松与团队共享并跨项目使用。

## 审查代码 (实验性)

Copilot 可以对代码块进行快速审查，或者对工作区中未提交的更改进行审查。审查反馈会在编辑器中显示为评论，您可以应用这些建议。

| 操作 | 描述 |
|------|------|
| **审查并评论** _(预览版)_ | 选择一个代码块，然后从编辑器上下文菜单中选择 **Copilot** > **审查并评论** 进行快速审查。 |
| **Copilot 代码审查** | 在源代码控制视图中选择 **Copilot 代码审查** 按钮，对所有未提交的更改进行更深入的审查。加入[等待名单](https://gh.io/copilot-code-review-waitlist)。 |

## 生成测试

Copilot 可以为您代码库中的函数和方法生成测试。获取有关[聊天中的斜杠命令](/i18n/zh-cn/docs/copilot/copilot-chat.md#slash-commands)的更多信息。

| 操作 | 描述 |
|------|------|
| `/tests` | 为编辑器中所有或仅选定的方法和函数生成测试。生成的测试将附加到现有测试文件中，或创建一个新的测试文件。 |
| `/setupTests` | 获取帮助设置您的代码的测试框架。获取相关测试框架的推荐、设置和配置的步骤，以及 VS Code 测试扩展的建议。 |
| `/fixTestFailure` | 向 Copilot 询问如何修复失败的测试的建议。 |
| 测试覆盖率 _(实验性)_ | 为尚未被测试覆盖的函数和方法生成测试。[获取更多信息](https://code.visualstudio.com/updates/v1_93#_generate-tests-based-on-test-coverage-experimental)。 |
> **提示**
>
> - 提供有关要使用的测试框架或库的详细信息。

## 生成文档

为代码库中的函数和方法生成代码文档。获取有关[聊天中的斜杠命令](/i18n/zh-cn/docs/copilot/copilot-chat.md#slash-commands)的更多信息。

| 操作 | 描述 |
|------|------|
| `/docs` | 为编辑器中所有或仅选定的方法和函数生成文档注释。 |

## 调试和修复问题

使用 Copilot 帮助修复编码问题，并在 VS Code 中获取配置和启动调试会话的帮助。

| 操作 | 描述 |
|------|------|
| `/fix` | 向 Copilot 询问如何修复代码块或如何解决代码中的编译器或代码检查错误。例如，帮助修复未解析的 Node.js 包名。 |
| `/fixTestFailure` | 向 Copilot 询问如何修复失败的测试。 |
| `/startDebugging` _(实验性)_ | 生成 `launch.json` 调试配置文件并从聊天视图启动调试会话。[获取更多信息](https://code.visualstudio.com/updates/v1_93#_start-debugging-from-chat-experimental)。 |
| `copilot-debug` 命令 | 终端命令帮助您调试程序。在运行命令前加上此前缀以启动其调试会话（例如，`copilot-debug python foo.py`）。[获取更多信息](https://code.visualstudio.com/updates/v1_96#_debugging-with-copilot)。 |

> **提示**
>
> - 提供您需要的修复类型额外信息，例如优化内存消耗或性能。
> - 注意编辑器中的 Copilot 代码操作，这些操作指示修复代码问题的建议。

## 搭建新项目

Copilot 可以通过生成项目结构的脚手架或根据您的需求生成笔记本来帮助您创建新项目。

| 操作 | 描述 |
|------|------|
| `/new` | 在聊天视图中使用 `/new` 命令来搭建新项目或新文件。使用自然语言描述您需要的项目/文件类型，并在创建前预览脚手架内容。<br/>示例：`/new 使用 typescript 和 svelte 的 Express 应用` |
| `/newNotebook` | 在聊天视图中使用 `/newNotebook` 命令根据您的需求生成新的 Jupyter 笔记本。使用自然语言描述笔记本应包含的内容。<br/>示例：`/newNotebook 获取人口普查数据并使用 Seaborn 预览关键见解` |

## 源代码控制和问题

Copilot 可以分析您提交和拉取请求中的更改，并为提交消息和拉取请求描述提供建议。

| 操作 | 描述 |
|------|------|
| 提交 | 为源代码控制提交中的当前更改生成提交消息。 |
| 拉取请求 | 生成与拉取请求中的更改相对应的拉取请求标题和描述。 |
| `@github` | 在聊天中使用 `@github` 参与者询问您仓库中的问题、拉取请求等。获取有关[可用 GitHub 技能](https://docs.github.com/en/copilot/using-github-copilot/asking-github-copilot-questions-in-your-ide#currently-available-skills)的更多信息。<br/>示例：`@github 我被分配的所有开放 PR 是什么？`，`@github 显示我从 @dancing-mona 最近合并的 PR` |

## 搜索

使用 Copilot 在搜索视图中获取更相关的搜索结果。
| 操作 | 描述 |
|------|------|
| 语义搜索 | 在搜索视图中包含来自 Copilot 的语义相关搜索结果。 |

## 终端

获取有关 shell 命令的帮助，并在终端中运行命令时解决错误。

| 操作 | 描述 |
|------|------|
| `kb(inlinechat.start)` | 在终端内启动内联聊天，使用自然语言快速获取并运行 shell 命令。<br/>示例：`这台机器有多少核心？` |
| <i class="codicon codicon-sparkle"></i> <br/>使用 Copilot 修复 | 在失败的 shell 命令上选择 <i class="codicon codicon-sparkle"></i> 图标，获取解决错误的建议。 |
| <i class="codicon codicon-sparkle"></i> <br/>使用 Copilot 解释 | 在失败的 shell 命令上选择 <i class="codicon codicon-sparkle"></i> 图标，获取关于命令失败原因的解释。 |
| `@terminal` | 在聊天视图中使用 `@terminal` 参与者，询问有关集成终端或 shell 命令的问题。<br/>示例：`@terminal 列出此工作区中最大的5个文件` |
| `@terminal /explain` | 在聊天视图中使用 `/explain` 命令，解释来自终端的内容。<br/>示例：`@terminal /explain top shell 命令` |

## Python 和 Notebook 支持

您可以使用 Copilot Chat 在原生 Python REPL 和 Jupyter 笔记本中帮助您完成 Python 编程任务。

| 操作 | 描述 |
|------|------|
| <i class="codicon codicon-sparkle"></i> 生成<br/>`kb(inlinechat.start)` | 在笔记本中启动内联聊天以生成代码块或 Markdown 块。 |
| `#` | 在聊天提示中附加来自 Jupyter 内核的变量，以获得更相关的响应。 |
| 原生 REPL + `kb(inlinechat.start)` | 在原生 Python REPL 中启动内联聊天并运行生成的命令。 |

## VS Code 命令和 API

您可以使用 Copilot 获取有关 VS Code 功能、设置和 VS Code 扩展 API 的帮助。获取更多关于[聊天参与者](/i18n/zh-cn/docs/copilot/copilot-chat.md#chat-participants)的信息。

| 操作 | 描述 |
|------|------|
| `@vscode` | 使用 `@vscode` 聊天参与者，通过自然语言询问有关 VS Code 的问题。<br/>示例：`@vscode 如何启用自动换行？` |
| `@vscode /runCommand` | 使用 `/runCommand` 与 `@vscode` 聊天参与者一起运行 VS Code 命令。<br/>`@vscode /runCommand 启用开发者模式` |
| `@vscode /search` | 使用 `/search` 与 `@vscode` 聊天参与者一起生成 VS Code 搜索。<br/>示例：`@vscode /search 没有导入的 Python 文件` |

> **提示**
>
> - 如果您询问有关 VS Code 扩展 API 的问题，请使用 `#vscodeAPI` 聊天变量。

## 下一步

- [教程：在 VS Code 中开始使用 GitHub Copilot](/i18n/zh-cn/docs/copilot/getting-started.md)