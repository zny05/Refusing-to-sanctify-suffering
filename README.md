# 《不再歌颂苦难》漫画制作项目 / *Refusing to Sanctify Suffering*

> 将用户提供的文章改编为专业平面漫画的制作项目。拒绝将苦难赋予崇高、神圣的意义。

---

## 项目信息 / Project Info

| 项目 / Item | 内容 / Description |
|---|---|
| 项目名 / Project Name | 《不再歌颂苦难》/ *Refusing to Sanctify Suffering* |
| 主题 / Theme | 不把受苦当作爱的证明；关注家庭照护、残障者尊严、照护者保护与辅具可及性 |
| 原始素材 / Source Material | [story/standpoint.txt](story/standpoint.txt)（原样保留 / preserved as-is） |
| 改编底稿 / Adaptation Draft | [story/不再歌颂苦难_漫画改编版.md](story/不再歌颂苦难_漫画改编版.md) |
| 工作副本 / Working Copy | [story/不再歌颂苦难_原文.md](story/不再歌颂苦难_原文.md)（与 TXT 同文 / matches TXT content） |
| 制作规范 / Production SOP | [CLAUDE.md](CLAUDE.md) |
| 整体节奏规划 / Pacing Plan | [story_pacing_plan.md](story_pacing_plan.md) |
| 原文作者与授权 / Author & License | 尚未提供，发布前须确认 / Not yet provided; must be confirmed before publication |

---

## 故事概述 / Story Overview

一个五十六岁的父亲每天清晨弯腰把女儿从床上搬到轮椅上——这段视频在网上获得数百万播放，评论区充满「伟大的父爱」。然而，没有一条留言提到：有一种设备叫移位机，可以让父亲不必弯腰。

漫画通过老周父女的日常，探讨「我们到底是在赞美爱，还是在赞美受苦」，介绍转移板、移位机、天轨移位系统、转移带等辅助器具，并揭示照护者因「用工具=偷懒」的文化观念而无法获得专业辅助的困境。核心观点：**爱不是一次性的壮举，工具是爱的基础设施。**

A 56-year-old father bends over every morning to lift his paralyzed daughter from bed to wheelchair — a video of this goes viral with millions of views and comments praising his "great fatherly love." Yet not one comment mentions: there exists a patient lift hoist that would spare his back.

Through the daily life of father Old Zhou and his daughter Xiao Xia, the comic explores "are we praising love, or are we praising suffering?", introduces assistive devices (transfer boards, patient lifts, ceiling-mounted track systems, transfer belts), and reveals how cultural beliefs ("using tools = laziness") prevent caregivers from accessing professional assistance. Core message: **Love is not a single heroic act — tools are the infrastructure of love.**

---

## 当前阶段 / Current Stage

**已完成 / Completed**: **SOP Step 1–6 全部完成**（完整工作流闭环）。

| 步骤 / Step | 产出 / Output | 数量 / Count | 状态 / Status |
|---|---|---|---|
| Step 1: 架构与视觉规划 | [story_pacing_plan.md](story_pacing_plan.md) | 1 文件 | ✅ |
| Step 2: 角色一致性锚点 | `characters/*.json` | 9 个 JSON | ✅ |
| Step 3: 分批分阶段实施 | 内嵌于 pacing plan | 5 批次 (A–E) | ✅ |
| Step 4: 逐页拆解分镜 | `pages/page_00.md` ~ `page_15.md` | 16 个 MD | ✅ |
| Step 5: 定版分格细节 | `panels/pXX_panelYY.md` | 34 个 MD | ✅ |
| Step 6: 生图提示词工程 | `prompts/prompt_pXX_panelYY.json` | 34 个 JSON | ✅ |

**尚未开始 / Not yet started**: **Phase 2 生产与交付** — 角色设定图生成 → 分镜生图 → 质量复核 → 成品组装 → 发布准备。

### 规划概览 / Plan Overview

| 项目 / Item | 内容 / Description |
|---|---|
| 总页数 / Total Pages | 16 页（含封面 / including cover） |
| 叙事结构 / Narrative Structure | 三幕式「祛魅」之旅：情感钩子 ➔ 科学解构 ➔ 人文重塑 |
| 画风 / Art Style | 现代 editorial comic，暖色家庭场景 + 冷色数据/医学场景 |
| 核心角色 / Main Characters | 老周（父亲）、小夏（女儿）、「我」（叙述者） |
| 批量安排 / Batch Plan | A（P00–P02）→ B（P03–P05）→ C（P06–P09）→ D（P10–P13）→ E（P14–P15） |

---

## 目录结构 / Directory Structure

```
.
├── README.md                        # 本文件 / This file
├── CLAUDE.md                        # 漫画制作规范 SOP / Production SOP
├── LICENSE                            # 许可证 / License
├── story/                           # 原始素材与工作副本 / Source & working copies
│   ├── standpoint.txt               # 原始素材，原样保留 / Original, preserved as-is
│   ├── 不再歌颂苦难_原文.md          # 同文工作副本 / Working copy (matches TXT)
│   ├── 不再歌颂苦难_漫画改编版.md    # 漫画改编底稿 / Adaptation draft
│   └── 不再歌颂苦难_表达角度规划.md  # 表达角度规划（用户提供） / Expression planning (user-provided)
├── story_pacing_plan.md             # Step 1 整体节奏规划 / Step 1 pacing plan
├── characters/                      # 角色一致性锚点（.gitkeep 起步）/ Character anchors (starts with .gitkeep)
├── pages/                           # 页级分镜（.gitkeep 起步）/ Page scripts (starts with .gitkeep)
├── panels/                          # 格级脚本及成图（.gitkeep 起步）/ Panel scripts & renders (starts with .gitkeep)
└── prompts/                         # Nano Banana 2 提示词（.gitkeep 起步）/ Prompt JSONs (starts with .gitkeep)
```

> **注**：`CLAUDE.TXT`、`Prompt_Note.md`、`.env` 及 `.code-workspace` 为本地忽略文件，不纳入版本控制。
> **Note**: `CLAUDE.TXT`, `Prompt_Note.md`, `.env`, and `.code-workspace` are locally ignored and not version-controlled.

---

## 六步制作流程 / Six-Step Production Workflow

1. **架构与视觉规划** / **Architecture & Visual Planning**: 阅读原文，明确叙事框架、总页数、视觉节奏和逐页剧情，输出 [story_pacing_plan.md](story_pacing_plan.md)。✅ **Done**
2. **角色一致性锚点** / **Character Anchors**: 建立基础角色与表情 JSON，确定外观、服饰、动作、角度和场景描述。✅ **Done** (9 JSON)
3. **分批分阶段实施** / **Batch Execution**: 依据规划安排批次，每批检查剧情、人物和空间连贯性。✅ **Done** (5 批次 A–E)
4. **逐页拆解分镜** / **Page Storyboarding**: 输出 `pages/page_XX.md`，标注页面属性、分格、构图和视觉重心。✅ **Done** (16 MD)
5. **定版分格细节** / **Panel Details**: 输出 `panels/pXX_panelYY.md`，明确画面布局、人物表现、气泡位置和文字。✅ **Done** (34 MD)
6. **生图提示词工程** / **Image Prompt Engineering**: 输出 `prompts/prompt_pXX_panelYY.json`，供 Nano Banana 2 使用。✅ **Done** (34 JSON)

---

## 强制规范 / Mandatory Rules

| 规范 / Rule | 说明 / Description |
|---|---|
| 角色描述原文引用 / Character descriptions must cite anchors | 分镜与提示词中的人物描述必须直接引用角色 JSON 中的具体描述，不以文件名或链接代替 |
| 页面组织 / Page organization | 按 `[Page X]`、`[Panel 1..N]` 组织；跨页标明 Left Page / Right Page |
| 提示词无画幅比例 / No aspect ratio in prompts | 提示词不包含画幅比例字段；在 Nano Banana 2 中统一指定 |
| 水印位置 / Watermark position | 每格提示词要求右下角生成对应水印，例如 `P01-PN01` |
| 文字完整性 / Text completeness | 提示词包含统一画风、人物特征、构图、光影、中文对白、旁白与音效字；无某类文字时明确为空，不自行添加 |

---

## 改编与事实核查边界 / Adaptation & Fact-Check Boundaries

- 尊重照护者和被照护者，不把残障者表现为家庭负担，不以羞辱、猎奇或美化伤痛获取关注。
- 辅具不是对所有人的统一处方。选型、适配与使用应由相关专业人员结合个体状况、环境和设备说明评估；漫画不代替医疗建议或操作培训。
- 原文中的研究比例、疾病因果断言、价格、补贴和租赁政策尚未核验。引用前需核对出处、样本、适用范围、时间及地区；未核实内容不得包装成确定事实。
- 不虚构研究来源、治疗效果、作者或现实人物身份。新增人物、对白及情节需与原文事实区分。

---

## 版本与仓库 / Versioning & Repository

- **GitHub 仓库**: [zny05/Refusing-to-sanctify-suffering](https://github.com/zny05/Refusing-to-sanctify-suffering)
- 本项目为全新初始提交，不含旧项目历史。旧提交历史仅保留在本地 `legacy-main` 分支。
- `.env`、工作区文件及本地配置文件不纳入版本控制。

---

## 许可证 / License

保留现有 [LICENSE](LICENSE)。原始文章及后续引用素材的权利与改编许可需另行确认；仓库许可证不替代第三方素材授权。

---

*本项目为文化公益性质的制作探索，所有内容以尊重与关怀为基本前提。*
*This project is a cultural and public-interest creative exploration. All content is produced with respect and care as its fundamental premise.*
