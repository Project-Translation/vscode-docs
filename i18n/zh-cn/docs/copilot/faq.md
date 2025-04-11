---
Order: 15
Area: copilot
TOCTitle: 常见问题
ContentId: e02ded07-6e5a-4f94-b618-434a2c3e8f09
PageTitle: GitHub Copilot 常见问题
DateApproved: 03/05/2025
MetaDescription: 在 Visual Studio Code 中使用 GitHub Copilot 的常见问题。
MetaSocialImage: images/shared/github-copilot-social.png
---
# GitHub Copilot 常见问题

本文解答了在 Visual Studio Code 中使用 GitHub Copilot 的常见问题。

## GitHub Copilot 订阅

### 如何获取 Copilot 订阅？

获取 GitHub Copilot 访问权限有几种不同的方式：

| 用户类型                   | 描述 |
|--------------------------------|-------------|
| 个人                     | <ul><li>设置 [GitHub Copilot Free](https://github.com/github-copilot/signup) 以体验有限的 Copilot 功能，无需订阅。请参阅 [关于 GitHub Copilot Free](https://docs.github.com/en/copilot/managing-copilot/managing-copilot-as-an-individual-subscriber/about-github-copilot-free)。</li><li>注册付费的 GitHub Copilot 订阅以获得无限的补全和聊天互动。你可以[免费试用 GitHub Copilot](https://github.com/github-copilot/signup?ref_cta=Copilot+trial&ref_loc=about+github+copilot&ref_page=docs)，提供一次性 30 天的试用期。</li><li>查看 [为自己设置 GitHub Copilot](https://docs.github.com/en/copilot/setting-up-github-copilot/setting-up-github-copilot-for-yourself) 了解所有选项。 </li></ul> |
| 组织/企业成员 | <ul><li>如果你是拥有 GitHub Copilot 订阅的组织或企业的成员，你可以通过访问 <https://github.com/settings/copilot> 并在“从组织获取 Copilot”下请求访问权限来请求 Copilot 访问权限。</li><li>查看 [为您的组织设置 GitHub Copilot](https://docs.github.com/en/copilot/setting-up-github-copilot/setting-up-github-copilot-for-your-organization) 以启用您的组织的 Copilot。</li></ul> |

### 我达到了补全或聊天互动的限制

你的代码补全和聊天互动的限制每月从你首次注册 Copilot Free 计划的那天开始重置。如果你达到了限制，你可以选择注册[付费订阅](#如何获取-copilot-订阅)，获得无限数量的补全和聊天消息。或者，你可以等到下个月继续免费使用 Copilot。

![在聊天视图、状态栏和标题栏中显示达到 Copilot 聊天消息限制的视觉指示器。](images/faq/copilot-chat-limit-reached.png)

如果只有聊天互动达到了限制，你仍然可以使用 Copilot 进行代码补全。

如果只有代码补全达到了限制，你仍然可以使用 Copilot 进行聊天互动和 Copilot 编辑。

### 我的 Copilot 订阅在 VS Code 中未被检测到

- 要在 Visual Studio Code 中使用 Copilot Chat，你必须使用具有 GitHub Copilot 访问权限的 GitHub ID 登录 Visual Studio Code。如果你的 Copilot 订阅与另一个 GitHub 账户相关联，你可能需要退出当前的 GitHub 账户并使用另一个账户登录。在活动栏中使用 **Accounts** 菜单退出当前的 GitHub 账户。

- 验证你的 Copilot 订阅在 [GitHub Copilot 设置](https://github.com/settings/copilot) 中仍然有效。

### 如何为 Copilot 切换账户
要切换到另一个 GitHub 账户以使用 Copilot：

1. 从活动栏打开扩展视图（或使用 `kb(workbench.view.extensions)`），并在搜索框中输入 *GitHub Copilot*。

    ![VS Code 中的扩展视图，显示 GitHub Copilot 扩展。](images/faq/copilot-extensions.png)

    > [!NOTE]
    > 有两个 Copilot 扩展：GitHub Copilot 和 GitHub Copilot Chat。

1. 对于 **GitHub Copilot** 扩展，选择齿轮图标，然后选择 **账户偏好设置**。

    ![VS Code 中的账户菜单，显示注销当前 GitHub 账户的选项。](images/faq/extension-account-preferences.png)

1. 在账户偏好设置快速选择中，选择现有账户或选择 **使用新账户...** 以使用不同的 GitHub 账户登录。

    ![VS Code 中的账户菜单，显示使用 GitHub 登录以使用 GitHub Copilot 的选项。](images/faq/account-preferences-quick-pick.png)

1. 对 **GitHub Copilot Chat** 扩展重复这些步骤。

## 常规

### Copilot 的网络和防火墙配置

- 如果您或您的组织使用了如防火墙或代理服务器等安全措施，可能需要将某些域 URL 加入“允许列表”并打开特定的端口和协议。了解更多关于[为 GitHub Copilot 排查防火墙设置](https://docs.github.com/en/copilot/troubleshooting-github-copilot/troubleshooting-firewall-settings-for-github-copilot)的信息。

- 如果您在公司设备上工作并连接到公司网络，您可能通过 VPN 或 HTTP 代理服务器连接到互联网。在某些情况下，这些类型的网络设置可能会阻止 GitHub Copilot 连接到 GitHub 的服务器。了解更多关于[为 GitHub Copilot 排查网络错误](https://docs.github.com/en/copilot/troubleshooting-github-copilot/troubleshooting-network-errors-for-github-copilot)的信息。

### 如何为 Copilot 提供反馈？

如果您想对 Copilot 功能（包括内联建议和聊天）提供反馈，您可以在 [vscode-copilot-release](https://github.com/microsoft/vscode-copilot-release/issues) 存储库中创建问题。

如果您在报告问题时，可以包含来自 [GitHub Copilot 日志](#view-logs-for-github-copilot-in-vs-code) 的信息，这会很有帮助。

### 在 VS Code 中查看 GitHub Copilot 日志

GitHub Copilot 扩展的日志文件存储在 Visual Studio Code 扩展的标准日志位置。日志文件对于诊断连接问题很有用。

使用 **切换输出** 命令 (`kb(workbench.action.output.toggleOutput)`) 并在下拉菜单中选择 **GitHub Copilot** 或 **GitHub Copilot Chat**。

### 是否有 Copilot 扩展的预发布版本？

是的，您可以切换到 Copilot 扩展的预发布（每晚）版本，以尝试最新的功能和修复。从扩展视图中，右键点击或选择齿轮图标调出上下文菜单，然后选择 **切换到预发布版本**：

![扩展视图上下文菜单，显示切换到预发布版本选项](images/faq/switch-to-pre-release.png)

您可以通过扩展详情中的“预发布”徽章来判断是否在运行预发布版本：
## Copilot代码补全

### 如何启用/禁用Copilot？

您可以从状态栏暂时停用Copilot补全。系统会提示您是希望全局禁用Copilot（对所有代码）还是仅禁用当前活动编辑器中检测到的编程语言（例如，Python）。

### 编辑器中的内联补全不工作

- 验证[GitHub Copilot是否未被全局或针对此语言禁用](#如何启用禁用copilot)
- 验证您的[GitHub Copilot订阅是否处于活动状态并被检测到](#我的copilot订阅在vs-code中未被检测到)
- 验证您的[网络设置](#copilot的网络和防火墙配置)是否配置为允许连接到GitHub Copilot。
- 验证您是否未达到本月的补全限制，使用的是[Copilot免费计划](https://docs.github.com/copilot/managing-copilot/managing-copilot-as-an-individual-subscriber/about-github-copilot-free)。

## Copilot聊天

### Copilot聊天功能对我不起作用？

如果Copilot聊天不起作用，请检查以下每个要求：

- 确保您使用的是最新版本的Visual Studio Code（运行**代码：检查更新**）。
- 确保您拥有最新版本的[GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)和[GitHub Copilot聊天](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat)扩展。
- 您的GitHub账户必须在VS Code中登录，并且拥有活动的Copilot订阅。检查您的[Copilot订阅](https://github.com/settings/copilot)。
- 验证您是否未达到本月的聊天互动限制，使用的是[Copilot免费计划](https://docs.github.com/copilot/managing-copilot/managing-copilot-as-an-individual-subscriber/about-github-copilot-free)。

### 为什么我的Copilot聊天扩展被阻止？

如果您收到消息称某个扩展被阻止使用Copilot聊天，则该扩展很可能由于检测到来自该特定扩展的滥用模式而被禁用。遇到此问题时，请联系扩展的发布者。您可以在Visual Studio Marketplace的扩展详细信息页面上找到发布者信息。

## 其他资源

- [GitHub Copilot信任中心](https://resources.github.com/copilot-trust-center/)
- [GitHub Copilot常见问题解答](https://github.com/features/copilot#faq)在GitHub文档中