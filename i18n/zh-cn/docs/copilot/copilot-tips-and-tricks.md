---
ContentId: 58ea6755-9bfa-42c2-a4c8-ff0510f9c031
DateApproved: 2025/02/06
MetaDescription: 在 VS Code 中使用 GitHub Copilot 优化开发体验的技巧和窍门。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中使用 Copilot 的技巧和窍门

本文提供了在 Visual Studio Code 中使用 GitHub Copilot 优化开发体验的技巧和窍门。

## 在 VS Code 中使用 Copilot 的检查列表

使用以下检查列表充分利用 Copilot：

1. [选择合适的工具](#选择合适的-copilot-工具)。_使用适合编辑、提问或保持编写代码流程的工具。_

1. [个性化 Copilot](#使用自定义指令个性化-copilot)。_使用自定义指令获取符合您的风格和编码实践的代码建议。_

1. [编写有效的提示](#提示工程) 并提供[上下文](#提供正确的上下文)。_获取最相关的响应。_

1. [索引您的工作区](#工作区索引)。_接收关于您代码库的准确响应。_

1. [选择您的 AI 模型](#选择您的-ai-模型)。_在快速编码和规划/推理之间选择模型。_

1. [重用提示](#可重用提示)。_通过保存和在团队中重用特定任务的提示节省时间。_

## 选择合适的 Copilot 工具

根据您的任务，您可以选择不同的 Copilot 工具。

| 工具 | 使用场景 |
|------|----------|
| [代码补全](/i18n/zh-cn/docs/copilot/ai-powered-suggestions.md) | 在保持编写流程的同时简化编码。<br/>在编辑器中编写时接收代码片段、变量名称和函数的内联建议。 |
| [聊天](/i18n/zh-cn/docs/copilot/copilot-chat.md) | 进行持续的聊天对话，用于头脑风暴设计理念或获取代码建议，可选择调用特定领域的聊天参与者。<br/>选择将特定代码建议应用到您的代码库中。 |
| [编辑](/i18n/zh-cn/docs/copilot/copilot-edits.md) | 使用自然语言开始编码编辑会话。<br/>在您的工作区中自动应用跨多个文件的大型代码更改。 |
| [代理模式](/i18n/zh-cn/docs/copilot/copilot-edits.md#use-agent-mode-preview) | 通过启动代理式编码流程实现高层次需求。<br/>Copilot 自主调用多个工具来规划和实施所需的代码更改和任务。 |

## 使用自定义指令个性化 Copilot

当 Copilot 生成代码或回答问题时，它会尝试匹配您的编码实践和偏好，例如您使用的库或您如何命名变量。然而，它可能并不总是有足够的上下文来有效地做到这一点。例如，如果您使用特定版本的框架，您需要在提示中提供额外的上下文。

为了增强 Copilot 的响应，您可以使用_自定义指令_为其提供有关您的团队工作流程、工具或项目具体信息的上下文细节。Copilot 然后将这些自定义指令与每次请求结合使用。

要为您的工作区启用自定义指令：

1. 在工作区根目录下创建一个 `.github/copilot-instructions.md` 文件
1. 将您的指令以 Markdown 格式添加到文件中。例如：

    ```markdown
    # Copilot 的自定义指令
## 项目背景
此项目是一个使用 React 和 Node.js 构建的 Web 应用程序。

## 缩进
我们使用制表符，而非空格。

## 编码风格
变量名使用驼峰命名法，并优先使用箭头函数而非传统函数表达式。

## 测试
我们使用 Jest 进行单元测试，使用 Playwright 进行端到端测试。

获取有关[在 VS Code 中为 Copilot 使用自定义指令](/i18n/zh-cn/docs/copilot/copilot-customization.md)的更多详细信息。

## 提示工程

通过使用有效的提示，您可以提高 Copilot 响应的质量。一个精心设计的提示可以帮助 Copilot 更好地理解您的需求，并生成更相关的代码建议。

* 从一般开始，然后具体化。

    ```text
    生成一个计算器类。
    添加加法、减法、乘法、除法和阶乘的方法。
    不要使用任何外部库，也不要使用递归。
    ```

* 提供您想要的示例。

    ```text
    生成一个函数，该函数接受一个字符串并返回其中的元音数量。
    示例：
    findVowels("hello") 返回 2
    findVowels("sky") 返回 0
    ```

* 将复杂任务分解为更简单的任务。

    不要要求 Copilot 生成一个餐饮计划应用程序，而是将其分解为更小的任务：
    * 生成一个函数，该函数接受一个成分列表并返回一个食谱列表。
    * 生成一个函数，该函数接受一个食谱列表并返回一个购物清单。
    * 生成一个函数，该函数接受一个食谱列表并返回一周的餐饮计划。

* 提供[正确的上下文](#提供正确的上下文)，例如代码选择、文件、终端输出等。

    例如，使用 `#codebase` 变量来指代整个代码库：

    ```text
    在 #codebase 中哪里使用了数据库连接字符串？
    ```

* 迭代您的提示。

    提供后续提示以细化或修改响应。例如：

    * "编写一个计算数字阶乘的函数。"
    * "不要使用递归，并通过使用缓存进行优化。"
    * "使用有意义的变量名。"

* 保持聊天历史相关。

    Copilot 使用对话历史来提供上下文。如果过去的问题和响应不相关，请从历史中删除它们。或者，如果您想更改上下文，请开始一个新会话。

获取有关[提示工程](/i18n/zh-cn/docs/copilot/prompt-crafting.md)的更多详细信息。

在 GitHub Copilot 文档中查找使用 Copilot 的[提示示例](https://docs.github.com/en/copilot/copilot-chat-cookbook)。

## 提供正确的上下文

通过相关上下文丰富您的提示，以从 Copilot 获得更准确和相关的响应。

* 使用 `#codebase` 变量让 Copilot 自动找到正确的文件。
* 在提示中使用 `#file` 或 `#sym` 聊天变量来引用文件或符号。
* 将文件、文件夹或编辑器选项卡拖放到聊天提示上。
* 将问题、测试失败或终端输出添加到您的聊天提示中，以提供特定场景的上下文。
* 将图像或屏幕截图添加到您的提示中，让 Copilot 分析图像。

当您使用[代理模式](/i18n/zh-cn/docs/copilot/copilot-edits.md#use-agent-mode-preview)时，Copilot 会自动为您查找相关文件和上下文。

获取有关[向聊天提示添加上下文](/i18n/zh-cn/docs/copilot/copilot-chat-context.md)的更多详细信息。
## 可重用提示

可重用提示使您能够将特定任务的提示及其上下文和说明保存到文件中。然后，您可以在聊天中附加并重用该提示。如果您将提示存储在工作区中，您还可以与团队共享。

创建可重用提示的步骤：

1. 使用命令面板中的**创建提示**命令创建提示文件。

    此命令会在工作区根目录的`.github/prompts`文件夹中创建一个`.prompt.md`文件。

1. 使用Markdown格式描述您的提示和相关上下文。

    例如，使用此提示生成一个新的React表单组件。

    ```markdown
    您的目标是生成一个新的React表单组件。

    如果未提供，请询问表单名称和字段。

    表单的要求：
    * 使用表单设计系统组件：[design-system/Form.md](../i18n/zh-cn/docs/design-system/Form.md)
    * 使用`react-hook-form`进行表单状态管理：
    * 始终为您的表单数据定义TypeScript类型
    * 优先使用使用register的*非受控*组件
    * 使用`defaultValues`防止不必要的重新渲染
    * 使用`yup`进行验证：
    * 在单独的文件中创建可重用的验证模式
    * 使用TypeScript类型确保类型安全
    * 自定义用户友好的验证规则
    ```

1. 在聊天中添加提示作为上下文。

开始使用[可重用提示](/i18n/zh-cn/docs/copilot/copilot-customization.md#reusable-prompt-files-experimental)。

## 选择您的AI模型

Copilot提供不同的AI模型供您选择。有些模型针对快速编码任务进行了优化，而其他模型则更适合于较慢的规划和推理任务。

| 模型类型 | 模型 |
|-----------|--------|
| 快速编码 | <ul><li>GPT-4o</li><li>Claude Sonnet 3.5</li><li>Claude Sonnet 3.7</li><li>Gemini 2.0 Flash</li></ul> |
| 推理/规划 | <ul><li>Claude Sonnet 3.7 Thinking</li><li>o1</li><li>o3-mini</li></ul> |

通过聊天输入字段中的模型选择器选择最适合您需求的模型。

了解更多关于[Copilot Chat的AI模型](https://docs.github.com/en/copilot/using-github-copilot/ai-models/changing-the-ai-model-for-copilot-chat)的信息，请参阅GitHub Copilot文档。

## 工作区索引

Copilot使用索引来快速准确地搜索您的代码库以查找相关代码片段。此索引可以由GitHub维护，也可以存储在您的机器上。

对于GitHub存储库，您可以使用基于[GitHub代码搜索](https://docs.github.com/en/enterprise-cloud@latest/copilot/using-github-copilot/asking-github-copilot-questions-in-github#asking-exploratory-questions-about-a-repository)的远程工作区索引。这允许Copilot即使在代码库非常大时也能非常快速地搜索您的整个代码库。

获取更多关于[工作区索引](/i18n/zh-cn/docs/copilot/workspace-context.md#managing-the-workspace-index)的详细信息。

## 相关资源

* [为Copilot Chat进行提示工程](/i18n/zh-cn/docs/copilot/prompt-crafting.md)
* [使用GitHub Copilot的最佳实践](https://docs.github.com/en/copilot/using-github-copilot/best-practices-for-using-github-copilot)在GitHub Copilot文档中
* [在VS Code中个性化Copilot](/i18n/zh-cn/docs/copilot/copilot-customization.md)