---
Order: 3
Area: copilot
TOCTitle: 设置
ContentId: 37fd3bd2-4209-49f6-bec5-c544d6b1b289
PageTitle: 在 Visual Studio 中设置 GitHub Copilot
DateApproved: 03/05/2025
MetaDescription: 访问您的 GitHub Copilot 订阅并在 Visual Studio 中设置 GitHub Copilot。
MetaSocialImage: images/shared/github-copilot-social.png
---
# 在 VS Code 中设置 GitHub Copilot

本指南将引导您在 Visual Studio Code 中设置 GitHub Copilot。要在 VS Code 中使用 Copilot，您需要通过您的 GitHub 账户访问 GitHub Copilot，并在 VS Code 中安装 Copilot 扩展。

> [!TIP]
> 如果您还没有 Copilot 订阅，您可以通过注册 [Copilot 免费计划](https://github.com/github-copilot/signup) 来免费使用 Copilot，并获得每月的完成和聊天交互限制。

## 获取 GitHub Copilot 的访问权限

获取 GitHub Copilot 访问权限的方法有几种：

| 用户类型                   | 描述 |
|--------------------------------|-------------|
| 个人                     | <ul><li>设置 [GitHub Copilot 免费版](https://github.com/github-copilot/signup) 以获得无需订阅的有限 Copilot 体验。请参阅 [关于 GitHub Copilot 免费版](https://docs.github.com/en/copilot/managing-copilot/managing-copilot-as-an-individual-subscriber/about-github-copilot-free)。</li><li>注册付费的 GitHub Copilot 订阅以获得无限的完成和聊天交互。您可以 [免费试用 GitHub Copilot](https://github.com/github-copilot/signup?ref_cta=Copilot+trial&ref_loc=about+github+copilot&ref_page=docs)，提供一次性 30 天的试用期。</li><li>请参阅 [为自己设置 GitHub Copilot](https://docs.github.com/en/copilot/setting-up-github-copilot/setting-up-github-copilot-for-yourself) 以了解所有选项。 </li></ul> |
| 组织/企业成员 | <ul><li>如果您是拥有 GitHub Copilot 订阅的组织或企业的成员，您可以通过访问 <https://github.com/settings/copilot> 并在“从组织获取 Copilot”下请求访问权限来请求 Copilot 的访问权限。</li><li>请参阅 [为您的组织设置 GitHub Copilot](https://docs.github.com/en/copilot/setting-up-github-copilot/setting-up-github-copilot-for-your-organization) 以启用您的组织的 Copilot。</li></ul> |

## 在 VS Code 中设置 Copilot

VS Code 提供了一种简化的体验来设置 GitHub Copilot。这将安装 GitHub Copilot 扩展并登录到您的 GitHub 账户。如果您还没有 Copilot 订阅，它将激活 [Copilot 免费计划](https://github.com/github-copilot/signup)。

1. 从 VS Code 标题栏中的 Copilot 菜单或从命令面板 (`kb(workbench.action.showCommands)`) 中选择 **免费使用 AI 功能与 Copilot...**

    ![VS Code 标题栏中的 Copilot 菜单，显示免费使用 AI 功能与 Copilot 的选项。](images/setup/copilot-menu-use-ai-features.png)

    > [!TIP]
    > 您还可以通过使用键盘快捷键 `kb(workbench.action.chat.open)` 或使用 **打开聊天** 命令直接打开聊天视图。

1. 选择 **登录以免费使用 Copilot** 以登录到您的 GitHub 账户。此步骤还将安装 Copilot 扩展。

    ![聊天视图显示 Copilot 消息和一个按钮，允许您登录以使用 Copilot。](images/setup/copilot-chat-view-new-user.png)
如果您已经拥有 Copilot 订阅，现在可以在 VS Code 中开始使用 Copilot。

1. 如果您尚未拥有 Copilot 订阅，请按照浏览器中的步骤注册 Copilot 免费计划

    > [!IMPORTANT]
    > 您的 GitHub Copilot 免费版本的遥测功能当前已启用。默认情况下，允许匹配公共代码的代码建议，包括 VS Code 和 <github.com> 体验中的代码引用。您可以通过在 VS Code 中将 `setting(telemetry.telemetryLevel)` 设置为 `off` 来选择退出遥测数据收集，或者您可以在 [Copilot 设置](https://github.com/settings/copilot) 中调整遥测和代码建议设置。

## 在 VS Code 中开始使用 Copilot

在您登录 GitHub 账户并获得 Copilot 访问权限后，开始在 VS Code 中探索 AI 驱动的编码。

1. 验证聊天视图 (`kb(workbench.action.chat.open)`) 是否显示，并且您可以在聊天输入框中输入提示。

    ![聊天视图在次要侧边栏中打开，并显示 Copilot 欢迎消息。](images/setup/copilot-chat-view-welcome.png)

    请注意，您可以选择多个语言模型与 Copilot 一起使用。

1. 继续使用 [Copilot 快速入门](/i18n/zh-cn/docs/copilot/getting-started.md) 探索 VS Code 中 Copilot 的关键功能。

## 在 VS Code 中手动设置 GitHub Copilot

要在 VS Code 中手动设置 GitHub Copilot，请执行以下步骤：

1. 在 VS Code 中安装 GitHub Copilot 扩展

    > <a class="install-extension-btn" href="vscode:extension/GitHub.copilot?referrer=docs-copilot-setup">安装 GitHub Copilot 扩展</a>

    您还可以打开扩展视图并搜索 *GitHub Copilot* 来安装扩展。

    > [!NOTE]
    > 当您安装 GitHub Copilot 扩展时，[GitHub Copilot Chat](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat) 扩展也会被安装。

1. 从 VS Code 登录 Copilot

    通过在命令面板 (`kb(workbench.action.showCommands)`) 中输入 **GitHub Copilot: 登录** 来登录您的 GitHub 账户

    ![VS Code 中的命令面板，显示登录 GitHub Copilot 的选项。](images/setup/command-palette-copilot-sign-in.png)

## 使用不同的 GitHub 账户使用 Copilot

如果您的 Copilot 订阅与另一个 GitHub 账户相关联，请在 VS Code 中退出您的 GitHub 账户，并使用另一个账户登录。

1. 在活动栏中选择 **账户** 菜单，然后为您当前登录的 Copilot 账户选择 **退出**。

    ![VS Code 中的账户菜单，显示退出当前 GitHub 账户的选项。](images/setup/vscode-accounts-menu-signout.png)

1. 通过在命令面板 (`kb(workbench.action.showCommands)`) 中输入 **GitHub Copilot: 登录** 来登录您的 GitHub 账户

    或者，通过在活动栏中选择 **账户** 菜单，然后选择 **使用 GitHub 登录以使用 GitHub Copilot** 在 VS Code 中登录 GitHub。

    ![VS Code 中的账户菜单，显示使用 GitHub 登录以使用 GitHub Copilot 的选项。](images/setup/vscode-accounts-menu.png)

## 下一步
* 继续阅读 [Copilot 快速入门](/i18n/zh-cn/docs/copilot/getting-started.md)，了解 VS Code 中 Copilot 的主要功能。

* 查看我们的 [Copilot 速查表](/i18n/zh-cn/docs/copilot/copilot-vscode-features.md)，了解 Copilot 的主要命令和快捷方式概览。