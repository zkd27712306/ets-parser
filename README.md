# ETS 试卷解析器

一个纯前端的 ETS 试卷解析工具。上传 `%APPDATA%\ETS` 文件夹后，自动识别多套试卷、题型和答案，支持按试卷/题型/题目三级勾选，并导出干净的 TXT。

## ✨ 功能

- 📂 上传 ETS 根目录，自动扫描多套试卷
- 🏷 自动识别题型（模仿朗读 / 听选信息 / 回答问题 / 短文复述 / 提问）
- ✅ 按试卷、题型、题目三级勾选
- 📤 导出 TXT，支持完整导出和只导出答案
- 🔍 关键词搜索，实时过滤题目
- 📄 听力原文折叠显示，默认收起
- 🌙 深色模式，打开页面即按系统主题显示
- 🌐 纯前端，数据不上传，全部在本地浏览器处理
- 🧹 干净结果，自动去掉 `ets_th1` 前缀和重复的题目提示

## 📍 ETS 数据目录位置（Windows）

| 写法 | 路径 |
|---|---|
| 推荐 | `%APPDATA%\ETS` |
| 等价 | `%USERPROFILE%\AppData\Roaming\ETS` |
| 系统盘 | `%SYSTEMDRIVE%\Users\%USERNAME%\AppData\Roaming\ETS` |
| 特殊 | `%SYSTEMDRIVE%\Users\ADMIN_%USERNAME%\AppData\Roaming\ETS` |

快速打开：按 `Win + R`，粘贴 `%APPDATA%\ETS` 回车。

典型结构：

    %APPDATA%\ETS\
    └── 612578\
        ├── content_664036\
        │   ├── content.json
        │   ├── content2.json
        │   └── info.json
        ├── content_664037\
        ├── ...
        └── template_661\
            ├── res.json
            ├── ctrl.json
            └── info.json

## 🚀 使用方法

### 在线使用

打开：

[https://zkd27712306.github.io/ets-parser/](https://zkd27712306.github.io/ets-parser/)

### 本地使用

1. 下载 `index.html`
2. 用 Chrome / Edge 打开
3. 点击「选择 ETS 根目录」，选中 `%APPDATA%\ETS`
4. 自动解析后，勾选要导出的试卷 / 题型 / 题目
5. 点「导出 TXT」或「只导出答案」

## 🧩 支持的题型

| 题型 | 对应结构 | 输出内容 |
|---|---|---|
| 模仿朗读 | `collector.read` | 朗读原文 |
| 听选信息 | `collector.role` | 题目 + 参考答案 |
| 回答问题 | `collector.role` | 题目 + 参考答案 |
| 短文复述 | `collector.picture` | 复述要点 + 参考原文 |
| 提问 | `collector.role` | 中文提示 + 参考问句 |
| 单词跟读 | `collector.word` | 单词 + 释义 + 音标 |
| 短文跟读 | `collector.repeat_essay` | 第 X 句 + 原文 + 翻译 |
| 对话跟读 | `collector.repeat_dialogue` | 第 X 句 + 原文 + 翻译 |

## ⚠️ 注意事项

- 浏览器出于安全限制，必须**手动点击选择文件夹**，无法自动读取
- 仅支持 **Chrome / Edge**（依赖 `webkitdirectory`）
- 解析前建议在 ETS 里**完整下载并打开**目标试卷，避免缓存错位
- 本工具仅供学习研究，请勿用于违规用途
- 请勿将导出的试卷内容公开传播
- 仓库中请勿提交真实试卷 JSON，避免版权与个人信息问题

## 📄 许可证

采用 GPL-3.0 许可证
