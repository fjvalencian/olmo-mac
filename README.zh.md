<p align="center">
  <img src="assets/olmo-icon.png" width="120" alt="Olmo" />
</p>

<p align="center"><a href="README.md">English</a> · <a href="README.es.md">Español</a> · <a href="README.ja.md">日本語</a> · <b>中文</b></p>

# Olmo

**一款注重隐私的开源 macOS AI 会议笔记应用。**

Olmo 会录制你的会议和通话，实时转录，并将其转化为干净、可编辑的 Markdown
摘要——全部在你自己的 Mac 上、使用你自己的 API 密钥运行。没有机器人加入你的
通话，你的笔记始终属于你。

## 功能

- **通话双方的声音。** 同时采集你的麦克风和对方的声音（系统音频），无论是否
  佩戴耳机。
- **没有机器人。** 不会有任何程序加入你的会议——录音都在你的 Mac 本地完成。
- **实时转录**和 **AI 摘要**，生成可编辑、可搜索、可保存的 Markdown。
- **使用你自己的密钥（BYOK）。** 使用你自己的 Deepgram 和 OpenAI 密钥；你的
  音频和笔记不会经过我们的服务器。
- **同步到 Notion。** 每条摘要都会自动导出到一个 Notion 页面——一次会议一个
  页面，绝不重复。
- **Google 日历。** 在日历里查看你的会议，直接开始记笔记。

## 安装

- 从 [Releases](https://github.com/fjvalencian/olmo-mac/releases) 页面**下载**
  最新的 `Olmo.dmg`。需要 **macOS 14 或更高版本**。
- **网站:** <https://fjvalencian.github.io/olmo-mac/>

### 从源码构建

环境要求：macOS 14+、Xcode 15+ 和
[XcodeGen](https://github.com/yonaskolb/XcodeGen)（`brew install xcodegen`）。

```bash
git clone https://github.com/fjvalencian/olmo-mac.git
cd olmo-mac/Olmo-MacOS
xcodegen generate
open Olmo-MacOS.xcodeproj   # 然后 ⌘R
```


## API 密钥（BYOK）

Olmo 采用 **自带密钥（BYOK）**：你连接自己的 Deepgram 和 OpenAI 账户，
你的音频和笔记会直接发送到 *你* 掌控的服务——绝不经过我们的服务器。

### 为什么选择 Deepgram？

Olmo 会**在你说话的同时实时**转录，因此需要快速、准确的实时语音转文字。
Deepgram 正是为此而生：低延迟流式传输、出色的准确度和多语言支持，以及
简单的**按量付费**模式，无需订阅。新账户可获得 **$200 免费额度**，无需信用卡——
在开始付费之前足够开很多场会议。

> 这 $200 是**注册时一次性赠送的额度**（注册一年后过期），并非每月发放。
> 用完之后，你只需按转录用量以按量付费的价格付费。

**获取密钥：**

1. 在 [console.deepgram.com/signup](https://console.deepgram.com/signup) 注册——免费、无需信用卡。
2. 在控制台进入 **API Keys → Create a New API Key**，复制密钥。
3. 在 Olmo 中打开 **设置 → API 密钥**，粘贴到 Deepgram 字段。

**OpenAI 密钥**也以同样方式设置（用于生成 AI 摘要）。


## 隐私与安全

Olmo 的设计宗旨是让你的对话始终属于你。

- **本地优先。** 你的录音和笔记保存在 **你的 Mac 上**（Core Data），不会上传到任何 Olmo 服务器。
- **没有 Olmo 中间人（BYOK）。** 转录和摘要使用 **你自己的** Deepgram 和 OpenAI 密钥——这些数据发送到你在这些服务上的 *自己的* 账户，不经过我们的服务器。
- **无追踪。** 没有任何第三方分析、遥测或广告 SDK。Olmo 不会"回传数据"。
- **密钥安全保存。** 你的 API 密钥和令牌保存在 **macOS 钥匙串**（Keychain）中（仅限本机，不进入 iCloud）。
- **集成需主动开启。** 只有当 *你* 连接 Notion 和 Google 日历时，才会用 *你的* 令牌/账户、为你授权的操作进行通信。
- **权限由你掌控。** Olmo 会请求麦克风（你的声音）和屏幕录制（用于采集对方的系统音频）。你在 macOS 中授权，并可随时撤销。
- **开源。** 不必只听我们说——代码就在这里，你可以自行阅读和验证。

> 诚实说明：为了把语音转成文字、把文字转成摘要，音频和转录会使用你自己的密钥发送到你选择的服务（Deepgram、OpenAI）。Olmo 无法完全在本地完成这一步——但这是 *你的* 账户和 *你的* 数据，且不会有任何内容保存在 Olmo 服务器上。

## 技术栈

SwiftUI (macOS 14+) · AVFoundation + ScreenCaptureKit（麦克风 + 系统音频）·
Deepgram（语音转文字）· OpenAI（摘要）· Core Data（本地存储）·
Google Calendar 和 Notion API。

## 参与贡献

欢迎贡献——请查看 [CONTRIBUTING.md](CONTRIBUTING.md)。发现 bug 或有想法？
欢迎提交 [issue](https://github.com/fjvalencian/olmo-mac/issues)。

## 许可证

[MIT](LICENSE)。
