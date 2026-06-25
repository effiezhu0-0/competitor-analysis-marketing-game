# 示例输出 01：标准输出

## 第一阶段：样本确认稿

```markdown
# 小红书样本确认稿

## 样本 1

- 链接：<https://www.xiaohongshu.com/explore/example-1>
- 摘要：该帖围绕蚂蚁庄园小鸡桌面组件的不同状态展开，评论区讨论“怎么设置”“为什么我没有”等问题。
- 初步判断：这是“状态展示 + 教程需求”型样本，能支撑用户对设置和触发机制有明确诉求的结论。
- 证据截图：
  - 详情页：[widget_post_1_detail.jpg](file:///path/to/screenshots/widget_post_1_detail.jpg)
  - 评论区：[widget_post_1_comments.jpg](file:///path/to/screenshots/widget_post_1_comments.jpg)

## 样本 2

- 链接：<https://www.xiaohongshu.com/explore/example-2>
- 摘要：该帖展示百变小鸡状态，评论中出现长期收集、攒状态、期待新图等表达。
- 初步判断：这是“图鉴收集 / 长期养成”型样本。
- 证据截图：
  - 详情页：[widget_post_2_detail.jpg](file:///path/to/screenshots/widget_post_2_detail.jpg)
  - 评论区：[widget_post_2_comments.jpg](file:///path/to/screenshots/widget_post_2_comments.jpg)
```

确认稿要求：

- 只展示详情页和评论区截图。
- 不展示列表页截图。
- 样本确认稿阶段可以使用图片路径链接，方便用户点击核对。
- 用户确认前不生成最终报告。

## 第二阶段：最终报告结构

用户确认后，生成 HTML + PNG 报告。报告结构如下：

```text
1. 任务概览
2. 样本总览
3. 竞品对比
4. 关键结论（每条结论下方直接展示相关证据截图）
5. 样本图文证据
6. 可执行建议
```

## 关键结论示例

```html
<section>
  <h2>4. 关键结论</h2>

  <div class="insight">
    <b>C1：用户关注的不是“小组件好不好看”，而是“我怎么也能拥有”。</b>
    <p>第 1、4 条评论中出现“怎么设置”“为什么我这里找不着”等问题，说明内容转化关键在教程化和可复现性。</p>
    <div class="evidence-grid">
      <div class="evidence-card">
        <img src="file:///path/to/screenshots/widget_post_1_comments.jpg" alt="样本1评论区证据">
        <p>样本 1 评论区：设置/触发问题</p>
      </div>
      <div class="evidence-card">
        <img src="file:///path/to/screenshots/widget_post_4_comments.jpg" alt="样本4评论区证据">
        <p>样本 4 评论区：找不到/怎么设置</p>
      </div>
    </div>
  </div>
</section>
```

最终报告要求：

- 图片必须以 `<img>` 形式直接嵌入展示。
- 不单独输出“结论-证据映射表”章节。
- 一个结论可以对应多个帖子和多张截图。
- 结论必须能从页面可见内容和截图证据追溯。
- 不编造评论、互动量和用户观点。

## 最终回复示例

```markdown
已按确认样本生成最终竞品分析报告，未重新搜索。

1. HTML 报告  
[competitor_report.html](file:///path/to/report/competitor_report.html)

2. PNG 报告  
[competitor_report.png](file:///path/to/report/competitor_report.png)
```
