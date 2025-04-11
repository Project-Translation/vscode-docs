---
Order: 13
Area: copilot
TOCTitle: Copilot 可扩展性
ContentId: e375ec2a-43d3-4670-96e5-fd25a6aed272
PageTitle: GitHub Copilot 可扩展性概述
DateApproved: 03/05/2025
MetaDescription: 概述如何通过使用聊天 API 或语言模型 API 在 Visual Studio Code 扩展中扩展 GitHub Copilot。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中扩展 GitHub Copilot

使用 GitHub Copilot 的可扩展性来扩展 Visual Studio Code 中 Copilot Chat 的功能，或向您的 VS Code 扩展添加人工智能驱动的功能。要在 VS Code 中扩展 Copilot，您需要构建一个 VS Code 扩展，并使用扩展 API 与 GitHub Copilot 进行交互。

根据您的用例，您有以下选项来在您的 VS Code 扩展中使用 Copilot：

- **VS Code 聊天扩展**：使用聊天 API 创建一个聊天参与者，为用户提供自然语言界面，并通过 VS Code 中的聊天视图提供特定领域的帮助。您可以选择使用 Copilot 大型语言模型 (LLM) 来解释用户提示并生成响应。

- **使用 Copilot 的 LLM**：使用语言模型 API 和 VS Code 扩展 API 在您的扩展中构建人工智能驱动的功能，并增强特定于编辑器的交互。

或者，您还可以构建一个 **Copilot 扩展**，作为具有额外功能的 GitHub 应用程序实现。Copilot 扩展可以在所有支持的 IDE 和 GitHub 上工作，但无法访问特定于 VS Code 的功能。请在 GitHub 文档中获取更多关于 [Copilot 扩展](https://docs.github.com/en/copilot/building-copilot-extensions/about-building-copilot-extensions) 的信息。

## 使用案例

您可以使用 Copilot 的功能通过在您的扩展中集成人工智能驱动的功能来增强 VS Code 中的开发体验。以下是您如何在您的 VS Code 扩展中使用 Copilot 的一些示例：

- **文档查询**：一个聊天参与者可以允许 Copilot Chat 使用检索增强生成 (RAG) 来查询第三方文档服务，并基于检索到的信息生成响应。

- **人工智能辅助编码**：使用 Copilot LLM 为编辑器提供注释以提供编码建议。

- **人工智能驱动的审查**：使用 Copilot LLM 审查您的代码以发现安全漏洞或性能改进。

- **数据检索**：一个聊天参与者可以允许 Copilot Chat 查询数据库或第三方数据服务以检索关于特定主题的信息。

- **企业编码助手**：一个基于您企业数据的聊天参与者，并且了解您公司遵循的特定编码指南。

- **增强扩展**：使用语言模型 API 为您现有的 VS Code 扩展添加人工智能驱动的功能。

这些是在 Visual Studio Marketplace 中为 VS Code 的聊天视图贡献聊天参与者的扩展的一些示例。

<div class="marketplace-extensions-chat"></div>

请访问 [Marketplace](https://marketplace.visualstudio.com/search?term=tag%3Achat-participant&target=VSCode&category=All%20categories&sortBy=Relevance) 或使用集成的 [扩展视图](/i18n/zh-cn/docs/configure/extensions/extension-marketplace.md)，并使用 `chat-participant` 标签搜索更多扩展。

## 在 VS Code 中开始使用 Copilot 可扩展性

要开始在您的 VS Code 扩展中扩展 Copilot，请探索以下资源：
- [**教程：AI驱动的代码注释**](/api/extension-guides/language-model-tutorial.md)：逐步指南，帮助您实现一个VS Code扩展，使用语言模型API在编辑器中生成代码注释，以改进您的代码。

- [**教程：代码导师聊天参与者**](/api/extension-guides/chat-tutorial.md)：逐步指南，帮助您实现一个代码导师聊天参与者，使用户能够在VS Code的聊天视图中使用自然语言请求解释技术主题。

- [**聊天参与者示例代码**](https://github.com/microsoft/vscode-extension-samples/tree/main/chat-sample)：用于开始构建使用聊天API和语言模型API的VS Code聊天扩展的示例代码。

- **扩展指南**：了解如何使用[聊天API](/api/extension-guides/chat.md)和[语言模型API](/api/extension-guides/language-model.md)来扩展您的VS Code扩展中的Copilot。

## 相关内容

- [开始使用Copilot扩展](https://github.com/features/copilot/extensions)
- [使用GitHub Copilot增强VS Code扩展](https://www.youtube.com/watch?v=YI7kjWzIiTM) Microsoft Build会议