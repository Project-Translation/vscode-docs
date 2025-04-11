---
Order: 5
Area: copilot
TOCTitle: 代码补全
ContentId: 7ab2cd6c-45fd-4278-a6e8-1c9e060593ea
PageTitle: 使用 GitHub Copilot 进行 AI 驱动的代码补全
DateApproved: 03/05/2025
MetaDescription: 使用 GitHub Copilot 在 Visual Studio Code 中通过 AI 驱动的代码补全提升您的编码体验。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中使用 GitHub Copilot 进行代码补全

GitHub Copilot 作为一个 AI 驱动的配对程序员，会自动提供建议来完成您的代码、注释、测试等。它在您编写代码时直接在编辑器中提供这些建议，并且可以与多种编程语言和框架一起工作。

Copilot 提供两种类型的建议：

* **代码补全** - 在编辑器中开始输入，Copilot 会提供与您的编码风格相匹配并考虑您现有代码的代码建议。

* **下一个编辑建议（预览版）** - 使用 Copilot 下一个编辑建议（即 Copilot NES）预测您的下一个代码编辑。根据您正在进行的编辑，Copilot NES 既预测您将要进行的下一个编辑的位置，也预测该编辑的内容。

## 入门

1. 安装 GitHub Copilot 扩展。

    > <a class="install-extension-btn" href="vscode:extension/GitHub.copilot?referrer=docs-copilot-ai-powered-suggestions">安装 GitHub Copilot 扩展</a>

1. 使用您的 GitHub 账户登录以使用 Copilot。

    > [!TIP]
    > 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup)免费使用 Copilot，并获得每月的补全和聊天互动限制。

1. 通过我们的 [Copilot 快速入门](/i18n/zh-cn/docs/copilot/getting-started.md)了解 Copilot 在 VS Code 中的关键功能。

## 内联建议

Copilot 在您输入时提供代码建议：有时是当前行的完成，有时是整个新的代码块。您可以接受全部或部分建议，或者继续输入并忽略建议。

请注意在以下示例中，Copilot 如何通过使用淡化的*幽灵文本*建议实现 `calculateDaysBetweenDates` JavaScript 函数：

![JavaScript 幽灵文本建议。](images/inline-suggestions/js-suggest.png)

当您看到内联建议时，您可以使用 `kbstyle(Tab)` 键接受它。

Copilot 尝试为代码建议应用您已有的代码中的相同编码风格。请注意在以下示例中，Copilot 为建议的 `subtract` 方法应用了与 `add` 方法相同的输入参数命名方案。

![JavaScript 幽灵文本建议。](images/inline-suggestions/ts-suggest-parameter-names.png)

### 部分接受建议

您可能不想接受 GitHub Copilot 的整个建议。您可以使用 `kb(editor.action.inlineSuggest.acceptNextWord)` 键盘快捷键接受建议的下一个单词或下一行。

### 替代建议

对于任何给定的输入，Copilot 可能会提供多个替代建议。您可以将鼠标悬停在建议上以选择其他建议。

![悬停在内联建议上可让您从多个建议中选择](images/inline-suggestions/copilot-hover-highlight.png)

### 从代码注释生成建议
而不是依赖 Copilot 来提供建议，您可以通过使用代码注释来提供关于您期望的代码的提示。例如，您可以指定要使用的算法或概念类型（例如，“使用递归”或“使用单例模式”），或者要添加到类中的方法和属性。

以下示例展示了如何指示 Copilot 在 TypeScript 中创建一个表示学生的类，并提供有关方法和属性的信息：

![使用代码注释让 Copilot 在 TypeScript 中生成带有属性和方法的 Student 类。](images/inline-suggestions/ts-suggest-code-comment.png)

## 后续编辑建议（预览）

内联建议在自动完成代码部分方面表现出色。但由于大多数编码活动是编辑现有代码，因此 Copilot 代码完成的自然演进是帮助编辑，无论是在光标处还是更远的地方。编辑通常不是孤立进行的 - 不同场景下需要进行的编辑有一个逻辑流程。Copilot 后续编辑建议（Copilot NES）就是这种演进。

<video src="./images/inline-suggestions/nes-video.mp4" title="Copilot NES 视频" controls poster="./images/inline-suggestions/point3d.png"></video>

根据您正在进行的编辑，Copilot NES 既预测您将要进行的下一个编辑的位置，也预测该编辑的内容。Copilot NES 帮助您保持工作流程，建议与您当前工作相关的未来更改，您只需按 `kbstyle(Tab)` 即可快速导航并接受 Copilot 的建议。建议可能涵盖单个符号、一整行或多行，具体取决于潜在更改的范围。

### 启用编辑建议

Copilot NES 目前处于预览阶段。您可以通过 VS Code 设置 `setting(github.copilot.nextEditSuggestions.enabled)` 来启用它：

1. 打开 VS Code 设置编辑器 (`kb(workbench.action.openSettings)`)
1. 搜索 `github.copilot.nextEditSuggestions.enabled`
1. 启用该设置

> [!IMPORTANT]
> 如果您是 Copilot 商业或企业用户，您的组织管理员必须选择加入使用 Copilot 编辑器预览功能，除了您在编辑器中设置 `setting(github.copilot.nextEditSuggestions.enabled)` 之外。了解更多关于[在您的组织中管理 Copilot 政策](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization/managing-policies-for-copilot-in-your-organization#enabling-copilot-features-in-your-organization)的信息。

### 导航和接受编辑建议

您可以使用 `kbstyle(Tab)` 键快速导航建议的代码更改，节省您查找下一个相关编辑的时间（无需手动搜索文件或引用）。然后，您可以再次按 `kbstyle(Tab)` 键接受建议。

槽中的箭头指示是否有可用的编辑建议。您可以将鼠标悬停在箭头上以探索编辑建议菜单，该菜单包括键盘快捷键和设置配置：
![Copilot NES 槽菜单展开](./images/inline-suggestions/gutter-menu-highlighted-updated.png)
如果编辑建议位于当前编辑器视图下方，箭头将指向下方而不是右方：
![Copilot NES 箭头方向变化](./images/inline-suggestions/nes-arrow-directions.gif)

> [!IMPORTANT]
> 如果您使用的是 VS Code vim 扩展，您可能需要更新您的 `keybindings.json`。了解更多信息请查看 [GitHub 问题](https://github.com/VSCodeVim/Vim/issues/9459#issuecomment-2648156285)。

### 下一编辑建议的使用案例

**捕捉和纠正错误**

* **Copilot 帮助处理简单的错误，如拼写错误。** 它会建议修复缺少或交换的字母，如 `cont x = 5` 或 `conts x = 5`，这些应该为 `const x = 5`。

    ![Copilot NES 修复从 "conts" 到 "const" 的拼写错误](./images/inline-suggestions/nes-typo.gif)

* **Copilot 还可以帮助处理逻辑上的更复杂错误**，如倒置的三元表达式：

    ![Copilot NES 修复斐波那契逻辑错误](./images/inline-suggestions/nes-fib-logic.gif)

    或者应该使用 `&&` 而不是 `||` 的比较：

    ![Copilot NES 修复 if 语句错误](./images/inline-suggestions/nes-de-morgan.gif)

**改变意图**

* **Copilot 建议对代码的其余部分进行与新意图相匹配的更改。** 例如，当将类从 `Point` 更改为 `Point3D` 时，Copilot 会建议在类定义中添加 `z` 变量。接受更改后，Copilot NES 接下来建议将 `z` 添加到距离计算中：

    ![Copilot NES gif 用于更新 Point 到 Point3D](./images/inline-suggestions/nes-point.gif)
    <!-- ![Copilot NES 用于更新 Point 到 Point3D](./images/inline-suggestions/point3d.png)

    ![Copilot NES 用于将 z 添加到 Point3D 的距离计算中](./images/inline-suggestions/point3d-distance.png) -->

**添加新变量或逻辑**

* **使用新添加的参数、变量或函数**。Copilot 帮助您使用刚添加的新代码。这可能是一个小的更改，如在实际方法中调用新的方法参数。

    它也可能是更复杂的：如果您在 VS Code 扩展的 `extension.ts` 中添加了一个新命令，Copilot 首先会建议在 `extension.ts` 中清理该命令。然后当您打开 `package.json` 时，Copilot 建议也注册该命令：

    ![更新 extension.ts 和 package.json 以添加新命令](./images/inline-suggestions/nes-extension-and-package.gif)

    <!-- ![在 package.json 中添加命令](./images/inline-suggestions/add-disposable.png)
    ![在 package.json 中添加命令](./images/inline-suggestions/call-disposable-full.png) -->

**重构**

* **在一个文件中重命名一个变量，Copilot 将建议在其他地方更新它。** 如果您使用了一个新名称或命名模式，Copilot 建议以类似的方式更新后续代码。

    ![Copilot NES 在更新函数名称后建议更改](./images/inline-suggestions/nes-gutter.gif)

* **匹配代码风格**。在复制粘贴一些代码后，Copilot 会建议如何调整它以匹配当前代码的粘贴位置。

### 编辑建议配置选项

要进一步配置编辑建议，请配置以下设置：
* `setting(editor.inlineSuggest.edits.codeShifting)`：如果您不希望 Copilot NES 在显示建议时移动您的代码，请禁用此设置。

* `setting(editor.inlineSuggest.edits.renderSideBySide)`：

     * **auto（默认）**：如果视口中有足够的空间，则并排显示较大的编辑建议，否则建议显示在相关代码下方。
     * **never**：从不并排显示建议，始终在相关代码下方显示建议。

## 提示与技巧

### 上下文

为了给您提供相关的内联建议，Copilot 会查看您编辑器中当前和打开的文件，以分析上下文并创建适当的建议。在使用 Copilot 时，在 VS Code 中打开相关文件有助于设置此上下文，让 Copilot 能够更好地了解您的项目。

### 启用或禁用代码补全

您可以临时启用或禁用代码补全，适用于所有语言或仅特定语言。

要启用或禁用代码补全：

1. 在 VS Code 标题栏中选择 Copilot 菜单，然后选择 **配置代码补全...**。

    ![VS Code 标题栏中的 Copilot 菜单](images/inline-suggestions/configure-code-completions.png)

1. 要为所有语言启用或禁用补全，分别选择 **启用补全** 或 **禁用补全**。

1. 要为当前文件的语言启用或禁用补全，选择 **为 \<language\> 启用补全** 或 **为 \<language\> 禁用补全**。

### 更改 AI 模型

不同的超大规模语言模型（LLM）在不同的数据上进行训练，可能具有不同的能力和优势。您可以更改用于生成代码补全的语言模型。

要更改用于代码补全的模型：

1. 在 VS Code 标题栏中的 Copilot 菜单中选择 **配置代码补全...**。

    ![VS Code 标题栏中的 Copilot 菜单](images/inline-suggestions/configure-code-completions.png)

1. 选择 **更改补全模型...**，然后从列表中选择一个模型。

> [!NOTE]
> 可用的模型列表可能会随时间变化。如果您是 Copilot 商业或企业用户，您的管理员需要通过在 GitHub.com 上的 [Copilot 政策设置](https://docs.github.com/en/enterprise-cloud@latest/copilot/managing-copilot/managing-github-copilot-in-your-organization/managing-policies-for-copilot-in-your-organization#enabling-copilot-features-in-your-organization) 中选择加入 `编辑器预览功能` 来为您的组织启用某些模型。

## 设置

### 代码补全设置

* `setting(editor.inlineSuggest.enabled)` - 启用或禁用内联补全。

* `setting(editor.inlineSuggest.fontFamily)` - 配置内联补全的字体。

* `setting(editor.inlineSuggest.showToolbar)` - 启用或禁用内联补全的工具栏。

* `setting(editor.inlineSuggest.syntaxHighlightingEnabled)` - 启用或禁用内联补全的语法高亮。

### 下一个编辑建议设置

* `setting(github.copilot.nextEditSuggestions.enabled)` - 启用 Copilot 下一个编辑建议（Copilot NES）。

* `setting(editor.inlineSuggest.edits.codeShifting)` - 配置 Copilot NES 是否可以移动您的代码以显示建议。
* `setting(editor.inlineSuggest.edits.renderSideBySide)` - 配置是否允许Copilot NES在可能的情况下并排显示较大的建议，或者Copilot NES是否应始终在相关代码下方显示较大的建议。

## 下一步

* 通过[Copilot快速入门](/i18n/zh-cn/docs/copilot/getting-started-chat.md)探索关键功能。

* 使用[Copilot聊天](/i18n/zh-cn/docs/copilot/copilot-chat.md)进行AI聊天对话。

* 在YouTube上观看我们的[VS Code Copilot系列](https://www.youtube.com/playlist?list=PLj6YeMhvp2S5_hvBl2SE-7YCHYlLQ0bPt)视频。