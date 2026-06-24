# 营销互动竞品分析skill

可在Zero中使用的skill，主要用于营销互动游戏的竞品分析场景。

它支持：

- 根据关键词搜索小红书内容
- 浏览帖子详情页、评论区
- 截取详情页和评论区相关图片
- 输出图文对应的竞品分析报告

Skill 文件路径：

```text
skills/xiaohongshu-scraper/SKILL.md
```

## 分析维度

- 达成的业务目标
- 游戏玩法模式
- 用户牵引及留存机制
- 内容叙事与情绪价值

## 核心流程

1. 输入关键词，例如“JOY游记”
2. Agent在小红书中搜索关键词并截取信息
3. Agent输出图文对应信息来源，让用户确认样本是否可用
4. 用户确认后，生成最终竞品分析报告。

## 安装方式

将 skill 文件夹复制到本地 Zero Skills 目录：

```bash
cp -R skills/xiaohongshu-scraper "~/Library/Application Support/Relay/Electron/resources/SKILLs/"
```

如果你的 Zero 安装路径不同，请把 `xiaohongshu-scraper` 文件夹复制到对应的 Skills 目录下。

安装后，Zero 在遇到小红书、竞品分析、关键词搜索、帖子评论分析等任务时，可以使用该 Skill。

## 打包方式

如果需要生成可分发压缩包，可以执行：

```bash
cd skills
zip -r xiaohongshu-scraper-skill.zip xiaohongshu-scraper -x "*/.DS_Store"
```

生成的 `xiaohongshu-scraper-skill.zip` 可以发给其他用户安装。

## 目录结构

```text
.
├── README.md
└── skills
    └── xiaohongshu-scraper
        ├── SKILL.md
        └── evals
            └── evals.json
```

## 注意事项

- 该Skill依赖浏览器自动化能力来打开小红书页面、滚动评论区和截图。
- 如果小红书页面出现登录弹窗，需要先完成登录。
- 截图建议保存到稳定目录，避免放在 `/tmp` 后被系统清理。
- 最终报告应优先使用 HTML + PNG 两种格式，方便查看和分享。
