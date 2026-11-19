# 好奇熊 app 规则源

> 使用者/爱好者自发整理的规则源合集，**非任何软件的官方仓库**。
>
> 收录好奇熊**支持导入**的各种格式的源，并附上已核对过地址可访问、仍在维护的示例。
>
> 最后核对（订阅地址可用性）：2026-11-19
>
> 📌 条目中的 `source update` 徽章由 shields.io 实时读取源仓库最后提交时间，会随源仓库更新自动变化；它反映的是源仓库活跃度，不代表本页的维护状态。

## 🚀 快速使用

1. 在下面挑一个订阅地址并复制
2. 好奇熊 → **源管理 → 规则源** → 点 **导入规则**（发现页菜单里也有同名入口），把地址粘贴进输入框
3. 按提示预览并确认导入。导入时会**自动识别格式**，不用自己选

> 💡 想长期保持最新：粘贴后点 **加为订阅**，之后在「订阅源」里可 **立即同步**，或打开 **自动更新**。
>
> - 导入方式有三种：粘贴订阅网址 / 粘贴文本 / 选择本地文件。
> - 源不在多，好用的三五个足以。多个订阅里有同一条规则会互相覆盖，覆盖了再导一次就行。

## 🧩 支持导入的格式一览

- **通用规则**（JSON / `fox://` / `eso://`）：好奇熊的原生格式。`fox://作者:规则名@…` 是分享出来的压缩串，`eso://` 是兼容前缀。原样导入，支持漫画、小说、视频、音频四类。见 [一、本仓库](#一本仓库通用规则)。
- **Kazumi**：Kazumi 的动漫规则，支持单条规则文件、规则数组，或规则库的 `index.json`。好奇熊会自动转成视频规则，`index.json` 会自动拉取其中全部规则；XPath 模式和 API 模式都能转，已弃用的规则会被跳过。见 [二、Kazumi](#二kazumi动漫)。
- **Animeko**：Animeko 的数据源订阅（`{schemaVersion, mediaSources[]}`）。「网页选择器」类转成视频规则，JSON 接口类等其它类型会被跳过。见 [三、Animeko](#三animeko动漫)。
- **TVBox**：TVBox 的单仓 / 多仓订阅。苹果CMS 接口类站点转成视频规则，直播源可一并导入；Spider（jar/js/py）类站点不支持，会被跳过。见 [四、TVBox](#四tvbox影视--直播)。
- **ZY-Player**：单个站点的 JSON（含 `api` 与 `name`），自动识别并转成视频规则。见 [五、ZY-Player](#五zy-player)。

## 一、本仓库（通用规则）

### ⭐ 推荐：视频规则，以动漫为主（38 条）

订阅地址（任选一条）：

- **推荐 1**：`https://gh-proxy.org/raw.githubusercontent.com/wbetrue/somesnull/main/pd2.json`
- **推荐 2**：`https://fastly.jsdelivr.net/gh/wbetrue/somesnull@main/pd2.json`
- **GitHub 原始地址**：`https://github.com/wbetrue/somesnull/raw/main/pd2.json`

### 本仓库全部文件

- `pd2.json` — 视频规则，以动漫为主；38 条；日常使用，**首选**
- `simple.json` — 示例：漫画、小说、视频、音频各 1 条；4 条；想看规则怎么写的人
- `eso_source_9_11.json` — 其它软件（eso）的历史规则：漫画 20 / 小说 62 / 视频 23 / 音频 8；113 条；仅供参考，**失效较多**

`simple.json`（能直接写 JS、支持 JSONPath 等，可以看规则结构）：

- `https://gh-proxy.org/raw.githubusercontent.com/wbetrue/somesnull/main/simple.json`
- `https://fastly.jsdelivr.net/gh/wbetrue/somesnull@main/simple.json`
- `https://github.com/wbetrue/somesnull/raw/main/simple.json`

`eso_source_9_11.json`（约 180 KB，网络不好时优先用镜像）：

- `https://gh-proxy.org/raw.githubusercontent.com/wbetrue/somesnull/main/eso_source_9_11.json`
- `https://fastly.jsdelivr.net/gh/wbetrue/somesnull@main/eso_source_9_11.json`
- `https://github.com/wbetrue/somesnull/raw/main/eso_source_9_11.json`

> gh-proxy、jsDelivr 是第三方镜像，可能随时变化；jsDelivr 对分支有缓存，更新会有延迟。打不开就换一条，或用 GitHub 原始地址。

## 二、Kazumi（动漫）

源仓库：[Predidit/KazumiRules](https://github.com/Predidit/KazumiRules) ![source update](https://img.shields.io/github/last-commit/Predidit/KazumiRules?label=source%20update)

- **规则库索引**（18 条，自动拉取全部）
  - 订阅：`https://raw.githubusercontent.com/Predidit/KazumiRules/main/index.json`
- **单条规则示例（普通模式）**
  - 订阅：`https://raw.githubusercontent.com/Predidit/KazumiRules/main/AGE.json`
- **单条规则示例（API 模式）**
  - 订阅：`https://raw.githubusercontent.com/Predidit/KazumiRules/main/giriGiriLove.json`

## 三、Animeko（动漫）

源仓库：[open-ani/animeko](https://github.com/open-ani/animeko) ![source update](https://img.shields.io/github/last-commit/open-ani/animeko?label=source%20update)

- **官方订阅：网页选择器类数据源**
  - 订阅：`https://sub.creamycake.org/v1/css1.json`

- 该订阅共 21 个数据源：20 个网页选择器类可导入，1 个 JSON 接口类会被跳过。
- 订阅里含少量成人向数据源，导入后可以在规则管理里删除。
- Animeko 的另一个 `bt1.json` 全部是 RSS 类，好奇熊不支持，不必导入。

## 四、TVBox（影视 + 直播）

按维护仓库分组（`source update` 徽章显示各仓库最后提交时间）：

- **[1771245847/TvBox](https://github.com/1771245847/TvBox)** ![source update](https://img.shields.io/github/last-commit/1771245847/TvBox?label=source%20update)
  - **单仓**：`https://raw.githubusercontent.com/1771245847/TvBox/master/tvbox.json` — 站点 16 个，其中苹果CMS 接口站 9 个可导入，其余 Spider 类被跳过；直播 1 路
  - **多仓**：`https://raw.githubusercontent.com/1771245847/TvBox/master/tvbox.txt` — 3 条子线路，其中 2 条是第三方动态地址，是否可用以导入预览为准
- **[fswws/tvbox-source](https://github.com/fswws/tvbox-source)** ![source update](https://img.shields.io/github/last-commit/fswws/tvbox-source?label=source%20update)
  - **单仓（直播为主）**：`https://raw.githubusercontent.com/fswws/tvbox-source/main/tvbox.json` — 站点 9 个，其中苹果CMS 接口站 1 个；直播 25 路。每日自动更新
  - **仅直播**：`https://raw.githubusercontent.com/fswws/tvbox-source/main/live.json` — 只有直播源，10 路
- **[qist/tvbox](https://github.com/qist/tvbox)** ![source update](https://img.shields.io/github/last-commit/qist/tvbox?label=source%20update)
  - **大体量单仓**：`https://raw.githubusercontent.com/qist/tvbox/master/jsm.json` — 站点 163 个，其中苹果CMS 接口站约 15 个可导入，其余是 Spider 类；直播 3 路

- `fswws/tvbox-source` 的 jsDelivr 备用地址：`https://fastly.jsdelivr.net/gh/fswws/tvbox-source@main/tvbox.json`
- TVBox 的配置里**大量是 Spider（jar / js / py）类站点**，好奇熊不支持，导入时会被跳过并在预览里写明原因，这是正常现象。所以「站点总数」不等于「能导入的数量」。
- 多仓订阅最多处理前 30 个子源，会自动合并去重。

## 五、ZY-Player

支持**单个站点**的 JSON（含 `api`、`name`），也支持由这种站点组成的数组：

```json
{"key": "mysite", "name": "我的资源站", "api": "https://example.com/api.php/provide/vod/at/xml/"}
```

> ⚠️ ZY-Player 的「一键配置」整包（外层带 `sites`、`iptv`、`analyzes`）暂不支持识别，导入会提示「未识别」。需要的话，请把里面的站点拆成单个站点或数组再导入。
>
> 这类资源站接口老化很快，本页不收录整包列表；想要稳定的苹果CMS 接口站，建议直接用上面 TVBox 的单仓订阅。

## ❓ 常见问题

- **其它软件的源能全部导入吗？** 不能。会被跳过的类型（Spider、RSS、JSON 接口类等）都会在导入预览里列出原因。可能出现不兼容的情况，主要影响「发现」功能，搜索一般不受影响。
- **导入后搜不到、发现页没内容？** 多半是站点本身失效或改版，换一条规则，或到 Issues 反馈。
- **地址打不开 / 超时？** 本仓库的文件有多条线路可换；其它仓库的地址如果 raw 访问慢，可以自己换镜像。
- **提示「未识别」或导入 0 条？** 检查地址是否完整，并且指向 `.json` 文件本身而不是网页。

## 🤝 参与

- 发现规则或订阅失效、有好资源推荐，欢迎提 [Issues](../../issues)
- 会写规则的朋友，欢迎一起维护，保持精简高质

## 📜 声明

本仓库由使用者/爱好者个人整理分享，仅供学习交流，与任何软件官方无关。
规则只是描述如何访问第三方公开网站的配置，本仓库不存储、不提供任何影视、漫画、小说、音乐等内容，相关内容版权归原权利人所有。第三方仓库的内容与更新由其维护者负责。请遵守当地法律法规，支持正版。
