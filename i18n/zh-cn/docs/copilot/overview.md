---
Order: 1
Area: copilot
TOCTitle: 概述
ContentId: 0aefcb70-7884-487f-953e-46c3e07f7cbe
PageTitle: GitHub Copilot 概述
DateApproved: 2025/03/05
MetaDescription: Copilot 是您在 VS Code 中的 AI 配对编程工具。使用代码补全和内联聊天加速编码。使用 Copilot Edits 添加新功能或解决错误，并使用聊天探索您的代码库。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中使用 GitHub Copilot

[GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) 是您在 Visual Studio Code 中的 AI 配对编程工具。在编辑器中输入时获取代码建议，或使用内联聊天加速编写代码。使用 Copilot Edits 在整个项目中添加新功能或解决错误，或使用自然语言在聊天中探索您的代码库。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup) 免费使用 Copilot，并获得每月的代码补全和聊天互动限制。

GitHub Copilot 可以在多种场景中提供帮助。

<div class="card-grid">
<a href="#_code-completions-in-the-editor" class="card">
    <i class="codicon codicon-keyboard"></i>
    <p class="card-title">在输入时获取代码建议</p>
</a>
<a href="#_iterate-on-changes-across-multiple-files" class="card">
    <i class="codicon codicon-edit-session"></i>
    <p class="card-title">跨多个文件进行更改</p>
</a>
<a href="#_answer-coding-questions" class="card">
    <i class="codicon codicon-comment-discussion"></i>
    <p class="card-title">询问有关您的代码的问题</p>
</a>
<a href="#_code-refactoring-and-improvements" class="card">
    <i class="codicon codicon-lightbulb"></i>
    <p class="card-title">重构和改进您的代码</p>
</a>
<a href="#_fix-issues" class="card">
    <i class="codicon codicon-debug"></i>
    <p class="card-title">修复代码问题和调试</p>
</a>
<a href="#_jumpstart-your-project" class="card">
    <i class="codicon codicon-new-file"></i>
    <p class="card-title">搭建新项目或文件</p>
</a>
<a href="#_generate-unit-test-cases" class="card">
    <i class="codicon codicon-beaker"></i>
    <p class="card-title">配置和生成测试</p>
</a>
<a href="#_generate-code-documentation" class="card">
    <i class="codicon codicon-book"></i>
    <p class="card-title">生成代码文档</p>
</a>
<a href="#_productivity-improvements" class="card">
    <i class="codicon codicon-sparkle"></i>
    <p class="card-title">提高您在 VS Code 中的生产力</p>
</a>
</div>

## 入门

1. 从 VS Code 标题栏中的 Copilot 菜单或命令面板 (`kb(workbench.action.showCommands)`) 中选择 **使用 Copilot 免费使用 AI 功能...**

1. 使用您的 GitHub 账户登录以使用 Copilot

    > [!TIP]
    > 如果您还没有 Copilot 订阅，您可以通过 [Copilot 免费计划](https://github.com/github-copilot/signup) 免费开始使用。按照 [设置指南](/i18n/zh-cn/docs/copilot/setup.md) 中的步骤设置 Copilot 订阅。

1. 通过我们的 [Copilot 快速入门](/i18n/zh-cn/docs/copilot/getting-started.md) 了解 Copilot 在 VS Code 中的关键功能。
## 键盘快捷键

使用以下键盘快捷键与 Copilot 开始聊天对话：

| 快捷键 | 描述 |
|----------|-------------|
| `kb(workbench.action.chat.open)` | 打开**聊天视图**并使用自然语言与 Copilot 开始聊天对话。 |
| `kb(workbench.action.chat.openEditSession)` | 打开**Copilot 编辑视图**并在多个文件中开始代码编辑会话。 |
| `kb(workbench.action.quickchat.toggle)` | 打开**快速聊天**并向 Copilot 提问。 |
| `kb(inlinechat.start)` | 启动**内联聊天**，直接从编辑器向 Copilot 发送聊天请求。使用自然语言或使用 `/` 命令向 Copilot 发出指令。 |

查看我们的 [Copilot 速查表](/i18n/zh-cn/docs/copilot/copilot-vscode-features.md) 以了解 Copilot 命令和快捷键的概览。

## 在 VS Code 中使用 GitHub Copilot 的用例

### 编辑器中的代码补全

* **Copilot 在您输入时建议代码**。Copilot 分析您正在编辑的文件及其相关文件的上下文，并在编辑器内提供建议。例如，开始输入方法名称，Copilot 会根据您的编码风格建议实现。

    ![内联聊天建议实现 'CalculateDaysBetweenDates' JavaScript 函数](images/overview/js-suggest.png)

* **预测您的下一个代码编辑**，使用 Copilot 下一个编辑建议（Copilot NES）（预览版）。根据您正在进行的编辑，Copilot NES 既预测您将要进行的下一个编辑的位置，也预测该编辑的内容。使用 `kbstyle(Tab)` 键快速导航并接受建议。了解如何开始使用 [Copilot NES](/i18n/zh-cn/docs/copilot/ai-powered-suggestions.md#next-edit-suggestions-preview)。

    ![Copilot NES 用于添加 z 到 Point3D 的距离计算](images/overview/point3d-distance.png)

### 在多个文件中迭代更改

* **启动 AI 驱动的代码编辑会话**。 [Copilot 编辑](/i18n/zh-cn/docs/copilot/copilot-edits.md) 将 Copilot 聊天的对话流程和内联聊天的快速反馈结合在一个体验中。在一侧进行持续的多轮聊天对话，同时受益于内联代码建议。

    ![显示“将活动页面设为主页”的 Copilot 编辑响应，并在编辑器中显示差异的屏幕截图。](images/copilot-edits/copilot-edits-changed-files.png)

### 回答编码问题

* **为常见的编码任务和挑战提供指导和支持**。向 Copilot 询问语法或一般编程概念，无需导航文档或在线论坛搜索。Copilot 以自然语言格式或代码片段格式给出响应。例如，您可以问“什么是递归？”或“如何在 Java 中创建单例？”。

    ![Copilot 聊天回答什么是单例](images/overview/copilot-chat-singleton.png)

* **通过解释选定代码提高代码理解**。Copilot 生成代码功能和目的的自然语言描述。这在您想了解代码行为或非技术利益相关者需要了解代码工作原理时很有用。

    ![内联聊天解释所选文本中使用的排序算法](images/overview/inline-chat-question-example.png)
* **提供与您的代码库相关的指导**。Copilot 了解您的工作区环境，可以提供针对您的项目量身定制的逐步指导和代码示例。例如，“如何添加联系人页面？”或“我如何从数据库中读取客户数据？”。

    ![Copilot Chat 提供关于向 Express 应用添加页面的逐步指导](images/getting-started-chat/copilot-chat-view-add-page.png)

### 代码重构和改进

* **提供实现代码重构的建议**。Copilot 根据您的代码库上下文建议重构。例如，要求 Copilot 重构一个函数以避免使用递归，或者建议一种可以提高性能的算法。

    ![内联聊天重构以使用不同的排序算法](images/overview/inline-chat-convert-sort.png)

* **对选定代码提出可能的改进建议**，例如改进错误和边缘情况的处理，或更改逻辑流程以使代码更易读。

    ![Copilot 内联聊天建议改进错误处理](images/overview/copilot-inline-chat-error-handling.png)

### 修复问题

* **提出修复代码中错误的建议**，使用 `/fix` 命令，通过基于错误或问题上下文的代码片段和解决方案。例如，如果您的代码产生错误消息或警告，Copilot Chat 可以根据错误消息、代码语法和周围代码建议可能的修复。更改可能包括对变量、控制结构或函数调用的更改，以解决问题。

    ![内联聊天 /fix 用于错误，建议安装缺失的库](images/overview/inline-chat-fix-error-message-example.png)

* **提出修复失败测试的建议**（预览）。当您运行代码的自动化测试时，Copilot 可以使用 `/fixTestFailure` 命令建议修复失败测试的代码。

    ![Copilot Chat /fixTestFailure 用于识别和建议修复失败的测试](images/overview/copilot-chat-fix-test-failure.png)

* **建议终端命令修复**。当命令在终端中无法运行时，Copilot 会在槽口显示一个闪光，提供快速修复以解释发生了什么。

    ![在终端中失败的终端命令后，选择与 Copilot 修复的选项。](images/overview/terminal-command-explanation.png)

### 启动您的项目

* **生成一个新的 VS Code 工作区**，用于您选择的技术，使用 `/new` 快速开始新项目。选择和选择您的技术栈，预览工作区文件，让 Copilot 为您搭建整个工作区。

    ![请求 @workspace 代理使用 TypeScript 搭建一个新的 Node.js 项目](images/overview/copilot-chat-view-workspace-file-tree.png)

* **使用自然语言搭建一个新的 Jupyter 笔记本**。通过使用 `/newNotebook` 生成一个基于描述预配置的新笔记本。例如，要搭建一个加载、检查和可视化样本数据集的新笔记本，向 Copilot 提示 "@workspace /newNotebook 下载泰坦尼克数据集并使用 MatPlotLib 显示关键信息"。

    ![请求 @workspace 代理搭建一个读取泰坦尼克数据并使用 MatPlotLib 可视化的新笔记本](images/overview/copilot-new-notebook.png)

### 生成单元测试用例
* **根据您的代码库配置测试框架**。例如，如果您有一个JavaScript和TypeScript项目，Copilot将建议适合的测试框架并提供配置步骤以适应您的工作区。

    ![聊天视图显示使用/setupTests斜杠命令为JavaScript和TypeScript设置测试框架](images/overview/copilot-chat-setup-tests.png)

* **为您的测试框架编写单元测试用例**，基于编辑器中打开的代码或您在编辑器中高亮的代码片段。Copilot会识别您的测试框架和编码风格，并生成匹配的代码片段。

    ![聊天视图显示使用/tests斜杠命令为C#计算器类中的Divide方法生成单元测试](images/overview/workspace-agent-tests-example.png)

* **识别并编写边缘情况和边界条件的测试用例**，这些可能难以手动识别。例如，Copilot可以建议错误处理、空值或意外输入类型的测试用例。

* **建议断言**，确保函数正常工作，基于代码的上下文和语义。例如，生成断言以确保函数输入参数有效。

### 生成代码文档

* **为多种语言生成代码文档**，针对编辑器中打开的代码或您在编辑器中高亮的代码片段。使用`/doc`或Copilot智能操作来帮助您生成有意义的代码文档。

    ![内联聊天/doc示例为计算器类生成文档代码注释](images/overview/inline-chat-doc-example.png)

### 生产力提升

* **AI生成的提交消息和PR描述**，基于提交中的代码更改或拉取请求中的更改。在源代码控制视图或GitHub PR扩展中使用*sparkle*按钮生成总结您更改的标题和描述。

    ![悬停在源代码控制输入框的sparkle按钮显示生成提交消息](images/overview/generate-commit-message.png)

* **AI生成的重命名建议**，用于您源代码中的符号。当您重命名代码中的符号时，Copilot会根据符号的上下文和代码库建议新的名称。

    ![内联聊天为Python文件中的符号建议新名称](images/overview/copilot-inline-chat-rename-suggestion.png)

* **语义搜索结果**（预览）。搜索视图列出跨文件的精确文本匹配，此外还列出基于您的搜索文本在语义上相关的匹配。

    ![搜索视图显示与搜索条件不完全匹配的语义搜索结果](images/overview/semantic-search-results.png)

* **使用终端内联聊天**询问关于终端的问题或如何使用特定的shell命令。例如，您可以询问“列出src目录中最大的5个文件”，或“如何启用shell集成”。

    ![屏幕截图显示您可以询问复杂的问题，如“列出src目录中最大的5个文件”](images/overview/terminal-chat-2.png)

## 下一步
* [在 VS Code 中开始使用 Copilot 快速入门](/i18n/zh-cn/docs/copilot/getting-started.md)
* [开始使用 Copilot Edits 跨多个文件进行编辑](/i18n/zh-cn/docs/copilot/copilot-edits.md)
* [快速了解 VS Code 中 Copilot 的功能](/i18n/zh-cn/docs/copilot/copilot-vscode-features.md)

## 其他资源

您可以在 [GitHub Copilot 文档](https://docs.github.com/copilot/getting-started-with-github-copilot?tool=vscode) 中阅读更多关于 Copilot 及其在 VS Code 中的使用方法。

或者查看 YouTube 上的 [VS Code Copilot 系列](https://www.youtube.com/playlist?list=PLj6YeMhvp2S5_hvBl2SE-7YCHYlLQ0bPt)，您可以找到更多介绍性内容和使用 Copilot 与 [Python](https://www.youtube.com/watch?v=DSHfHT5qnGc)、[C#](https://www.youtube.com/watch?v=VsUQlSyQn1E)、[Java](https://www.youtube.com/watch?v=zhCB95cE0HY)、[PowerShell](https://www.youtube.com/watch?v=EwtRzAFiXEM)、[C++](https://www.youtube.com/watch?v=ZfT2CXY5-Dc) 等编程语言的特定视频。