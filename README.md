# Competitor Analysis Marketing Game Skills

This repository contains reusable Zero skills for marketing-game competitor analysis workflows.

## Included Skills

### xiaohongshu-scraper

A Zero skill for keyword-driven Xiaohongshu competitor research. It supports:

- Searching Xiaohongshu by keyword
- Opening post detail pages
- Browsing and scrolling the comment area container
- Capturing detail-page and comment-area screenshots
- Producing a sample confirmation draft before final reporting
- Generating HTML/PNG competitor analysis reports with embedded evidence screenshots

Skill path:

```text
skills/xiaohongshu-scraper/SKILL.md
```

## Key Workflow

1. Search Xiaohongshu by keyword.
2. Sample relevant posts.
3. Open each post detail page.
4. Scroll inside the comment-area container, not just the full page.
5. Save evidence screenshots:
   - Detail page screenshot
   - Comment area screenshot
6. Output a sample confirmation draft first.
7. After user confirmation, generate the final competitor analysis report.

## Report Requirements

The final report should include:

- Task overview
- Sample overview
- Competitor comparison
- Key insights with embedded evidence screenshots
- Actionable recommendations

Important reporting rules:

- Evidence screenshots must be embedded directly in the HTML/PNG report.
- Do not show only `file://` image paths in final reports.
- A single insight can be supported by multiple related posts and screenshots.
- Do not force a one-post-one-insight structure.
- Use only visible page information. Do not fabricate metrics or comments.

## Install

Copy the skill folder into your Zero skills directory:

```bash
cp -R skills/xiaohongshu-scraper "~/Library/Application Support/Relay/Electron/resources/SKILLs/"
```

If your Zero installation uses a different skills directory, copy the folder there instead.

## Package

A distributable ZIP can be created with:

```bash
cd skills
zip -r xiaohongshu-scraper-skill.zip xiaohongshu-scraper -x "*/.DS_Store"
```

## Notes

This skill is designed for research and analysis workflows. It depends on browser automation availability when interacting with Xiaohongshu pages. If login is required, complete login in the browser session before continuing collection.
