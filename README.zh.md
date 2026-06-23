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

## 技术栈

SwiftUI (macOS 14+) · AVFoundation + ScreenCaptureKit（麦克风 + 系统音频）·
Deepgram（语音转文字）· OpenAI（摘要）· Core Data（本地存储）·
Google Calendar 和 Notion API。

## 参与贡献

欢迎贡献——请查看 [CONTRIBUTING.md](CONTRIBUTING.md)。发现 bug 或有想法？
欢迎提交 [issue](https://github.com/fjvalencian/olmo-mac/issues)。

## 许可证

[MIT](LICENSE)。
