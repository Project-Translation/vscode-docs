---
Order: 10
Area: copilot
TOCTitle: 工作区上下文
ContentId: c77dcce9-4ba9-40ac-8ae5-2df855088090
PageTitle: 使用 @workspace 上下文引用进行聊天
DateApproved: 2025/03/05
MetaDescription: 如何使用 Copilot 的 @workspace 聊天功能针对整个代码库提问。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 让 Copilot Chat 成为工作区的专家

在 Copilot Chat 中引用 `@workspace`，您可以针对整个代码库提问。根据问题，Copilot 智能地检索相关文件和符号，并在回答中以链接和代码示例的形式引用它们。基于 `@workspace` 引用，Copilot Chat 成为以下任务的领域专家：

- 在您的代码库中查找现有代码：
  - `"@workspace 数据库连接字符串在哪里配置？"` - 解释数据库连接在哪里以及如何配置
  - `"@workspace 如何验证日期？"` - 在代码库中查找现有的日期验证帮助程序
  - `"@workspace 测试在哪里定义？"` - 提供测试套件、案例以及相关引用和配置的位置
- 制定复杂代码编辑计划：
  - `"@workspace 如何为按钮添加丰富的工具提示？"` - 提供使用现有工具提示组件与按钮元素的计划
  - `"@workspace 将日期验证添加到 #selection"` - 计划如何将现有的日期验证应用到选定的代码
  - `"@workspace 为忘记密码表单添加新的 API 路由"` - 概述在哪里添加新路由以及如何将其连接到现有代码
- 解释代码库中的高级概念：
  - `"@workspace 如何实现身份验证？"` - 概述身份验证流程并引用相关代码
  - `"@workspace 哪些 API 路由依赖于这个服务？"` - 列出在选定代码中使用该服务的路由
  - `"如何构建这个 #codebase？"` - 根据文档、脚本和配置列出构建项目的步骤

## `@workspace` 使用哪些来源作为上下文？

为了回答您的问题，`@workspace` 会搜索开发人员在 VS Code 中导航代码库时会使用到的相同来源：

- 工作区中所有[可索引文件](#工作区索引中包含哪些内容)，除了被 `.gitignore` 文件忽略的文件
- 带有嵌套文件夹和文件名的目录结构
- 如果工作区是 GitHub 存储库且[被代码搜索索引](https://docs.github.com/en/enterprise-cloud@latest/copilot/github-copilot-enterprise/copilot-chat-in-github/using-github-copilot-chat-in-githubcom#asking-a-question-about-a-specific-repository-file-or-symbol)，则使用 GitHub 的代码搜索索引
- 工作区中的符号和定义
- 当前选中的文本或活动编辑器中可见的文本

> [!NOTE]
> 如果您打开了一个文件或在被忽略的文件中选中了文本，则会绕过 `.gitignore`。

## `@workspace` 如何找到最相关的上下文

您的整个 VS Code 工作区可能太大，无法全部传递给 GitHub Copilot 以响应您的聊天提示。相反，`@workspace` 从不同的上下文来源中提取最相关的信息，以支持 Copilot 的回答。

首先，`@workspace` 确定回答您的问题所需的信息，包括对话历史、工作区结构和当前选定的代码。
接下来，它使用不同的方法收集上下文，例如通过本地搜索或使用 [GitHub 的代码搜索](https://github.blog/2023-02-06-the-technology-behind-githubs-new-code-search)来查找相关代码片段，并使用 VS Code 的语言 IntelliSense 来添加函数签名、参数等详细信息。

最后，GitHub Copilot 使用这些上下文来回答您的问题。如果上下文过大，只会使用最相关的部分。响应中会标注文件、文件范围和符号的引用。这使您可以从聊天响应中直接链接到代码库中相应的信息。提供给 Copilot 的代码片段会在响应中列为参考。

## `@workspace` 斜杠命令的上下文

`@workspace` 提供了几个 *斜杠命令*，作为常用任务的简写，节省您的时间和输入工作。每个命令定义了自己的优化上下文，通常无需额外的提示或聊天变量。这里是可用的斜杠命令及其上下文：

| 命令        | 上下文 |
| -------------- | ------- |
| `/explain`     | <ul><li>从活动编辑器中的文本选择开始（`#selection`）。为了优化 Copilot 聊天响应，请确保扩展文本选择以包括任何相关信息，以帮助 Copilot 提供有用的响应。</li><li>查找所引用符号（如函数和类）的实现，从而提供更准确和有用的解释。</li></ul> |
| `/tests`       | <ul><li>活动编辑器中的当前文本选择。如果没有选择文本，则使用当前活动文件的内容。</li><li>相关的现有测试文件，以了解现有测试和最佳实践。</li></ul> |
| `/fix`         | <ul><li>活动编辑器中的当前文本选择。如果没有选择文本，则使用编辑器中当前可见的文本。</li><li>错误和所引用符号，以了解需要修复的内容和方法。</li></ul> |
| `/new`         | <ul><li>仅使用聊天提示作为上下文。</li></ul> |
| `/newNotebook` | <ul><li>仅使用聊天提示作为上下文。</li></ul> |

您可以通过在聊天提示中使用聊天变量（如 `#editor`、`#selection` 或 `#file`）来明确扩展上下文。例如，要根据另一个文件中的模式修复当前文件中的错误，请使用此聊天提示：`@workspace /fix linting error in the style of #file:form.ts`。

## 管理工作区索引

Copilot 使用索引来快速准确地在您的代码库中搜索相关代码片段。该索引可以由 GitHub 维护，也可以存储在您的机器上。本节介绍 Copilot 可以使用的不同类型的索引（[远程](#remote-index)、[本地](#local-index) 和 [基本](#basic-index)），并解释何时使用每种索引以及如何在它们之间切换。

要查看 Copilot 当前使用的索引类型，请通过在状态栏中选择 `{}` 图标来检查语言状态 UI。Copilot 工作区索引条目显示索引类型以及与此索引相关的任何相关信息，例如正在重新索引的文件数量。

![在语言状态 UI 中查看 Copilot 索引的状态](images/copilot-chat/workspace-index-status.png)

### 远程索引
对于 GitHub 存储库，Copilot 可以使用 [GitHub 代码搜索](https://docs.github.com/en/enterprise-cloud@latest/copilot/using-github-copilot/asking-github-copilot-questions-in-github#asking-exploratory-questions-about-a-repository) 来构建您代码库的远程索引。这允许 Copilot 非常快速地搜索您的整个代码库，即使代码库非常大。

要使用远程索引：

- 在 VS Code 中使用您的 GitHub 账户登录。

- 打开一个带有 GitHub git 远程的项目。确保您也已将代码推送到 GitHub。

    如果 GitHub 拥有您代码的相对较新的版本，远程索引的效果会更好，因此请定期将代码推送到 GitHub。

- 通过运行 **构建远程工作区索引** 命令或在工作区索引状态 UI 中选择构建索引按钮来构建远程索引。

    构建远程索引可能需要一些时间，特别是对于大型代码库。您可以在工作区索引状态 UI 中监控远程索引的状态。

    一旦构建了远程索引，GitHub 会在您推送代码更改时自动保持其更新。您只需针对每个存储库运行一次 **构建远程工作区索引** 命令。

### 本地索引

在无法使用 [远程索引](#remote-index) 的情况下，Copilot 可以改用存储在您本地机器上的高级语义索引。此索引也可以提供快速、高质量的搜索结果。然而，它目前仅限于 2500 个可索引文件。与远程索引不同，本地索引必须针对每个用户在每台机器上构建一次。使用远程索引时，给定存储库的所有用户都可以使用同一个索引。

如果您的项目有少于 750 个可索引文件，Copilot 会自动构建高级本地索引。对于拥有 750 到 2500 个文件的项目，您可以运行 **构建本地工作区索引** 命令来开始索引。此命令只需运行一次。

构建初始本地索引或在许多文件发生更改时（例如切换 git 分支）更新索引可能需要一些时间。您可以在工作区索引状态 UI 中监控当前本地索引状态。

### 基本索引

如果您的项目没有 [远程索引](#remote-index) 并且还有超过 2500 个 [可索引文件](#what-content-is-included-in-the-workspace-index)，Copilot 将回退到使用基本索引来搜索您的代码库。此索引使用更简单的算法来搜索您的代码库，并已针对本地处理大型代码库进行了优化。

基本索引对于许多问题应该运作良好。然而，如果您发现 Copilot 在回答关于您代码库的问题时遇到困难，请尝试升级到 [远程索引](#remote-index)。

### 工作区索引中包含的内容

Copilot 索引属于您当前项目的相关文本文件。这不仅限于特定的文件类型或编程语言，但是 Copilot 会自动跳过一些通常与 `@workspace` 问题无关的常见文件类型，例如 `.tmp` 或 `.out` 文件。Copilot 还排除任何使用 `setting(files.exclude)` 设置或属于 `.gitignore` 文件的文件。

Copilot 目前也不索引二进制文件，例如图像或 PDF。

## 使用 `@workspace` 的提示
您提问的方式会显著影响 `@workspace` 提供的参考资料的质量和回答的准确性。为了优化结果，请考虑以下建议：

- 在提问时要具体详细，避免使用模糊或含糊的术语，如“这是做什么的”（其中“这个”可能被解释为上一个回答、当前文件或整个项目等）。
- 在提示中加入可能出现在您的代码或其文档中的术语和概念。
- 查看回答中的*已使用参考资料*，确保文件相关性。如果有必要，请调整您的问题。
- 通过选择代码或提及聊天变量（如 `#editor`、`#selection` 或 `#file`）明确包含相关上下文。
- 回答可以从多个参考资料中获取，例如“查找没有 catch 块的异常”或“提供 handleError 调用的示例”。然而，不要期望对整个代码库进行全面的代码分析，如“这个函数被调用了多少次？”或“修复这个项目中的所有错误”。
- 暂时避免假设代码之外的信息，如“谁贡献了这个文件？”或“总结这个文件夹的审查评论”。

## 相关资源

- 开始使用 [Copilot 聊天教程](/i18n/zh-cn/docs/copilot/getting-started-chat.md)
- [使用聊天参与者 API 构建聊天扩展](/api/extension-guides/chat.md)