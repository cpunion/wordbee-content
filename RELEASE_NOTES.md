# content-2026.09.05

首批可选内容包含 4 个独立词典/例句包和 1 个原创三词格式示例，兼容 `.wordbee` v1。全部无真人录音、媒体 URL、个人学习数据或账号信息。

| 下载文件 | 内容 | 词典词条 | 文件大小 |
| --- | --- | ---: | ---: |
| `open-freedict-eng-zho-2025.11.23.r2.wordbee` | FreeDict / WikDict 英汉释义 | 24,786 | 2,260,437 字节 |
| `open-oewn-2025.r2.wordbee` | Open English WordNet 英文释义、例句及部分音标 | 127,251 | 8,531,521 字节 |
| `open-cmudict-74790861.r2.wordbee` | CMU ARPABET 与近似美式宽式 IPA | 125,955 | 2,081,267 字节 |
| `open-tatoeba-cc0-2026-09-05.r1.wordbee` | Tatoeba English CC0 精选例句索引，可选 | 32,353 | 4,307,122 字节 |
| `original-three-words.wordbee` | 原创花园词表及配套三词示例资料 | 3 | 861 字节 |

## 获取、校验和导入

在 [GitHub Release](https://github.com/cpunion/wordbee-content/releases/tag/content-2026.09.05) 下载对应文件，或使用 [catalog.json](catalog.json) 中的 `mirrorURL` 服务器镜像。两个下载地址的文件大小和 SHA256 应完全相同。

下载所有 5 个包和 `SHA256SUMS.txt` 到同一个目录后可校验：

```sh
# macOS
shasum -a 256 -c SHA256SUMS.txt

# Linux
sha256sum -c SHA256SUMS.txt
```

只下载其中一个包时，可计算该文件的 SHA256，与 `SHA256SUMS.txt` 对应行或 `catalog.json` 的 `sha256` 比较；不需要为校验下载其他包。

将文件保存到 iPhone/iPad 的“文件”，交给支持 `.wordbee` 的 WordBee 导入，也可通过 Mac AirDrop。导入为异步任务；纯词典包不会创建学习词表、计划或修改既有掌握状态。原创示例包含演示词表，导入会创建“花园 → 第一天”两级内容以及配套示例词典。

## 内容和许可边界

- FreeDict：该 eng-zho 版本为 CC BY-SA 3.0；转换数据保留同许可，附原 COPYING。
- OEWN：CC BY 4.0 和 Princeton WordNet 许可并存，附两份原始声明；不要只保留仓库 MIT 文档许可。
- CMU：附完整原始 BSD-style 通知。IPA 为 ARPABET 的近似宽式转换，不推断音节和重音位置，不是录音，也不是经过人工校对的完整发音指南。发声可以使用 App 的 Apple TTS。
- Tatoeba：只使用英文 CC0 专用导出。完整扫描 41,503 行后精选 25,012 条独立句子，每个索引词最多 3 句；无释义、翻译、录音，不做词形归一，不是完整句库。用户可主动选择并排在主要词典之后，用来补缺例句。
- 原创示例：三词释义及例句为原创 CC0 格式演示，不是权威词典。

社区词典及例句均未通过儿童适龄审核；Tatoeba 是可选内容，不默认启用。逐句来源 metadata 保存在包中，不代表 App 已有逐句来源按钮。详细来源和处理损失见 [SOURCES.md](SOURCES.md)。

本次不发布：任何私人录音或资料、未清权的 ECDICT 聚合数据、来源/选词编排权限未明确的赛事词表。Kaikki 大型分卷不属于此基础包目录；仅在单独校验、审查完成后作为进阶内容另行提供，解析器存在不等于数据已经发布。

## 包检查

这 5 个文件已逐一核对实际大小、SHA256、ZIP CRC、manifest 身份及词条数量；开放词典包的原始许可文件完整保留。`.r2` 是此批包的构建修订号，与上游源版本区分记录在目录中。下载源文件的 hash 与转换后 `.wordbee` 的 hash 是不同对象，不应混用。
