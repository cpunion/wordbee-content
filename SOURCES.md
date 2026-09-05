# 来源与许可

## FreeDict / WikDict eng-zho 2025.11.23

- 官方源：https://download.freedict.org/dictionaries/eng-zho/2025.11.23/
- 许可：CC BY-SA 3.0 Unported，以该版本 TEI header 和同包 COPYING 为准。
- 署名：Karl Bartel；FreeDict / WikDict；Wiktionary contributors via DBnary。
- 转换：26,660 个原始条目按规范拼写合并成 24,786 个词典条目，保留多义项和原显示变体；无媒体。
- 再分发转换后的词典须保留来源及相同许可；不能以本仓库 MIT 取代数据许可。

## Open English WordNet 2025

- 官方源：https://github.com/globalwordnet/english-wordnet
- 许可：https://github.com/globalwordnet/english-wordnet/blob/main/LICENSE.md
- 底层声明：https://wordnet.princeton.edu/license-and-commercial-use
- 署名：Open English WordNet contributors；Princeton University WordNet contributors。
- 包含原始 LICENSE.md 和 WNDB_License.txt，CC BY 4.0 与底层通知均保留。
- 转换：128,009 个上游条目合并为 127,251 个规范词条，多条释义及例句保留，无媒体。

## CMUdict

- 官方源：https://github.com/cmusphinx/cmudict
- 固定提交：74790861f652b15e4ac49015a90074ad62a27690。
- 许可：https://github.com/cmusphinx/cmudict/blob/74790861f652b15e4ac49015a90074ad62a27690/LICENSE
- 保留完整 Carnegie Mellon University 版权、条件和免责声明。
- 转换：保留 ARPABET，并按明确映射生成无音节/重音推断的近似宽式 IPA；125,955 个词条，无录音。

## 原创示例

三个词为 seed、grow、look after，简短释义及例句为原创，采用 CC0 1.0。该示例不是完整词典或儿童适龄资料的背书。

## Tatoeba English CC0 精选例句索引

- 官方英文 CC0 专用下载：https://downloads.tatoeba.org/exports/per_language/eng/eng_sentences_CC0.tsv.bz2
- 格式与许可说明：https://tatoeba.org/en/downloads
- CC0 范围说明：https://en.wiki.tatoeba.org/articles/show/cc0-contributions
- 许可：CC0 1.0 Universal，https://creativecommons.org/publicdomain/zero/1.0/；完整 legal code 原样存于包内。
- 署名及转换说明：Tatoeba contributors；英文 CC0-only 导出转换为按字面 token 查询的精选例句索引。不包含翻译或音频，也不从原句许可推断这些资料的许可。
- 实际快照：HTTP `Last-Modified: Sat, 05 Sep 2026 06:35:09 GMT`；读取时间 `2026-09-05T13:24:30Z`。上游 URL 每周更新，日期以实际下载记录为准。
- 原始 `.bz2` 裸 SHA256：`489556f5ed662d97f1350ef81aa4b0fc430ea32c0c98853020666b055ee4b40c`；CC0 许可文本 SHA256：`a2010f343487d3f7618affe54f789f5487602331c0a8d03f49e9a7c547cf0499`。
- 完整扫描 41,503 行英文语料，排除字符长度不合要求的 2,608 行、token 数不符的 1,723 行、控制字符行 1 行；37,171 行合格。
- 每词最多保留 3 句，按“与 10 token 的距离、字符长度、句子 ID”排序。最终 32,353 个索引词条、25,012 条独立句子、58,774 个词–句关联；12,159 条合格句未入选每词前三。这是明确的精选规则，不称全量句库。
- 只索引字面英文 token，保留内部撇号和连字符；不制造词组，不还原词形，`run`、`runs`、`running` 分别索引。不将含数字或非 ASCII 字母的词部分截取为另一个词。
- 每句长度 10–220 字符、3–30 个 token，要求完整句标点；排除 URL、邮箱、标记和控制字符。这些不等于语义质量、真实性或儿童安全审核。
- 逐句 ID、原句 URL、最后修改时间保留在包的 metadata。当前 App 只把例句当字符串展示，不保证逐句来源按钮已经可用。
- 本包为可选补充，不默认启用；没有释义或音标，不应替代主要词典。

所有发布包的文件 SHA256 见 Release 清单。上游下载文件的 SHA 与转换包 SHA 是不同对象，不应混用；上游版本标签也不替代实际下载快照校验。
