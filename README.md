# 营销互动竞品分析skill

可在 Zero 中使用的 Skill，主要用于营销互动游戏、互动活动和社媒内容的竞品分析场景。

## 当前包含的 Skill

### competitor-analysis-marketing-game

`competitor-analysis-marketing-game` 是一个用于营销游戏、互动活动与小红书社媒内容调研的 Zero Skill。

它支持：

- 根据关键词搜索小红书内容
- 浏览帖子详情页、评论区
- 在评论区容器内单独滚动浏览
- 截取详情页和评论区相关图片
- 先输出图文对应的样本确认稿
- 用户确认后输出 HTML / PNG 格式竞品分析报告
- 在报告中直接嵌入证据截图，方便图文对应核验

Skill 文件路径：

```text
skills/competitor-analysis-marketing-game/SKILL.md
```

## 分析维度

- 达成的业务目标
- 游戏玩法模式
- 用户牵引及留存机制
- 内容叙事与情绪价值
- 评论区高频诉求
- 社媒传播与互动机制

## 适用场景

- 小红书竞品内容分析
- 营销游戏/互动活动种草内容分析
- 用户评论观点总结
- 评论区情绪和高频诉求提炼
- 社媒内容策略复盘
- 活动玩法、互动机制、用户反馈对比

## 核心流程

1. 输入关键词，例如“JOY游记”或“蚂蚁庄园桌面组件”。
2. Agent 在小红书中搜索关键词并抽样相关帖子。
3. Agent 逐条打开帖子详情页，浏览并滚动评论区容器。
4. Agent 截取详情页和评论区证据图。
5. Agent 输出图文对应信息来源，让用户确认样本是否可用。
6. 用户确认后，生成最终竞品分析报告。

## 报告输出规范

最终报告通常包含：

- 任务概览
- 样本总览
- 竞品对比
- 关键结论（直接嵌入证据截图）
- 样本图文证据
- 可执行建议

重要规则：

- 报告中的证据截图必须直接嵌入展示，不能只放 `file://` 图片地址。
- 一个结论可以由多个帖子共同支撑，不强制“一条帖子对应一条结论”。
- 结论要按内容相关性匹配证据截图。
- 不再单独输出冗余的“结论-证据映射表”章节，证据应直接放在关键结论下。
- 只使用页面可见信息，不编造评论、互动量或结论依据。
- 评论分析需要说明样本范围，例如“基于页面可见评论”。
- 若小红书要求登录，需要先在浏览器中完成登录，再继续采集。

## Skill 标准结构

该 Skill 按录入规范补齐了推荐结构：

```text
skills/competitor-analysis-marketing-game/
├── README.md
├── SKILL.md
├── references/
│   ├── overview.md
│   ├── rules.md
│   ├── workflow.md
│   └── source-docs/
│       └── 录入Skill标准.pdf
├── examples/
│   ├── input-01.md
│   └── output-01.md
└── evals/
    └── evals.json
```

## 安装方式

将 skill 文件夹复制到本地 Zero Skills 目录：

```bash
cp -R skills/competitor-analysis-marketing-game "~/Library/Application Support/Relay/Electron/resources/SKILLs/"
```

如果你的 Zero 安装路径不同，请把 `competitor-analysis-marketing-game` 文件夹复制到对应的 Skills 目录下。

安装后，Zero 在遇到小红书、竞品分析、营销游戏、互动活动、关键词搜索、帖子评论分析等任务时，可以使用该 Skill。

## 打包方式

如果需要生成可分发压缩包，可以执行：

```bash
cd skills
zip -r competitor-analysis-marketing-game-skill.zip competitor-analysis-marketing-game -x "*/.DS_Store"
```

生成的 `competitor-analysis-marketing-game-skill.zip` 可以发给其他用户安装。

## 注意事项

- 该 Skill 依赖浏览器自动化能力来打开小红书页面、滚动评论区和截图。
- 如果小红书页面出现登录弹窗，需要先完成登录。
- 截图建议保存到稳定目录，避免放在 `/tmp` 后被系统清理。
- 最终报告应优先使用 HTML + PNG 两种格式，方便查看和分享。
