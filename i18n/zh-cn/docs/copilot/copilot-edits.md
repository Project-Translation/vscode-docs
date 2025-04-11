---
Order: 8
Area: copilot
TOCTitle: Copilot 编辑
ContentId: 393f3945-0821-42ca-bdd7-fb82affacb6a
PageTitle: Copilot 编辑
DateApproved: 03/05/2025
MetaDescription: 开始使用 Copilot 编辑，启动一个 AI 驱动的代码编辑会话，跨项目中的多个文件进行编辑。
MetaSocialImage: images/shared/github-copilot-social.png
---
# Copilot 编辑

使用 Copilot 编辑启动一个 AI 驱动的代码编辑会话，并通过自然语言在多个文件中快速迭代代码更改。Copilot 编辑直接在编辑器中应用编辑，您可以在原地查看它们，并了解周围代码的完整上下文。

Copilot 编辑可以以两种模式运行：

* [_编辑模式_](#use-edit-mode)：选择要编辑的文件，提供相关上下文和提示，Copilot 将建议代码编辑。
* [_代理模式_](#use-agent-mode-preview)（预览）：让 Copilot 自主规划所需的任务和相关文件，以实现请求。Copilot 将应用代码编辑并建议终端命令，并持续迭代以解决出现的任何问题。

> [!IMPORTANT]
> 如果您使用的是笔记本，目前 Copilot 编辑的支持有限。我们建议您在 VS Code 中使用笔记本时使用 [Copilot 聊天](/i18n/zh-cn/docs/copilot/copilot-chat.md) 或 [内联聊天](/i18n/zh-cn/docs/copilot/copilot-chat.md#inline-chat)。

以下视频演示了如何使用 Copilot 编辑来扩展一个基本的 Express 应用程序，例如添加新页面、导航栏和主题切换器。

<video src="images/copilot-edits/copilot-edits-hero.mp4" title="使用 Copilot 编辑修改 Express 应用程序" loop controls muted></video>

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup) 免费使用 Copilot，并获得每月的完成和聊天互动限制。

## 编辑模式与代理模式（预览）

Copilot 可以以两种模式运行：_编辑模式_ 和 _代理模式_。这些模式迎合了不同的用户偏好和工作流程，允许灵活地编辑和迭代代码。

在编辑模式下，您提供相关上下文和您希望 Copilot 处理的文件。Copilot 将根据您的提示建议代码编辑，您可以通过提供后续提示手动迭代代码更改。

在代理模式下，Copilot 自主确定相关上下文和文件，确定需要执行的任务，并提供代码更改和终端命令以完成请求。然后它独立迭代以实现所需的结果，解决出现的问题。

Copilot 编辑的代理模式使用一组 [_工具_](#agent-mode-tools)，这些工具允许它执行特定任务，例如编辑文件、运行和监控终端命令，或验证代码。这些工具可以并行运行以完成请求任务。

在这两种模式下，您可以 [审查生成的编辑](#accept-or-discard-edits) 并决定保留或拒绝它们。

## 使用编辑模式

在编辑模式下，您选择要编辑的文件并提供相关上下文和提示。Copilot 将根据您的提示建议代码编辑。

1. 打开 Copilot 编辑视图 (`kb(workbench.action.chat.openEditSession)`)。
* 在 VS Code 标题栏的 Copilot 菜单中选择 **打开 Copilot 编辑** (`kb(workbench.action.chat.openEditSession)`)。

* 或者，选择 **视图** > **外观** > **次要侧边栏** (`kb(workbench.action.toggleAuxiliaryBar)`) 以打开次要侧边栏，然后选择 **Copilot 编辑** 视图。

1. 从模式下拉菜单中选择 **编辑**。

    ![显示 Copilot 编辑视图的屏幕截图，突出显示已选择的编辑模式。](images/copilot-edits/copilot-edits-edit-mode.png)

1. 使用 **添加文件** 指示相关上下文以供 Copilot 提示。

    您还可以将文件、文件夹或编辑器选项卡拖放到 Copilot 编辑视图中，以将其添加为上下文。

    Copilot 会自动将活动编辑器添加为上下文。使用 `setting(chat.implicitContext.enabled)` 设置来配置是否应自动添加活动编辑器。

    当您向提示中添加一个或多个文件时，Copilot 编辑会根据 Git 历史记录提出其他相关文件。使用 `setting(github.copilot.chat.edits.suggestRelatedFilesFromGitHistory)` 设置进行配置。

    > [!TIP]
    > 通过在提示中添加 `#codebase`，让 Copilot 自动查找正确的文件。确保启用 `setting(github.copilot.chat.codesearch.enabled)` _(预览)_ 设置以获得最佳结果。了解更多关于[向 Copilot 提示添加上下文](/i18n/zh-cn/docs/copilot/copilot-chat-context.md)的信息。

1. 输入提示以请求代码编辑。请具体且精确地说明您想要的更改，并将较大的任务分解为较小的任务。

    Copilot 编辑会在编辑器中流式传输编辑，并在 Copilot 编辑视图中显示更改文件的列表。

1. 审查建议的编辑，并接受或丢弃建议的编辑。

    作为用户，您可以控制对项目所做的更改，并可以[审查生成的编辑](#accept-or-discard-edits)。

1. 迭代代码更改。

    如果您对编辑不太满意，您可以提出后续问题，例如“不要包含电话号码”，或“使用 jest 而不是 vitest”。或者您可以进一步增量编辑您的代码。例如，在构建 Web 应用程序时，使用一系列提示，如“添加导航栏”，“添加主题切换器”，“以 JSON 格式在 MongoDB 中存储订单项目”。

## 使用代理模式（预览）

在代理模式下，Copilot 编辑以更自主和动态的方式运作，以实现所需的结果。Copilot 代理模式确定相关上下文，提供代码更改和终端命令，并迭代以修复问题。为了执行这些任务，代理模式使用一组[_工具_](#agent-mode-tools)。

> [!IMPORTANT]
> 如果您是 Copilot 商业或企业用户，您组织的管理员必须选择加入使用 Copilot 编辑器预览功能。了解更多关于[在您的组织中管理 Copilot 政策](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization/managing-policies-for-copilot-in-your-organization#enabling-copilot-features-in-your-organization)的信息。

要在 Copilot 编辑中使用代理模式：

1. 在 [VS Code Insiders](https://code.visualstudio.com/insiders) 中打开您的项目。
> [!NOTE]
> 代理模式处于预览阶段，目前可在 [VS Code Insiders](https://code.visualstudio.com/insiders/) 中使用。正在逐步向 VS Code 稳定版推出，一旦为您启用代理模式，您将在 Copilot Edits 视图中看到模式下拉菜单。

1. 打开 Copilot Edits 视图 (`kb(workbench.action.chat.openEditSession)`)

    * 从 VS Code 标题栏中的 Copilot 菜单中选择 **打开 Copilot Edits** (`kb(workbench.action.chat.openEditSession)`)。

    * 或者，选择 **视图** > **外观** > **次要侧边栏** (`kb(workbench.action.toggleAuxiliaryBar)`) 以打开次要侧边栏，然后选择 **Copilot Edits** 视图。

1. 从模式下拉菜单中选择 **代理**

    ![显示 Copilot Edits 视图的屏幕截图，突出显示选择了代理模式。](images/copilot-edits/copilot-edits-agent-mode.png)

1. 输入提示以请求代码编辑。

    您不必指定要处理的文件。在代理模式下，Copilot Edits 会自动确定相关上下文和要编辑的文件。

    ![显示 Copilot Edits 视图的屏幕截图，突出显示 Copilot 在代码库中搜索相关文件。](images/copilot-edits/copilot-edits-agent-search-codebase.png)

    Copilot Edits 在编辑器中流式传输编辑并更新已更改文件列表。此外，Copilot 还可能建议运行终端命令。例如，运行测试或构建应用程序。

1. 审查建议的代码编辑，并确认 Copilot 是否可以运行提议的终端命令。

    作为用户，您可以控制对项目所做的更改，并可以[审查生成的编辑](#accept-or-discard-edits)。

    Copilot 在运行终端命令前请求确认。您可以选择修改响应中的提议终端命令，然后选择 **继续** 运行它。

    如果您的项目在 `tasks.json` 中配置了[任务](/i18n/zh-cn/docs/debugtest/tasks.md)，代理模式会尝试运行适当的任务。例如，如果您定义了构建任务，代理模式将在运行应用程序前运行构建任务。使用 `setting(github.copilot.chat.agent.runTasks)` 设置启用或禁用运行工作区任务。

1. Copilot Edits 检测代码编辑和终端命令中的问题，并将迭代并执行额外操作以解决这些问题。

    例如，代理模式可能会因为代码编辑而运行单元测试。如果测试失败，Copilot 将使用测试结果来解决问题。

1. 继续提出后续问题并迭代 Copilot Edits 提供的代码更改。

Copilot Edits 代理模式会多次迭代以解决问题和问题。`setting(chat.agent.maxRequests)` 设置控制 Copilot Edits 在代理模式下可以发出的最大请求数。

## 接受或丢弃编辑

Copilot Edits 为您提供了一个代码审查流程，您可以接受或拒绝每个 AI 生成的编辑。如果您拒绝编辑，修改的文件将恢复到之前接受的状态。

Copilot 会在更改文件列表中列出已编辑的文件。具有待处理 Copilot 编辑的文件在资源管理器视图和编辑器选项卡中也有指示器。
![显示Copilot编辑视图的屏幕截图，突出显示已更改文件列表以及资源管理器视图和编辑器选项卡中的指示器。](images/copilot-edits/copilot-edits-changed-files.png)

使用编辑器覆盖控件，您可以通过 `kbstyle(Up)` (<i class="codicon codicon-arrow-up"></i>) 和 `kbstyle(Down)` (<i class="codicon codicon-arrow-down"></i>) 控件在建议的编辑之间导航。使用**保留**或**撤销**按钮接受或拒绝给定文件的编辑。

![显示带有建议更改的编辑器的屏幕截图，突出显示编辑器覆盖控件中的审阅控件。](images/copilot-edits/copilot-edits-file-review-controls.png)

要接受或拒绝文件内的特定编辑，请将鼠标悬停在代码编辑上，并使用该编辑的**保留**或**撤销**控件。

或者，您还可以从Copilot编辑视图中的已更改文件列表中接受或拒绝更改：

* 在已更改文件列表中选择**保留** (`kb(chatEditing.acceptAllFiles)`) 或**撤销** (`kb(chatEditing.discardAllFiles)`) 以接受或丢弃所有编辑。

* 选择单个文件上的**保留**或**撤销**图标以对该特定文件应用操作

![显示Copilot编辑视图的屏幕截图，突出显示接受所有和丢弃所有按钮。](images/copilot-edits/copilot-edits-accept-discard.png)

通过 `setting(chat.editing.autoAcceptDelay)` 设置，您可以配置一个延迟时间，之后建议的编辑将自动接受。将鼠标悬停在编辑器覆盖控件上以取消自动接受倒计时。

当您关闭VS Code时，待处理编辑的状态会被记住。当您重新打开VS Code时，待处理的编辑会被恢复，您仍然可以接受或丢弃这些编辑。

> [!NOTE]
> 在代理模式下，无论是否启用了自动保存 (`setting(files.autoSave)`)，编辑都会自动保存到磁盘。您仍然可以审阅编辑并选择拒绝它们（如果需要）。

## 中断代理模式请求

要中断正在进行的请求，您可以选择**暂停**或**取消**它。当您暂停请求时，Copilot会停止处理请求并等待您的输入。

当您暂停请求时，您可以选择输入新的提示，这将取消当前请求，或者您可以选择恢复当前请求。

当您取消请求时，Copilot会中断并结束当前活动的请求。您仍然可以[审阅并接受或拒绝](#accept-or-discard-edits)截至该点的更改。

## 撤销编辑

当您发送请求对代码进行编辑时，您可能希望回滚其中的一些更改，例如因为您想使用另一种实现策略。

您可以使用Copilot编辑视图标题栏中的**撤销最后编辑**控件来恢复最后的编辑，并返回到发送最后请求之前的状态。执行最后编辑的撤销后，您可以使用Copilot编辑视图标题栏中的**重做最后编辑**控件重新执行这些编辑。

![显示Copilot编辑视图的屏幕截图，突出显示视图标题栏中的撤销和重做操作。](images/copilot-edits/copilot-edits-undo-redo.png)
您还可以在 Copilot Edits 视图中悬停在请求上时使用 **撤销编辑（删除）** 控件（`kbstyle(x)` 图标）来撤销从该请求开始的所有编辑。

![显示 Copilot Edits 视图的屏幕截图，突出显示特定请求的撤销编辑控件。](images/copilot-edits/copilot-edits-undo-request.png)

> [!TIP]
> 有时 Copilot 在生成编辑时会走上错误的道路。一旦发生这种情况，通过添加到对话中，很难说服它采用另一种方法。在这种情况下，使用 **撤销最后一次编辑** 回到您同意 Copilot 响应的点。然后从那里开始使用改进的提示重新开始。

## 向 Copilot Edits 发送聊天请求

Copilot Chat 非常适合询问问题和探索关于您的项目或一般技术主题的想法。与其将 Copilot Chat 中的每个代码块应用到您的代码中，您可以将聊天会话转移到 Copilot Edits。Copilot Edits 针对代码编辑进行了优化，可以直接在您的代码中应用代码建议，同时跨多个文件进行操作。

在聊天视图中，选择聊天对话底部的 **使用 Copilot 编辑** 按钮，以使用 Copilot Edits 应用建议的代码更改。如果您的聊天会话中有多个聊天请求，您可以选择要转移到 Copilot Edits 的请求。

![突出显示聊天视图中将聊天对话移动到 Copilot Edits 的“使用 Copilot 编辑”按钮的屏幕截图。](images/copilot-edits/copilot-chat-edit-with-copilot.png)

将聊天请求移动到 Copilot Edits 后，该聊天请求将从聊天视图中的聊天对话中移除。

## 代理模式工具

为了完成一个请求，Copilot Edits 使用一组 _工具_ 来完成各个任务。将这些工具视为 Copilot 可以用来执行特定任务的专业工具。例如，这些任务包括列出目录中的文件、编辑工作区中的文件、运行终端命令、获取终端输出等。

根据工具的结果，Copilot 可能会调用其他工具来完成整体请求。例如，如果代码编辑导致文件中的语法错误，Copilot 可能会探索另一种方法并建议不同的代码更改。

尽管代理模式可以以自主方式运行，但您可以控制生成的编辑和运行的终端命令。

## 设置

以下列表包含与 Copilot Edits 相关的设置。您可以通过设置编辑器 (`kb(workbench.action.openSettings)`) 配置设置。
* `setting(chat.editing.confirmEditRequestRemoval)` - 在撤销编辑前请求确认（默认值：`true`）
* `setting(chat.editing.confirmEditRequestRetry)` - 在重做最后一次编辑前请求确认（默认值：`true`）
* `setting(chat.implicitContext.enabled)` _(预览版)_ - 配置是否应自动将活动编辑器添加为聊天提示的上下文。
* `setting(chat.editing.autoAcceptDelay)` - 配置建议编辑在多长时间后自动接受，使用零来禁用自动接受（默认值：0）
* `setting(github.copilot.chat.codesearch.enabled)` _(预览版)_ - 当您在提示中添加`#codebase`时，让Copilot查找正确的文件，类似于代理模式的工作方式（默认值：`false`）
* `setting(chat.agent.maxRequests)` - Copilot Edits在代理模式下可以发出的最大请求数（免费用户默认值：5，其他用户默认值：15）
* `setting(github.copilot.chat.edits.suggestRelatedFilesFromGitHistory)`_(实验性)_ - 在Copilot Edits中从git历史记录中建议相关文件（默认值：`false`）
* `setting(github.copilot.chat.agent.runTasks)` - 在Copilot Edits的代理模式下运行工作区任务（默认值：`true`）

## 键盘快捷键

以下列表包含与Copilot Edits相关的默认键盘快捷键。您可以使用键盘快捷键编辑器（`kb(workbench.action.openGlobalKeybindings)`）修改任何默认键盘快捷键。

* `kb(workbench.action.chat.openEditSession)` - 打开Copilot Edits视图
* `kb(workbench.action.chat.sendToChatEditing)` - 从聊天视图发送提示到Copilot Edits
* `kb(workbench.action.chat.attachContext)` - 将上下文附加到您的提示
* `kb(chatEditing.saveAllFiles)` - 将所有编辑的文件保存到磁盘
* `kb(chatEditing.acceptAllFiles)` - 接受所有编辑
* `kb(chatEditing.discardAllFiles)` - 丢弃所有编辑
* `kb(chatEditor.action.navigatePrevious)` - 在文件内导航到前一个编辑
* `kb(chatEditor.action.navigateNext)` - 在文件内导航到下一个编辑

> [!TIP]
> 如果您想更改特定于Copilot Edits视图的操作的键盘快捷键，您需要在`when`子句中包含以下条件：`chatLocation == 'editing-session'`。

## 限制

* 目前还不支持多个同时进行的编辑会话。
* 在编辑会话中，尚不支持使用`@workspace /new`来搭建新项目。目前，请使用Copilot Chat进行初始搭建。
* 虽然`#codebase`在查找与您的查询相关的上下文方面表现出色，但后续生成的编辑质量差异很大。尝试使用`setting(github.copilot.chat.codesearch.enabled)` _(预览版)_ 设置，以获得改进的、代理化的体验来查找文件，或者明确将文件添加到您的提示中以创建更好的结果。
* 对Jupyter笔记本、其他自定义文本格式和二进制文件格式的支持缺失或未经测试。
* Copilot Edits每10分钟限于7个编辑请求。

## 常见问题

### Copilot Edits与Copilot Chat有何不同？
[Copilot Chat](/i18n/zh-cn/docs/copilot/copilot-chat.md) 和 Copilot Edits 都使用对话界面，您可以使用自然语言提示来获取 AI 驱动的建议。Copilot Edits 和 Copilot Chat 之间有几个明显的区别。

Copilot Edits 将您置于**代码编辑**的环境中，您可以启动编辑会话并使用提示来更改您的代码库。Copilot Edits 可以直接在您的代码库中的**多个文件**上生成并应用代码更改。您可以立即在代码的上下文中**预览生成的编辑**。

[聊天视图](/i18n/zh-cn/docs/copilot/copilot-chat.md#chat-view)为您提供了一个更**通用**的聊天界面，用于询问关于您的代码或一般技术主题的问题。Copilot 还可以提供代码建议并在聊天对话中生成代码块。您需要**手动应用**每个代码块到项目中的不同文件中，以评估它们的有效性。

[内联聊天](/i18n/zh-cn/docs/copilot/copilot-chat.md#inline-chat)通过在编辑器中提供聊天界面，保持您在编码流程中，您可以直接在代码的上下文中**预览生成的代码**建议。内联聊天的范围仅限于启动它的编辑器，因此它只能为**单个文件**提供代码建议。您还可以使用内联聊天来询问通用问题。

Copilot Edits 还为您提供了一个**代码审查流程**，您可以轻松审查生成的编辑并决定接受或丢弃它们。Copilot Chat 没有这种代码审查机制。此外，您可以撤销过去的编辑并**回滚更改**到之前接受的状态。

下表显示了每种体验的功能比较。

| 功能                  | Copilot Edits | 聊天视图 | 内联聊天 | 快速聊天 |
|-----------------------------|:-------------:|:---------:|:-----------:|:----------:|
| 多文件编辑            | ✅ | ✅* |    | ✅* |
| 预览代码编辑          | ✅ |     | ✅ |     |
| 代码审查流程            | ✅ |     |    |      |
| 回滚更改           | ✅ |     |    |      |
| 附加上下文              | ✅ | ✅ | ✅ | ✅  |
| 使用参与者和命令 |    | ✅  |    | ✅  |
| 生成 shell 命令     |    | ✅  |    | ✅  |
| 通用聊天        |    | ✅  | ✅ | ✅  |

\* _代码块包含在聊天对话中，需要手动应用到正确的文件中_

### 我可以更改 Copilot Edits 视图的位置吗？

您可以将 Copilot Edits 视图拖放到活动栏中，以在主侧边栏中显示它。您还可以将其移动到次要侧边栏。了解更多关于 [自定义布局](/i18n/zh-cn/docs/configure/custom-layout.md#workbench) 的信息。

### 为什么我会使用编辑模式而不是代理模式？

考虑以下标准来选择编辑模式和代理模式：
* **编辑范围**：如果您的请求仅涉及代码编辑，并且您知道更改的具体范围，您可以使用编辑模式。
* **预览功能**：代理模式仍处于预览阶段，可能不适用于所有场景。
* **持续时间**：代理模式涉及处理请求的多个步骤，因此可能需要更长时间才能获得响应。例如，确定相关上下文和文件进行编辑，确定行动计划等。
* **非确定性**：代理模式会评估生成编辑的结果，并可能多次迭代。因此，代理模式可能比编辑模式更不确定。
* **请求配额**：在代理模式下，根据任务的复杂性，一个提示可能会导致对后端的多次请求。

## 我可以将 Copilot Edits 与笔记本一起使用吗？

当您使用笔记本时，Copilot Edits 的支持有限。例如，在 VS Code 中使用笔记本时无法使用代理模式。

我们建议您在 VS Code 中使用笔记本时使用 [Copilot Chat](/i18n/zh-cn/docs/copilot/copilot-chat.md) 或 [Inline Chat](/i18n/zh-cn/docs/copilot/copilot-chat.md#inline-chat)。

## 相关内容

* [快速了解 VS Code 中 Copilot 的功能](/i18n/zh-cn/docs/copilot/copilot-vscode-features.md)
* [使用 Copilot Chat 进行 AI 聊天对话](/i18n/zh-cn/docs/copilot/copilot-chat.md)