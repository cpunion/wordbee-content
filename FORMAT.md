# .wordbee 内容包 v1

文件是 ZIP，根目录仅 `manifest.json`，可选资源位于 `assets/`。这个格式不赋予内容任何额外权利。公开包必须有明确许可，不允许私人数据或录音。

```json
{
  "schemaVersion": 1,
  "id": "my-original-list",
  "version": "1.0.0",
  "name": "我的原创词表",
  "source": "",
  "license": "CC0 1.0",
  "licenseURL": "https://creativecommons.org/publicdomain/zero/1.0/",
  "attribution": "由作者自行选择并贡献的示例",
  "lists": [
    { "id": "lesson-1", "name": "第一课", "words": ["seed", "grow", "look after"] }
  ]
}
```

上例仅用于演示，作者应自行确认所选内容和编排的权利。

- 包的 `id` 与内部词表 `id` 是更新身份，更新必须保留；`version` 是作者内容版本。ID 使用字母、数字、`_-.`，长度 1–120，不使用保留词表 ID `__root`。
- 词表可包含 `parentID` 引用同包节点，支持多级；不得循环或引用不存在节点。`words` 保留顺序、短语和显示大小写。
- 包可含 `dictionary: { id, name, entries }`。只装词典时令 `lists=[]`，不会生成空词表。
- 每个词典条目有 `spelling`，可选 `sourceURL`；`acceptedSpellings`、`definitions`、`definitionsZH`、`examples`、`ipaUS`、`ipaUK`、`etymologies` 均为字符串数组。相同规范拼写的义项应合并，不能重复建词条。
- 包级 `attribution`、`licenseURL` 和逐词 `sourceURL` 是兼容 v1 的可选扩展，缺省为空。具体来源 URL 必须为无认证凭据的 HTTPS。
- 原始 UTF-8 版权通知放在 `assets/licenses/`，每份最多 4 MiB、合计最多 8 MiB；App 仅在词典级保存一次，支持离线阅读。
- `sourceMetadata` 可以记录构建及逐义项来源，当前 App 不将所有扩展字段转为独立 UI；不能据此承诺逐句可点击来源。
- v1 单包 manifest 最多 64 MiB、词典最多 250,000 个规范词条，词表总成员最多 500,000。总压缩包最多 512 MiB。过大资料必须明确分包，不得默默截断。
- 不允许绝对路径、`..`、反斜杠、符号链接、大小写重复路径、可执行文件或压缩炸弹。

导入后词表、词典使用设备本地 `local-pack:` 身份；更新不会重置计划、掌握状态、复习历史或积分。内容包不能代替学习数据备份。
