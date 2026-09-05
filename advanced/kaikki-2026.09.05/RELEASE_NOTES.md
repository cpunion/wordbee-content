# Kaikki 英语文本：进阶技术分卷

版本：`kaikki-2026.09.05`；内容修订：`2026.08.05-raw.2026.08.28.4c27d202e875.r2`。

本系列是 64 个 **技术分发包**，不是普通用户的默认安装目录。不要要求用户逐个安装、排序 64 个词典。约 135 万词条的整库 SwiftData 保存、iPad 内存及完整 App 交互性能尚未完成验收；不能因分卷通过格式检查而默认启用全部大库。

基础的 FreeDict、OEWN、CMU 与可选 Tatoeba 继续使用[首批内容版本](https://github.com/cpunion/wordbee-content/releases/download/content-2026.09.05/RELEASE_NOTES.md)。本系列单独发布，不改变基础版本的 5 个文件或校验和。

## 文件和获取

| 项目 | 数量 / 大小 |
| --- | ---: |
| `.wordbee` 分卷 | 64 |
| 可表示的英文原始候选 | 1,487,171 |
| 合并后的原生词条身份 | 1,347,885 |
| 明示排除的符号记录 | 468 |
| 分卷压缩大小合计 | 109,219,455 字节 |
| 全部 manifest 合计 | 689,402,030 字节 |
| 最大单卷 manifest | 10,934,709 字节 |
| 最大单卷词条数 | 21,368 |
| 真人音频、音频 URL、例句 | 0 |

每个文件的名称、词数、大小、SHA256、GitHub 附件、CDN 镜像与源站备选地址见 [catalog.json](https://github.com/cpunion/wordbee-content/releases/download/kaikki-2026.09.05/catalog.json)。发布标签为 [kaikki-2026.09.05](https://github.com/cpunion/wordbee-content/releases/tag/kaikki-2026.09.05)。`mirrorURL` 指向 `https://wordbee-cdn.appyun.io/wordbee/content/kaikki-2026.09.05/` 下对应文件名；`originURL` 保留 `https://img.appyun.io/wordbee/content/kaikki-2026.09.05/` 作为直接源站备选，后者不是 CDN。App API 独立位于 `https://workbee.appyun.io`（标准 HTTPS 443）。

2026-09-05，本系列 64 卷与基础版本 5 包合计 **69 包、126,400,663 字节**均已从 CDN 逐一完整下载，实际字节数和 SHA256 全部匹配发布清单。缓存/HTTP 行为另做代表性验证：基础版本的原创示例包两次 GET 均为 861 字节且 SHA256 正确，`MISS → HIT`、第二次未回源，返回一年 `immutable` 策略；HEAD 200、Range 206/16 字节及 metadata 条件请求 304 也已实证。目录通过 `verifiedOn` 和 `onlineValidation` 区分全量文件完整性与代表性缓存检查；**不声称 64 卷均测得缓存 HIT，更不是完整 Kaikki 的 SwiftData 导入、设备内存或交互性能验收**。三个下载渠道对应同一文件；此次地址调整不改变任何分卷文件或分卷 SHA256，仅更新发布 metadata 及其校验值。

下载完整系列时须核验 64 卷的连续分区、版本、源快照及文件 hash，不能把单卷当作整个来源覆盖旧数据。`SHA256SUMS.txt` 用于核验实际下载的文件；只下载一部分时对照相应行计算 SHA256，不要把缺少其他文件误解为该文件损坏。

```sh
# 完整下载所列文件后，在对应目录执行；macOS
shasum -a 256 -c SHA256SUMS.txt
```

## 原始来源和许可

只使用 [Kaikki 官方 raw Wiktextract 数据](https://kaikki.org/dictionary/rawdata.html)，从原始多语言记录中选择 `lang_code=en`；没有使用可能混合其他资料的 postprocessed 下载。

- 官方源：`https://kaikki.org/dictionary/raw-wiktextract-data.jsonl.gz`
- 原始压缩文件大小：2,826,623,319 字节。
- **原始压缩文件** SHA256：`4c27d202e875550c2cc7ea93a4d21ddf80440e5030606d3edbb8b0e65dc64006`。
- Wiktionary dump：2026-08-05；Wiktextract 提取：2026-08-28。
- 下载响应 Last-Modified：`Fri, 28 Aug 2026 10:44:19 GMT`。

此源 hash 不等于任何一个转换后 `.wordbee` 包的 hash；两类对象分别记录。原始 2.8 GB 下载不作为本次公开 Release 附件。

采用 [Wiktionary 版权说明](https://en.wiktionary.org/wiki/Wiktionary:Copyrights) 中适用于原创词典文字的 **CC BY-SA 4.0** 路径。署名 Wiktionary contributors，以及 Wiktextract / Tatu Ylonen 与贡献者；说明格式转换，同一规范身份的不同义项及显示变体被合并。改编词典数据继续使用 CC BY-SA 4.0，不能以本仓库文档的 MIT 许可替换。

每卷均附两份完整来源通知：

- `assets/licenses/1-CC-BY-SA-4.0-legalcode.txt`；SHA256 `28a9529c7d0bb4dc51f4bf5c116a3d16ef247a052f7591466768ddf563fd1cf5`。
- `assets/licenses/2-Wiktionary-Copyrights.html`；SHA256 `b48a0c51776391ab168faf297818ad188a4c74b749e331c84a3c8ad0f7f673f5`。

每词保存对应 Wiktionary 页面；其他义项和大小写的原页面保留在 metadata，便于追溯作者历史。文字许可不推导为音频、图片、引文或其他媒体许可，因此 **所有例句、引文、媒体文件及音频链接均排除**。

## 转换和排除规则

- 固定系列 ID：`dictionary-kaikki-sha256-64-v1`。规范词条身份计算 SHA256，摘要首字节前 6 位选择 64 个桶；相同身份的义项和变体位于同卷，不按字母或难度分课。
- 分卷 ID 为 `dictionary-kaikki-shard-00` 至 `dictionary-kaikki-shard-3f`，内部词典 ID 为 `kaikki-shard-00` 至 `kaikki-shard-3f`。未来改变分桶算法/数量需要单独设计迁移，不能假设这些 ID 可直接复用。
- 保留英文释义、接受拼写、词源、全部 US/UK IPA 变体和原始地区 IPA 标签、词形及同反义词文字 metadata；r2 补全了多个 IPA 变体，不只留下第一个。当前 v1 App 不保证展示所有扩展字段。
- 468 条纯符号、盲文或标点记录在 App 规范化后为空，比如 `!`、`&`、`♥`、`⠁`，详见 [excluded-spelling-records.jsonl](https://github.com/cpunion/wordbee-content/releases/download/kaikki-2026.09.05/excluded-spelling-records.jsonl)。它们没有被导入，不能称为零损失全源复制；没有普通英文词或短语因此被截断。
- 排除记录清单 SHA256：`45069199b20a36e69bd5bdbfab516846039913af3ca68ca478a366cfd9bfd7cd`。`lineNumber` 是原始数据行号，不是本地路径或用户信息。
- 通用词典包含罕用、过时、成人及敏感词汇，不是分龄审核后的儿童课程。许可核对和格式校验不等于每条释义正确；地区 IPA 仍有 neutral fallback 映射，默认作为权威音标前需要单独质量测试。

## 已验证与未验证

[validation-native.json](https://github.com/cpunion/wordbee-content/releases/download/kaikki-2026.09.05/validation-native.json) 是去除本地环境信息后的原生验收摘要：在 macOS 编译运行未修改的 App `LearningContentPackageArchive` 与 `VocabularyIdentity`，校验 64 卷、1,347,885 个原生身份唯一性、128 份许可资产 CRC、各包 SHA256、零例句和音频。

发布清单另经独立全卷审计，复核 ZIP CRC、实际字节数、文件 hash、manifest 身份/版本/词数、来源和通知 hash、无本机私有路径、无录音或例句字段。实际保留 237,480 个 US/UK IPA 数组值及 283,943 个原始带标签的音标记录。

这些验证的边界是 **归档读取、解码、身份与安全预检**，不是全系列写入 SwiftData 的验收。整库下载、设备落盘耗时、峰值内存、恢复/取消与交互可用性仍是默认启用前的门槛。本 Release 不把未完成项描述为已完成。
