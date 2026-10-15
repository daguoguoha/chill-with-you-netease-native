# 开源项目与第三方声明

本文件区分实际复用的上游组件、外部运行依赖和仅由游戏提供的程序集引用。本联网一键部署包只预先包含本适配的 ChillNeteasePlaylist.dll、C# 源码、安装器源码、构建脚本和文档。BepInEx、ChillNetease.dll 与 QRCoder.dll 由 Install.ps1 在用户安装时从各自官方发布地址下载并校验；未随此 ZIP 预先分发。

| 项目 | 用途 | 对应来源/版本 | 许可证 |
|---|---|---|---|
| [ChillPatcher](https://github.com/BeyondtheApex/ChillPatcher) / ChillNetease | 网易云原生桥接，账号、歌单和音源请求；上游实现参考 | [3.0.3，commit 4800dd2ac005c3c70e1bf1bc732e00f00556ec48](https://github.com/BeyondtheApex/ChillPatcher/tree/4800dd2ac005c3c70e1bf1bc732e00f00556ec48/NativePlugins/netease_bridge) | GPL-3.0-or-later；保留 ChillPatcher Contributors 版权声明 |
| [go-musicfox](https://github.com/go-musicfox/go-musicfox) | 上述原生桥接使用的网易云逻辑 | 外部 DLL 内嵌构建记录的基础 commit [6a7a4a5b7b14](https://github.com/go-musicfox/go-musicfox/tree/6a7a4a5b7b14)，含上游桥接构建改动 | 所核对的这个历史 commit 的 LICENSE 为 MIT，原文保存在 licenses/go-musicfox-LICENSE.txt；不要用当前主分支许可证代替历史版本判断 |
| [netease-music](https://github.com/go-musicfox/netease-music) | 原生桥接间接使用的网易云 API 包 | [v1.5.0](https://github.com/go-musicfox/netease-music/tree/v1.5.0) | MIT，保留该版本 LICENSE.md 原文 |
| [BepInEx](https://github.com/BepInEx/BepInEx) | Unity 插件加载框架 | [v5.4.23.5](https://github.com/BepInEx/BepInEx/releases/tag/v5.4.23.5) | MIT，Copyright (c) 2018 Bepis |
| [HarmonyX](https://github.com/BepInEx/HarmonyX) | 通过 BepInEx 提供的 Harmony API 修改运行时音乐方法 | 使用用户 BepInEx 安装中的 0Harmony.dll | MIT，Copyright (c) 2020 BepInEx；若重分发特定二进制，另保留其准确版本及继承的版权声明 |
| [QRCoder](https://github.com/codebude/QRCoder) | 本地生成登录二维码 | [v1.4.3](https://github.com/codebude/QRCoder/tree/v1.4.3) | MIT，Copyright (c) 2013-2018 Raffael Herrmann |

本地适配新增了原生歌单下拉入口、曲目注册、音源按需加载、原生播放控件接入、加载取消处理、有限音频缓存及存档过滤，并保留此前 F8 账号管理界面。以上新增适配不代表本项目对上游网易云桥接和相关依赖享有原创版权。

Unity、游戏 Assembly-CSharp、TextMeshPro、UniTask、R3、ObservableCollections、Newtonsoft.Json 等仅从用户已安装游戏中引用，未复制到此发行包。不应将游戏的 Managed 目录或游戏资源提交到本仓库。

UPSTREAM_NATIVE_BUILDINFO.txt 记录外部 ChillNetease.dll 内嵌的 Go 模块版本，供以后制作完整版时继续核对。它不是完整的第三方许可证清单，也不证明该二进制已完成独立再分发审计。

若后续改为在发行包内直接附带 ChillNetease.dll、BepInEx 全框架或其他依赖，需要另外提供所分发版本要求的完整对应源码、构建说明及转依赖许可证，不能只留下本文件的项目链接。GPL 的源码提供方式参见 [GNU 官方 FAQ](https://www.gnu.org/licenses/gpl-faq.en.html#AnonFTPAndSendSources)。

本项目使用自己的 GPL-3.0-or-later 声明；完整 GPLv3 正文见根目录 LICENSE，上游声明和 MIT 原文见 licenses/。署名和许可证文本均应随源码及适用的发行包保留。

安装器新增功能包括 Steam 库发现、依赖下载与 SHA256 校验、既有加载器检查、更新备份、安装失败回退及安全停用，采用 GPL-3.0-or-later。
