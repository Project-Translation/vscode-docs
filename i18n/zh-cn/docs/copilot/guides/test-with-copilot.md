---
ContentId: 9f84b21e-5b76-4c3a-a5dd-2021ab343f1f
DateApproved: 2025/03/05
MetaDescription: 了解如何在 Visual Studio Code 中使用 GitHub Copilot 编写、调试和修复测试。
---

# 使用 GitHub Copilot 进行测试

编写和维护测试是软件开发中一个至关重要但往往耗时的部分。GitHub Copilot 通过帮助您在 Visual Studio Code 中更高效地编写、调试和修复测试来简化这一过程。本文将向您展示如何利用 Copilot 的测试功能来改进您的测试工作流程，并提高项目中的测试覆盖率。

Copilot 可以帮助完成以下测试任务：

* **设置测试框架**：获取帮助配置适合您项目和语言的测试框架和 VS Code 扩展。
* **生成测试代码**：创建覆盖您应用程序代码的单元测试、集成测试和端到端测试。
* **处理边缘情况**：生成覆盖边缘情况和错误条件的全面测试套件。
* **修复失败的测试**：接收修复测试失败的建议。
* **保持一致性**：个性化 Copilot 以生成遵循您项目编码实践的测试。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup) 来免费使用 Copilot，并获得每月的完成和聊天交互限制。

## 设置您的测试框架

为了加速您的测试工作流程，Copilot 可以帮助设置您的项目的测试框架和 VS Code 扩展。Copilot 会根据您的项目类型建议合适的测试框架。

1. 打开聊天视图 (`kb(workbench.action.chat.open)`)。
1. 在聊天输入字段中输入 `/setupTests` 命令。
1. 按照 Copilot 的指导配置您的项目。

## 使用 Copilot 编写测试

Copilot 可以通过生成覆盖您代码库的测试代码来帮助您为应用程序代码编写测试。这包括单元测试、端到端测试以及针对边缘情况的测试。

### 使用聊天提示

1. 打开您的应用程序代码文件。

1. 打开以下视图之一：
    * Copilot 编辑 (`kb(workbench.action.chat.openEditSession)`)
    * 聊天视图 (`kb(workbench.action.chat.open)`)
    * 内联聊天 (`kb(inlineChat.start)`)

1. 输入如下提示：
    * "为这段代码生成测试"
    * "编写包括边缘情况的单元测试"
    * "为这个模块创建集成测试"

在 GitHub 文档中获取更多关于[使用 GitHub Copilot 编写测试](https://docs.github.com/en/copilot/using-github-copilot/guides-on-using-github-copilot/writing-tests-with-github-copilot)的指导。

### 使用编辑器智能操作

要在不编写提示的情况下为您的应用程序代码生成测试，您可以使用编辑器智能操作。

1. 打开您的应用程序代码文件。
1. 可选地，选择您要测试的代码。
1. 右键点击并选择 **Copilot** > **生成测试**。

    Copilot 会在现有测试文件中生成测试代码，或者如果不存在测试文件，则创建一个新的测试文件。

1. 可选地，通过在内联聊天提示中提供额外上下文来完善生成的测试。

## 修复失败的测试

Copilot 与 VS Code 中的测试资源管理器集成，可以帮助修复失败的测试。
1. 在测试资源管理器中，将鼠标悬停在失败的测试上
1. 选择**修复测试失败**按钮（闪光图标）
1. 审查并应用 Copilot 的建议修复

或者，您可以：

1. 打开聊天视图
1. 输入 `/fixTestFailure` 命令
1. 按照 Copilot 的建议修复测试

> [!TIP]
> [Copilot Edits 代理模式（预览版）](/i18n/zh-cn/docs/copilot/copilot-edits.md#use-agent-mode-preview) 在运行测试时监控测试输出，并自动尝试修复和重新运行失败的测试。

## 个性化测试生成

如果您的组织有特定的测试要求，您可以自定义 Copilot 生成测试的方式，以确保它们符合您的标准。您可以通过提供自定义指令来个性化 Copilot 生成测试的方式。例如：

* 指定首选的测试框架
* 定义测试的命名约定
* 设置代码结构偏好
* 请求特定的测试模式或方法

获取更多关于[个性化 Copilot 生成测试](/i18n/zh-cn/docs/copilot/copilot-customization.md)的信息。

## 更好地生成测试的提示

在使用 Copilot 生成测试时，要获得最佳结果，请遵循以下提示：

* 在提示中提供关于您首选的测试框架的上下文
* 指定您是否想要特定类型的测试（单元测试、集成测试、端到端测试）
* 请求特定的测试用例或边缘情况
* 请求遵循您项目编码标准的测试

## 下一步

* 了解更多关于[VS Code 中的 Copilot](/i18n/zh-cn/docs/copilot/overview.md)。
* 探索[VS Code 中的通用测试功能](/i18n/zh-cn/docs/debugtest/testing.md)。
* 查看用于[生成单元测试](https://docs.github.com/en/copilot/example-prompts-for-github-copilot-chat/testing-code/generate-unit-tests)的示例提示