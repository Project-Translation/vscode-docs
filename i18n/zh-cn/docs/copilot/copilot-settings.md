---
Order: 14
Area: copilot
TOCTitle: 设置参考
ContentId: 7b232695-cbbe-4f3f-a625-abc7a5e6496c
PageTitle: GitHub Copilot 在 VS Code 中的设置参考
DateApproved: 03/05/2025
MetaDescription: GitHub Copilot 在 Visual Studio Code 中的配置设置概览。
MetaSocialImage: images/shared/github-copilot-social.png
---
# GitHub Copilot 在 VS Code 中的设置参考

本文列出了 GitHub Copilot 在 Visual Studio Code 中的配置设置。有关在 VS Code 中使用设置的一般信息，请参阅[用户和工作区设置](/i18n/zh-cn/docs/configure/settings.md)，以及[变量参考](/i18n/zh-cn/docs/reference/variables-reference.md)以了解预定义变量支持的信息。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup)免费使用 Copilot，并获得每月的完成和聊天交互限制。

团队正在持续改进 VS Code 中的 Copilot 并添加新功能。有些功能仍处于实验阶段。试用它们并在[我们的问题](https://github.com/microsoft/vscode-copilot-release/issues)中分享您的反馈。获取更多关于[VS Code 中的功能生命周期](/i18n/zh-cn/docs/configure/settings.md#feature-lifecycle)的信息。

## 常规设置

* `setting(github.copilot.editor.enableAutoCompletions)`：自动显示内联完成。
* `setting(github.copilot.enable)`：启用或禁用指定[语言](/i18n/zh-cn/docs/languages/identifiers.md)的 Copilot 完成。
* `setting(github.copilot.editor.enableCodeActions)`：控制是否在可用时显示 Copilot 命令作为代码操作。
* `setting(github.copilot.renameSuggestions.triggerAutomatically)`：控制 Copilot 是否为重命名生成建议。
* `setting(chat.commandCenter.enabled)` _(实验性)_：控制命令中心是否显示聊天操作的菜单。
* `setting(workbench.commandPalette.experimental.askChatLocation)` _(实验性)_：控制命令面板应在何处询问聊天问题。
* `setting(github.copilot.chat.search.semanticTextResults)` _(实验性)_：在搜索视图中启用语义搜索结果。
* `setting(github.copilot.nextEditSuggestions.enabled)` _(预览版)_：启用 Copilot 下一编辑建议 (Copilot NES) _(预览版)_。
* `setting(editor.inlineSuggest.edits.codeShifting)`：配置 Copilot NES 是否能够移动您的代码以显示建议。
* `setting(editor.inlineSuggest.edits.renderSideBySide)`：配置 Copilot NES 是否可以尽可能并排显示较大的建议，或者 Copilot NES 是否应始终在相关代码下方显示较大的建议。

## 聊天设置
* `setting(github.copilot.chat.codesearch.enabled)` _(预览)_: 在提示中使用 `#codebase` 时，Copilot 会自动发现相关文件以进行编辑。
* `setting(github.copilot.chat.followUps)`: 控制 Copilot 是否应在聊天中建议后续问题。
* `setting(github.copilot.chat.localeOverride)`: 指定 Copilot 应使用的语言环境，例如 `en` 或 `fr`。
* `setting(github.copilot.chat.runCommand.enabled)`: 在聊天视图中启用 `/runCommand` 意图以运行 VS Code 命令。
* `setting(github.copilot.chat.useProjectTemplates)`: 在使用 `/new` 时，使用相关的 GitHub 项目作为起始项目。
* `setting(github.copilot.chat.scopeSelection)`: 如果您使用 `/explain` 且活动编辑器没有选择，是否提示特定符号范围。
* `setting(github.copilot.chat.terminalChatLocation)`: 控制从终端发起的聊天查询应在哪里打开。
* `setting(chat.experimental.detectParticipant.enabled)` _(实验性)_: 在聊天视图中启用聊天参与者检测。
* `setting(chat.editor.fontFamily)`: 聊天代码块中的字体系列。
* `setting(chat.editor.fontSize)`: 聊天代码块中的字体大小（以像素为单位）。
* `setting(chat.editor.fontWeight)`: 聊天代码块中的字体粗细。
* `setting(chat.editor.lineHeight)`: 聊天代码块中的行高（以像素为单位）。
* `setting(chat.editor.wordWrap)`: 在聊天代码块中切换行包装。
* `setting(chat.implicitContext.enabled)` _(预览)_ - 配置是否应自动将活动编辑器添加为聊天提示的上下文。

## Copilot 编辑设置

* `setting(chat.editing.confirmEditRequestRemoval)` - 在撤销编辑之前请求确认（默认值：`true`）
* `setting(chat.editing.confirmEditRequestRetry)` - 在重新执行最后一次编辑之前请求确认（默认值：`true`）
* `setting(github.copilot.chat.edits.temporalContext.enabled)` _(实验性)_: 是否在 Copilot 编辑中包含最近查看和编辑的文件。
* `setting(github.copilot.chat.codesearch.enabled)` _(预览)_: 在提示中使用 `#codebase` 时，Copilot 会自动发现相关文件以进行编辑。
* `setting(chat.editing.alwaysSaveWithGeneratedChanges)` - 自动将 Copilot 编辑生成的更改保存到磁盘（默认值：`false`）
* `setting(chat.implicitContext.enabled)` _(预览)_ - 配置是否应自动将活动编辑器添加为聊天提示的上下文。
* `setting(chat.editing.autoAcceptDelay)` - 配置建议编辑在多久后自动接受，使用零来禁用自动接受（默认值：0）
* `setting(chat.agent.maxRequests)` - Copilot 编辑在代理模式下可以发出的最大请求数（默认值：15）
* `setting(github.copilot.chat.edits.suggestRelatedFilesFromGitHistory)`_(实验性)_ - 在 Copilot 编辑中从 git 历史记录中建议相关文件（默认值：`false`）
* `setting(github.copilot.chat.agent.runTasks)` - 在 Copilot 编辑的代理模式下运行工作区任务（默认值：`true`）
## 内联聊天设置

* `setting(inlineChat.acceptedOrDiscardBeforeSave)`: 控制编辑器中未完成的内联聊天会话是否阻止保存文件。
* `setting(inlineChat.finishOnType)`: 是否在更改区域之外输入时结束内联聊天会话。
* `setting(inlineChat.holdToSpeech)`: 按住内联聊天键盘快捷键是否会自动启用语音识别。
* `setting(inlineChat.inlineChat.lineEmptyHint)` _(实验性)_: 控制是否在空行上显示内联聊天的提示。
* `setting(inlineChat.lineNaturalLanguageHint)` _(实验性)_: 实验性建议，当一行主要由单词组成时触发内联聊天。
* `setting(github.copilot.chat.editor.temporalContext.enabled)` _(实验性)_: 是否在内联聊天中包含最近查看和编辑的文件与Copilot请求。

## 自定义Copilot提示

* `setting(github.copilot.chat.codeGeneration.useInstructionFiles)`: 控制是否将`.github/copilot-instructions.md`中的代码指令添加到Copilot请求中。
* `setting(github.copilot.chat.codeGeneration.instructions)` _(实验性)_: 将添加到生成代码的Copilot请求中的一组指令。
* `setting(github.copilot.chat.testGeneration.instructions)` _(实验性)_: 将添加到生成测试的Copilot请求中的一组指令。
* `setting(github.copilot.chat.reviewSelection.instructions)` _(预览)_: 将添加到审查当前编辑器选择的Copilot请求中的一组指令。
* `setting(github.copilot.chat.commitMessageGeneration.instructions)` _(实验性)_: 将添加到生成提交消息的Copilot请求中的一组指令。
* `setting(github.copilot.chat.pullRequestDescriptionGeneration.instructions)` _(实验性)_: 将添加到生成拉取请求标题和描述的Copilot请求中的一组指令。
* `setting(chat.promptFiles)` _(实验性)_: 启用提示文件并指定提示文件文件夹。设置为`true`以使用默认位置（`.github/prompts`），或使用`{ "/path/to/folder": boolean }`表示法指定不同的路径。相对路径从工作区的根文件夹解析。

## 调试设置

* `setting(github.copilot.chat.startDebugging.enabled)` _(预览)_: 在聊天视图中启用实验性的`/startDebugging`意图以生成调试配置。

## 测试设置
* `setting(github.copilot.chat.generateTests.codeLens)` _(实验性)_：为当前测试覆盖信息未覆盖的符号显示**生成测试**代码镜头。
* `setting(github.copilot.chat.setupTests.enabled)` _(实验性)_：启用实验性的`/setupTests`意图和在`/tests`生成中的提示。
* `setting(github.copilot.chat.fixTestFailure.enabled)`：启用聊天中的预览`/fixTestFailure`意图，并在未找到测试设置时自动委托某些`/fix`调用。
* `setting(github.copilot.chat.testGeneration.instructions)` _(实验性)_：一组将添加到生成测试的Copilot请求中的指令。

## 笔记本设置

* `setting(notebook.experimental.generate)` _(实验性)_：启用**生成**操作，以在笔记本编辑器中创建启用内联聊天的代码单元。

## 辅助功能设置

* `setting(inlineChat.accessibleDiffView)`：内联聊天是否也为其更改渲染一个可访问的差异查看器。
* `setting(accessibility.signals.chatRequestSent)`：当发出聊天请求时播放信号 - 声音（音频提示）和/或公告（警报）。
* `setting(accessibility.signals.chatResponseReceived)`：当接收到响应时播放声音/音频提示。
* `setting(accessibility.verbosity.inlineChat)`：提供有关如何访问内联编辑器聊天辅助功能帮助菜单的信息，并在输入获得焦点时提供描述如何使用该功能的提示警报。
* `setting(accessibility.verbosity.inlineCompletions)`：提供有关如何访问内联完成悬停和可访问视图的信息。
* `setting(accessibility.verbosity.panelChat)`：提供有关在聊天输入获得焦点时如何访问聊天帮助菜单的信息。
* `setting(accessibility.voice.keywordActivation)`：控制是否识别关键词短语“嘿代码”以启动语音聊天会话。
* `setting(accessibility.voice.autoSynthesize)`：控制当使用语音作为输入时，是否应自动朗读文本响应。
* `setting(accessibility.voice.speechTimeout)`：在您停止讲话后，语音语音识别保持活动状态的持续时间（以毫秒为单位）。

## 相关资源

* [快速概览VS Code中的Copilot功能](/i18n/zh-cn/docs/copilot/copilot-vscode-features.md)