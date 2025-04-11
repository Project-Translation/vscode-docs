---
ContentId: 5dfd207f-fcee-42c3-b7fe-622b42b3397c
PageTitle: 在 VS Code 中使用 GitHub Copilot 的最佳实践
DateApproved: 2025/03/05
MetaDescription: 通过在 VS Code 中使用 GitHub Copilot 的最佳实践，优化您的开发体验，包括如何编写聊天提示和提供上下文。
MetaSocialImage: images/shared/github-copilot-social.png
---
# Copilot Chat 的提示工程

本文介绍了如何编写提示，以从 Visual Studio Code 中的 Copilot Chat 获得更好的、更相关的响应。_提示工程_或_提示制作_是讨论 AI 时常听到的术语，指的是如何以及发送什么信息到 AI API 端点。

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/hh1nOX14TyY" title="使用 GitHub Copilot 的提示工程核心原则" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

如果您是 VS Code 或 GitHub Copilot 的新手，您可能需要先查看 [GitHub Copilot 概述](/i18n/zh-cn/docs/copilot/overview.md) 文章，或者直接进入 [入门](/i18n/zh-cn/docs/copilot/getting-started.md) 教程。

有不同的选项可以优化您的 Copilot 体验，包括内联建议和聊天：

- [充分利用 Copilot 内联建议](#getting-the-most-out-of-copilot-inline-suggestions)
- [充分利用 Copilot Chat](#getting-the-most-out-of-copilot-chat)

## 充分利用 Copilot 内联建议

[GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) 扩展会自动提供[建议](/i18n/zh-cn/docs/copilot/overview.md#Code-completions-in-the-editor)，帮助您更高效地编写代码。您可以做一些事情来帮助（“提示”）Copilot 提供最佳的建议。好消息是，您可能已经在做这些了，因为这些有助于您和您的同事理解您的代码。

### 为 Copilot 提供上下文

当 Copilot 有足够的上下文了解您在做什么以及您需要什么帮助时，它的表现最佳。就像您在请求同事帮助特定编程任务时会提供上下文一样，您也可以对 Copilot 这样做。

#### 打开的文件

对于代码补全，Copilot 会查看您编辑器中当前和打开的文件，以分析上下文并创建适当的建议。在使用 Copilot 时，在 VS Code 中打开相关文件有助于设置这个上下文，让 Copilot 看到您项目的更大图景。

#### 顶级注释

就像您会给同事一个简短的高层次介绍一样，在您正在工作的文件中添加一个顶级注释可以帮助 Copilot 理解您正在创建的部分的整体上下文。

<!-- Example of a good and bad top level comment -->

#### 适当的包含和引用

最好手动设置您工作所需的包含或模块引用。Copilot 可以提供建议，但您可能最清楚需要包含哪些依赖项。这也可以帮助 Copilot 了解您希望它在制作建议时使用哪些框架、库及其版本。

在以下 TypeScript 示例中，我们希望记录 `add` 方法的输出。当我们没有任何包含时，Copilot 建议使用 `console.log`：
![Copilot 内联建议在文件中没有导入时提出使用 Console.log。](images/prompt-crafting/copilot-suggestion-console-log.png)

另一方面，当你添加对 `Log4js` 的引用时，Copilot 会建议使用该框架来记录输出：

![Copilot 内联建议使用导入的日志框架进行日志记录。](images/prompt-crafting/copilot-suggestion-framework-log.png)

#### 有意义的函数名称

就像一个名为 `fetchData()` 的方法对同事（或几个月后的你）意义不大一样，`fetchData()` 也无法帮助 Copilot。使用有意义的函数名称可以帮助 Copilot 提供符合你需求的函数体。

<!-- 有意义的函数/方法名称示例。 -->

#### 具体且范围明确的函数注释

函数名称只能在不变得过长的情况下提供有限的描述。函数注释可以帮助填补 Copilot 可能需要了解的细节。

<!-- 有意义的函数/方法注释示例 -->

#### 使用样本代码启动 Copilot

一种让 Copilot 进入正确状态的技巧是，将接近你所需的样本代码复制并粘贴到你的开放编辑器中。提供一个小示例可以帮助 Copilot 生成符合你所需语言和任务的建议。一旦 Copilot 开始提供你想要并将实际使用的代码，你可以从文件中删除样本代码。这在 Copilot 默认提供旧代码建议时，帮助其跳转到较新的库版本尤其有用。

### 保持一致性并保持高质量标准

Copilot 将会依附于你的代码来生成遵循现有模式的建议，因此“垃圾进，垃圾出”的谚语适用。

始终保持高质量标准需要纪律。特别是当你快速且随意地编写代码以使其工作时，你可能希望在“黑客”模式下禁用 Copilot 补全。你可以通过 Copilot 状态菜单临时禁用补全。通过选择 Copilot 状态栏项目来调出 Copilot 状态菜单下拉列表。

![悬停在 Copilot 状态栏项目上显示“显示 Copilot 状态菜单”](images/prompt-crafting/show-copilot-status-menu.png)

从下拉列表中，你可以完全禁用补全，或者仅为活动文件类型禁用，例如 Markdown 文件。

![Copilot 状态菜单下拉列表中选择了“禁用补全”](images/prompt-crafting/disable-completions.png)

<!-- ### 具体化

将任务分解为单独的具体任务

具体说明输入、输出、范围、API、框架。

### 验证建议

Copilot 不是编译器或语言服务

你可能已经在使用的工具可以帮助。

#### 语言服务警告

#### 代码检查工具 -->

## 充分利用 Copilot 聊天

你还可以通过安装 [GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat) 扩展，使用[聊天界面](/i18n/zh-cn/docs/copilot/overview.md#Answer-coding-questions)从 Copilot 获取帮助。

当你使用聊天与 GitHub Copilot 互动时，有几件事你可以做来优化你的体验。

### 使用聊天参与者和斜杠命令
聊天参与者旨在收集关于代码库或特定领域或技术的额外上下文。通过使用适当的参与者，Copilot Chat 可以找到并提供更好的信息发送到 Copilot 后端。例如，如果您想询问关于您打开的项目的问题，请使用 `@workspace`，或者使用 `@vscode` 了解更多关于 VS Code 功能和 API 的信息。

![询问 @vscode 参与者如何更改 VS Code 颜色](images/prompt-crafting/agent-example.png)

斜杠命令帮助 Copilot Chat 理解您提问时的**意图**。您是在学习代码库（`/explain`），需要帮助解决问题（`/fix`），还是在创建测试用例（`/tests`）？通过让 Copilot Chat 知道您在尝试做什么，它可以调整其回复以适应您的任务，并提供有用的命令、设置和代码片段。

![内联聊天斜杠命令列表](images/prompt-crafting/inline-chat-slash-commands.png)

您可以用自然语言查询写出您的项目范围或当前任务，但使用聊天参与者和斜杠命令更为简洁和明确。

了解更多关于[聊天参与者](/i18n/zh-cn/docs/copilot/copilot-chat.md#chat-participants)和[斜杠命令](/i18n/zh-cn/docs/copilot/copilot-chat.md#slash-commands)的信息，请参阅 Copilot Chat。

### 使用聊天变量提供上下文

聊天参与者，如 `@workspace` 或 `@vscode`，可以提供提供特定领域上下文的聊天变量。您可以通过使用 `#` 符号在聊天提示中引用聊天变量。通过使用聊天变量，您可以更具体地包含在聊天提示中的上下文。

例如，`#file` 变量允许您在聊天提示中引用工作区中的特定文件。这有助于通过提供您正在处理的文件的上下文，使 Copilot Chat 的回答更相关于您的代码。您可以问类似“您能建议改进 #file:package.json 吗？”或“如何在 #file:devcontainer.json 中添加扩展？”的问题。通过使用 `#file` 变量，您可以获得更有针对性和准确的回答。

您还可以通过在聊天视图中使用**附加上下文**按钮来为您的聊天消息添加上下文。然后，您可以从快速选择中选择特定类型的上下文，例如当前选择、工作区中的一个或多个文件，或源代码中的一个或多个符号。

![VS Code Copilot 聊天视图的屏幕截图，显示附加上下文按钮和上下文快速选择。](./images/prompt-crafting/copilot-chat-view-attach-context.png)

了解更多关于[使用上下文变量与 Copilot Chat](/i18n/zh-cn/docs/copilot/copilot-chat.md#add-context-to-your-chat-prompt)的信息。

### 具体且保持简单

当您要求 Copilot 做某事时，请在您的请求中具体，并将大型任务分解为单独的、较小的任务。例如，不要要求 Copilot 创建一个使用 TypeScript 和 Pug 的 Express 应用，并且有一个从 MongoDB 数据库检索数据的产品页面。相反，首先要求 Copilot 创建使用 TypeScript 和 Pug 的 Express 应用。接下来，要求添加一个产品页面，最后要求从数据库中检索客户数据。
当您要求 Copilot 执行特定任务时，请明确指出您希望使用的输入、输出、API 或框架。您的提示越具体，结果就越好。例如，不要说“从数据库读取产品数据”，而是说“按类别读取所有产品，以 JSON 格式返回数据，并使用 Mongoose 库”。

### 迭代您的解决方案

在向 Copilot Chat 寻求帮助时，您不必满足于第一个响应。您可以迭代并提示 Copilot 改进解决方案。Copilot 既有生成代码的上下文，也有您当前的对话。

这是一个使用内联聊天创建计算 Fibonacci 数的函数的示例：

![Copilot 计算 Fibonacci 数的函数的第一次响应](images/prompt-crafting/fibonacci-first.png)

也许您更喜欢不使用递归的解决方案：

![要求 Copilot 不使用递归和新结果](images/prompt-crafting/fibonacci-second.png)

您甚至可以要求 Copilot 遵循编码惯例或改进变量名称：

![要求 Copilot 使用更好的变量名称和新结果](images/prompt-crafting/fibonacci-third.png)

即使您已经接受了一个结果，您也可以随时要求 Copilot 稍后对代码进行迭代。

## 关于 Copilot 提示的更多资源

如果您想了解更多关于高效使用 GitHub Copilot 的信息，您可以查看以下视频和博客文章：

* [GitHub Copilot 的有效提示](https://www.youtube.com/watch?v=ImWfIDTxn7E)
* [获取 GitHub Copilot 最大效益的实用技术](https://www.youtube.com/watch?v=CwAzIpc4AnA)
* [在 VS Code 中提示 GitHub Copilot 的最佳实践](https://www.linkedin.com/pulse/best-practices-prompting-github-copilot-vs-code-pamela-fox)
* [如何使用 GitHub Copilot：提示、技巧和用例](https://github.blog/2023-06-20-how-to-write-better-prompts-for-github-copilot/)