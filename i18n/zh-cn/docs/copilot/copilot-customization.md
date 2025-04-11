---
Order: 11
Area: copilot
TOCTitle: 自定义 Copilot
ContentId: 16c73175-a606-4aab-8ae5-a507fe8947eb
PageTitle: 在 VS Code 中自定义 GitHub Copilot
DateApproved: 03/05/2025
MetaDescription: 了解如何通过定义一组指令来自定义 GitHub Copilot 为您的项目生成代码或测试的方式。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中为 GitHub Copilot 定义自定义指令

您可以通过提供有关您的团队工作流程、工具或项目具体信息的上下文来增强 Copilot 的聊天响应。您无需在每次聊天查询中手动包含此上下文，可以创建一个_自定义指令_文件，自动将此信息纳入每次聊天请求中。

Copilot 将这些指令应用于聊天视图、快速聊天或内联聊天中的聊天提示。这些指令不会在聊天中显示，但由 VS Code 传递给 Copilot。

您可以为特定目的指定自定义指令：

* **代码生成指令** - 提供生成代码的特定上下文。例如，您可以指定私有变量应始终以 underscores 开头，或者单例应以特定方式实现。您可以在设置中或在工作区的 Markdown 文件中指定代码生成指令。

* **测试生成指令** - 提供生成测试的特定上下文。例如，您可以指定所有生成的测试应使用特定的测试框架。您可以在设置中或在工作区的 Markdown 文件中指定测试生成指令。

* **代码审查指令** - 提供审查当前编辑器选择的特定上下文。例如，您可以指定审查者应查找代码中的特定类型的错误。您可以在设置中或在工作区的 Markdown 文件中指定审查选择指令。

* **提交消息生成指令** - 提供生成提交消息的特定上下文。您可以在设置中或在工作区的 Markdown 文件中指定提交消息生成指令。

* **拉取请求标题和描述生成指令** - 提供生成拉取请求标题和描述的特定上下文。您可以在设置中或在工作区的 Markdown 文件中指定拉取请求标题和描述生成指令。

自定义指令由自然语言指令组成，应是简短、自包含的语句，用于补充聊天问题添加上下文或相关信息。

## 定义代码生成自定义指令

Copilot 可以帮助您生成代码，例如作为重构的一部分，生成单元测试，或实现功能。您可能有特定的库希望在项目中使用，或者希望 Copilot 生成的代码遵循特定的编码风格。

> [!NOTE]
> Copilot 不适用于[代码补全](/i18n/zh-cn/docs/copilot/ai-powered-suggestions.md)的代码生成指令。
以下代码片段展示了如何在 `settings.json` 文件中定义一组指令。要直接在设置中定义指令，请配置 `text` 属性。要引用外部文件，请配置 `file` 属性。

```json
  "github.copilot.chat.codeGeneration.instructions": [
    {
      "text": "始终添加注释：'由 Copilot 生成'。"
    },
    {
      "text": "在 TypeScript 中始终对私有字段名称使用下划线。"
    },
    {
      "file": "code-style.md" // 从文件 `code-style.md` 导入指令
    }
  ],
```

`code-style.md` 文件内容示例：

```markdown
始终使用 React 函数组件。

始终添加注释。
```

### 使用 `.github/copilot-instructions.md` 文件

您还可以在工作区或存储库中使用 `.github/copilot-instructions.md` 文件存储自定义指令，并让 VS Code 自动识别此文件。

如果您在 `.github/copilot-instructions.md` 文件和设置中都定义了自定义指令，Copilot 会尝试结合来自这两个来源的指令。

> [!NOTE]
> Visual Studio 中的 GitHub Copilot 也会检测 `.github/copilot-instructions.md` 文件。如果您有一个在 VS Code 和 Visual Studio 中都使用的工作区，您可以使用同一个文件为这两个编辑器定义自定义指令。

1. 将 `setting(github.copilot.chat.codeGeneration.useInstructionFiles)` 设置为 `true`，以指示 VS Code 中的 Copilot 使用自定义指令文件。

1. 在工作区根目录创建一个 `.github/copilot-instructions.md` 文件。如有需要，先创建一个 `.github` 目录。

    > [!TIP]
    > 在 VS Code 的资源管理器视图中，您可以通过输入完整路径作为文件名，在一次操作中创建文件夹和文件。

1. 将自然语言指令添加到文件中。您可以使用 Markdown 格式。

    指令之间的空白会被忽略，因此指令可以写成一个段落，每条指令单独一行，或者用空行分隔以提高可读性。

## 定义测试生成自定义指令

您可以使用 Copilot 为您的代码生成测试，例如通过在聊天视图中使用 `@workspace /tests` 提示。您可以定义自定义指令，以帮助 Copilot 生成特定于您的项目和开发工作流程的测试。

要配置自定义测试生成指令，请使用 `setting(github.copilot.chat.testGeneration.instructions)` 设置。您可以在用户或工作区级别定义自定义指令。

以下代码片段展示了如何在 `settings.json` 文件中定义一组指令。要直接在设置中定义指令，请配置 `text` 属性。要引用外部文件，请配置 `file` 属性。

```json
  "github.copilot.chat.testGeneration.instructions": [
    {
      "text": "始终使用 vitest 测试 React 组件。"
    },
    {
      "text": "使用 Jest 测试 JavaScript 代码。"
    },
    {
      "file": "code-style.md" // 从文件 `code-style.md` 导入指令
    }
  ],
```

`code-style.md` 文件内容示例：

```markdown
始终添加代码注释。
始终使用 React 功能组件。

```

## 定义代码审查自定义指令

您可以使用 Copilot 来审查编辑器中选定的代码。您可以定义自定义指令，以帮助 Copilot 考虑与您的项目和开发流程相关的特定代码审查标准。

要配置自定义代码审查指令，请使用 `setting(github.copilot.chat.reviewSelection.instructions)` 设置。您可以在用户或工作区级别定义自定义指令。

## 定义提交消息生成自定义指令

在源代码控制视图中，您可以使用 Copilot 为待处理的代码更改生成提交消息。您可以定义自定义指令，以帮助 Copilot 生成考虑到您的项目和开发流程特定格式和结构的提交消息。

要配置自定义提交消息生成指令，请使用 `setting(github.copilot.chat.commitMessageGeneration.instructions)` 设置。您可以在用户或工作区级别定义自定义指令。

## 定义拉取请求标题和描述生成自定义指令

当您安装了 [GitHub Pull Requests](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) 扩展时，您可以使用 Copilot 为拉取请求生成标题和描述。您可以定义自定义指令，以帮助 Copilot 生成考虑到您的项目和开发流程特定格式和结构的标题和描述。

要配置自定义拉取请求标题和描述生成指令，请使用 `setting(github.copilot.chat.pullRequestDescriptionGeneration.instructions)` 设置。您可以在用户或工作区级别定义自定义指令。

## 定义自定义指令的提示

* 保持您的指令简短且自包含。每个指令应为一个简单的单一陈述。如果您需要提供多条信息，请使用多个指令。

* 不要在指令中引用外部资源，例如特定的编码标准。

* 通过将您的指令存储在外部文件中，方便与团队或跨项目共享自定义指令。您还可以对文件进行版本控制，以跟踪随时间的变化。

## 可重用提示文件（实验性）

提示文件（_prompts_）让您构建和共享带有额外上下文的可重用提示指令。提示文件是一个 Markdown 文件，它模仿了在 Copilot Chat 中编写提示的现有格式（例如，`Rewrite #file:x.ts`）。这允许混合自然语言指令、额外上下文，甚至链接到其他提示文件作为依赖项。

虽然自定义指令有助于为每个 AI 工作流程添加整个代码库的上下文，但提示文件让您可以为特定的聊天交互添加指令。

常见用例包括：

* **代码生成**：为组件、测试或迁移创建可重用的提示（例如，React 表单或 API 模拟）。
* **领域专业知识**：通过提示分享专业知识，例如安全实践或合规检查。
* **团队协作**：使用对规范和文档的引用记录模式和指南。
* **入职**：为复杂过程或项目特定模式创建分步指南。

### 提示文件示例

* `react-form.prompt.md` - 记录一个用于生成表单的可重用任务：
您的目标是生成一个新的 React 表单组件。

如果未提供，请询问表单名称和字段。

表单的要求：
* 使用表单设计系统组件：[design-system/Form.md](../i18n/zh-cn/docs/design-system/Form.md)
* 使用 `react-hook-form` 进行表单状态管理：
* 始终为您的表单数据定义 TypeScript 类型
* 优先使用 *uncontrolled* 组件，使用 register
* 使用 `defaultValues` 防止不必要的重新渲染
* 使用 `yup` 进行验证：
* 在单独的文件中创建可重用的验证模式
* 使用 TypeScript 类型确保类型安全
* 自定义用户友好的验证规则

* `security-api.prompt.md` - 记录可用于对 REST API 进行安全审查的可重用安全实践：

    ```markdown
    安全的 REST API 审查：
    * 确保所有端点都受到身份验证和授权的保护
    * 验证所有用户输入并清理数据
    * 实施速率限制和节流
    * 实施安全事件的日志记录和监控
    …
    ```

### 使用

要启用提示文件，请配置 `setting(chat.promptFiles)` VS Code 设置。默认情况下，提示文件位于工作区的 `.github/prompts` 目录中。您还可以[指定其他文件夹](#prompt-files-experimental-settings)来存放提示文件。

#### 创建提示文件

1. 将 `setting(chat.promptFiles)` 设置为 `.github/prompts` 目录的 `true`。

1. 在工作区的 `.github/prompts` 目录中创建一个 `.prompt.md` 文件。

    或者，使用命令面板中的 **Create Prompt** 命令 (`kb(workbench.action.showCommands)`)。

1. 使用 Markdown 格式编写提示说明。

    在提示文件中，可以通过 Markdown 链接 (`[index](../index.ts)`) 或 `#file:../index.ts` 引用工作区中的其他文件。

    您还可以引用其他 `.prompt.md` 文件来创建提示层次结构，以便在多个提示文件中共享可重用的提示。

#### 创建用户提示文件

用户提示文件存储在您的[用户配置文件](/i18n/zh-cn/docs/configure/profiles.md)中。使用用户提示文件，您可以在多个工作区中共享可重用的提示。

您可以像添加工作区提示文件一样将用户提示文件添加到聊天提示中。

要创建用户提示文件：

1. 从命令面板中选择 **Create User Prompt** 命令 (`kb(workbench.action.showCommands)`)。

1. 为您的提示文件输入一个名称。

1. 使用 Markdown 格式编写提示说明。

#### 将提示文件附加到聊天请求

1. 选择 **Attach Context** <i class="codicon codicon-attach"></i> 图标 (`kb(workbench.action.chat.attachContext)`)，然后选择 **Prompt...**。

    或者，使用命令面板中的 **Chat: Use Prompt** 命令 (`kb(workbench.action.showCommands)`)。

1. 从快速选择中选择一个提示文件，将其附加到您的聊天请求中。

    您可以在 Copilot Chat 和 Copilot Edits 中使用提示文件。

1. 如有必要，附加任务所需的其他上下文文件。

    对于可重用的任务，只需发送提示，而无需任何额外的说明。
要进一步完善可重用的提示，请包含额外的说明以提供更多任务背景信息。

> [!TIP]
> 通过使用 Markdown 链接引用额外的上下文文件，如 API 规范或文档，为 Copilot 提供更完整的信息。

## 设置

### 自定义说明设置

* `setting(github.copilot.chat.codeGeneration.useInstructionFiles)`：控制是否将 `.github/copilot-instructions.md` 中的代码说明添加到 Copilot 请求中。
* `setting(github.copilot.chat.codeGeneration.instructions)` _(实验性)_：将添加到生成代码的 Copilot 请求中的一组说明。
* `setting(github.copilot.chat.testGeneration.instructions)` _(实验性)_：将添加到生成测试的 Copilot 请求中的一组说明。
* `setting(github.copilot.chat.reviewSelection.instructions)` _(预览版)_：将添加到审查当前编辑器选择的 Copilot 请求中的一组说明。
* `setting(github.copilot.chat.commitMessageGeneration.instructions)` _(实验性)_：将添加到生成提交消息的 Copilot 请求中的一组说明。
* `setting(github.copilot.chat.pullRequestDescriptionGeneration.instructions)` _(实验性)_：将添加到生成拉取请求标题和描述的 Copilot 请求中的一组说明。

### 提示文件（实验性）设置

* `setting(chat.promptFiles)` _(实验性)_：启用提示文件位置。使用 `{ "/path/to/folder": boolean }` 表示法来指定特定路径及其是否启用。相对路径从工作区的根文件夹解析。

    | 设置值 | 描述 |
    |---------------|-------------|
    | `{ "/path/to/folder": boolean }` | 为特定路径启用提示文件。指定一个或多个包含提示文件的文件夹。相对路径从工作区的根文件夹解析。<br/>默认情况下，`.github/prompts` 已添加但未启用。 |

## 相关内容

* 通过 [Copilot Chat](/i18n/zh-cn/docs/copilot/copilot-chat.md) 开始 AI 聊天对话。
* 通过 [Copilot Edits](/i18n/zh-cn/docs/copilot/copilot-edits.md) 开始 AI 驱动的编辑会话。