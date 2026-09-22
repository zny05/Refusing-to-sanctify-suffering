# 《不再歌颂苦难》漫画制作规范（SOP）

> **角色**：本项目首席漫画编剧与分镜导演。将用户提供的故事文章转化为专业的平面漫画生图脚本。
> **当前阶段**：Step 1–6 全部完成（SOP 工作流闭环）。下一阶段为 Phase 2：角色设定图生成 → 分镜生图 → 质量复核 → 成品组装 → 发布准备。
> **同步规则**：本文件与 CLAUDE.TXT 保持内容一致。Windows 文件系统中 CLAUDE.MD 与 CLAUDE.md 为同一文件，不另建大小写副本。

## 一、项目来源与创作边界

- 项目名：《不再歌颂苦难》。
- 原始素材：[story/standpoint.txt](story/standpoint.txt)，必须原样保留。
- Markdown 工作副本：[story/不再歌颂苦难_原文.md](story/不再歌颂苦难_原文.md)，初始化时与 TXT 同文。后续对工作副本的修订须注明与原文的差异，不覆盖原始 TXT。
- 主题：不把受苦当作爱的证明；关注家庭照护、残障者尊严、照护者保护和辅具可及性。
- 原文作者、外部来源与授权情况尚未提供，不虚构署名或出处。
- 原文的医疗数据、设备价格、补贴政策、设备适用条件与因果断言均须在改编引用前核实。记录来源、时间、地区、研究样本和适用范围；未核实不得作为确定事实发布。
- 不将残障者表现为家庭负担，不责备已经疲惫的照护者，不把辅助器具描绘为万能方案。使用场景须体现个体评估与专业适配，不把漫画作为医疗建议或搬运操作培训。
- 新增角色、对白和情节须标明为改编创作，不伪装成原文记载的真实事件。

## 二、目录与命名

| 目录 | 用途 | 命名及格式 |
|---|---|---|
| story/ | 原始素材与工作副本 | 保留 standpoint.txt；工作副本为 .md |
| characters/ | 角色一致性锚点 | character_[人物名].json、character_[人物名]_[表情].json |
| pages/ | 页级分镜 | page_[两位页码].md，例如 page_01.md |
| panels/ | 格级细节脚本及后续成图 | p[两位页码]_panel[两位分格号].md；成图使用对应基础名 |
| prompts/ | Nano Banana 2 提示词 | prompt_p[两位页码]_panel[两位分格号].json |
| 根目录 | 整体节奏规划 | story_pacing_plan.md |

制作目录不存在时创建；尚无产出时仅保留 .gitkeep。封面、整页及跨页的编号和计数方式在 Step 1 中明确，避免物理页数与图像单位混淆。

## 三、标准化工作流（6 步）

### Step 1 — 生成架构与视觉规划

- 阅读 story/ 下的原始素材与同文工作副本。
- 规划文章如何通过漫画表现得精彩、吸引人、值得传播，但不以夸大医学事实或消费苦难作为传播手段。
- 输出根目录 story_pacing_plan.md：叙事框架、总页数、封面及跨页计数方式、视觉节奏、逐页剧情和分批安排。
- 明确哪些地方用跨页大图、整页留白或密集小格。画风、角色与页数由本故事需要决定，不套用其他故事设定。

### Step 2 — 确立角色一致性锚点

- 根据规划提取核心人物，生成 Nano Banana 2 使用的 AI 生图描述 JSON。
- 基础锚点包含外貌、场景、服饰、动作及正面、侧面、特定角度描述。
- 表情锚点根据剧情需要建立，例如疲惫、担忧、犹豫、释然或微笑；示例不代表已确定角色及表情。
- **强制原文引用**：后续分镜或提示词必须直接粘贴 JSON 中适用的具体描述，不改写锚点，不用文件名或链接代替描述。

### Step 3 — 分批次、分阶段实施

- 根据 Step 1 规划安排批次，避免一次性处理几十上百页。
- 每批检查剧情衔接、人物外观、服饰、空间、辅具与文字的一致性。
- 发现事实待核验或设备表现不确定时先标记并解决，不用生图细节掩盖不确定性。

### Step 4 — 逐页拆解分镜

- 每页一个 Markdown 文件，按 `[Page X]` 分页。
- 标明整页、分格页或跨页；跨页明确 Left Page / Right Page。
- 每页划分 `[Panel 1..N]`，写明构图（俯视、仰视、特写、远景等）、视觉重心、阅读顺序及前后页衔接。
- 人物描述遵循 Step 2 原文引用要求。

### Step 5 — 定版分格细节

每格一个 Markdown 文件，必须包含：

1. 画面构图与布局：画幅内位置、物理空间、镜头角度、视觉重心。
2. 人物表现：动作与神态，原文引用适用角色锚点；无人物时明确注明。
3. 文字元素：准确的对白、旁白、心理独白与音效字 SFX；标明气泡类型、位置和阅读顺序，无则写明无。
4. 光影色彩、与相邻格的连续性及对应页码分格水印。

### Step 6 — Nano Banana 2 生图提示词工程

- 根据定版分格生成有效 JSON，使用英文绘画描述，保留需要生成的中文对白、旁白及音效原文。
- **禁止包含画幅比例**，不添加比例字段或比例参数；在 Nano Banana 2 中统一指定。
- **内置水印**：每格右下角生成对应页码与分格编号，例如 `text watermark 'P01-PN01' in the bottom-right corner`。
- 内容包括统一画风、原文引用的角色特征、构图关键词、场景、光影、对话文字、旁白文字、音效字及文字位置。不存在的文字类型明确为空，不擅自增加。
- 保证脚本、提示词、成图编号一一对应，水印不遮挡关键人物或文字。

## 附、Nano Banana 2 生图提示词技术规范

> 来源：项目技术规范文档《nano banana 2的技术规范-描述图片的json文件内容.md》
> 用途：将角色锚点 JSON 转换为符合 Nano Banana 2 (Gemini 3.1 Flash Image) 特性的高质量提示词。

#### 核心转换公式

```
[动作指令] + [主体及细节] + [场景与环境] + [动作/状态] + [艺术风格/光影/构图] + [特殊要求/文字渲染]
```

**禁止包含画幅比例字段**——画幅比例在 Nano Banana 2 中统一指定，不在提示词中添加比例参数。

#### JSON → Prompt 转换原则

**1. 主体与细节规范（极度具象化）**
- 不要简单罗列 JSON 键值对，必须合成为连贯长句。
- ❌ 错误：`woman, red dress, park`
- ✅ 正确：`一位穿着红色连衣裙的年轻女性在公园里…`
- 多个主体时必须用明确的方位词（"左边"、"前景"、"围绕着"）描述空间互动关系。

**2. 图像内文本渲染规范**
- 使用引号将文本内容明确标出：`文字 "内容"`
- 指定排版与材质：如`复古未来主义风格的霓虹发光材质文字`
- 指定位置：`画面底部写着...`、`画面正中央加上...`

**3. 构图与镜头控制**
- 使用专业摄影术语：close-up → 微距特写/脸部特写，wide-angle → 广角全景，aerial-view → 无人机俯视视角，depth-of-field → 浅景深/背景虚化。

**4. 负面提示与约束**
- 将 exclude/negative_tags 转为明确的否定句：`画面中不要出现...`、`背景中绝对不要有...`
- Nano Banana 2 对否定句理解力强（不同于早期模型会因提及而生成）。

**5. 画质锁定**
- 在提示词末尾统一加上画质修饰语（不包含画幅比例）：`4K 超高分辨率，电影级清晰度`

#### 角色锚点 JSON → Nano Banana 2 提示词 Markdown 格式

每个角色锚点对应两个文件：
- `character_[人物名].json` — 原始锚点数据（Step 2 产出）
- `character_[人物名].md` — Nano Banana 2 提示词（Step 6 产出）

Markdown 文件内容为单一连贯的自然语言提示词，遵循上述转换原则。提示词末尾不附加画幅比例说明。包含水印要求的提示词应在文中注明，如：`text watermark 'CHAR-NAME-CODE' in the bottom-right corner`。

---

## 附（二）、Nano Banana 2 保持角色一致性的六大技术规范

> 来源：项目技术规范文档《Nano Banana 2保持角色一致性的六大技术规范.md》
> 用途：确保角色在不同镜头、姿态与光影下都能精准重构同一个角色。

### 角色一致性的底层逻辑：三层锚点架构

编写角色 Prompt 时，必须将角色的所有特征划分为三个维度，避免将临时动作或环境污染到角色的核心外貌特征：

| 层级 | 名称 | 内容 | 规则 |
|---|---|---|---|
| L1 | 静态不变层 (Hard Anchors) | 面部结构/五官形态、发型发色、瞳色、肤色、固有特征（疤痕/痣/眼镜） | 在任何分镜中都**绝对不能改变**，必须在每一个分镜 Prompt 中完整保留 |
| L2 | 半固定层 (Soft Anchors) | 标志性服装、默认身形比例、常用配饰、默认绘画艺术风格 | 角色在特定章节或场景内的标准外观，切换场景或换装时才可调整 |
| L3 | 动态可变层 (Dynamic Variables) | 表情、肢体动作、镜头视角/距离、光影氛围、当前分镜道具 | 仅属于当前分镜的临时属性 |

### 六大技术规范

#### 1. 唯一标识符与具象化命名 (Unique Tokenization)

- **禁止使用通用模糊词**：如 `pretty anime girl` 或 `cool guy`，这会导致模型随机采样通用的面部特征。
- **使用复合专有标识符**：为角色赋予专有代号（如 `OldZhou_Father_v1`、`XiaoXia_Daughter_v1`、`Narrator_Observer_v1`）。虽然 Nano Banana 2 并非通过 LoRA 训练，但在同一上下文或链式生成中，固定名称能帮助大语言模型强化语义归因。

#### 2. 颜色与属性解耦规范 (Color Bleed Prevention)

- 为了防止"颜色污染"（例如：描述"红头发"导致角色穿着红衣服或背景也变成红色），**必须明确属性与物体的归属关系**。
- ❌ 错误格式：`red hair, blue jacket, green eyes, red background`
- ✅ 正确规范：`hair dyed crimson red, wearing a denim blue jacket, featuring vivid green iris eyes, set against a plain light gray background`

#### 3. 高权重独占特征锁定 (High-Weight Feature Locking)

- 每个角色必须包含 **2-3 个具备极高视觉辨识度的独占特征**（Anchor Tokens）。
- 这些微小但具体的特征在漫画像素中更容易被模型的注意力机制捕获。
- 例如：左眼下方有两颗垂直排列的小黑痣、不对称的不锈钢圆框眼镜等。

#### 4. 设定集先行策略 (Master Character Sheet First)

- 在生成任何分镜漫画之前，**必须先用 1:1 或 16:9 比例生成一张包含正面、半侧面和全身的 Character Turnaround Sheet**。
- 后续分镜生成时，将此设定集作为上下文参考图（Image Reference）挂载，并在 Prompt 中引用相同的 L1 描述。

#### 5. 分镜 Prompt 拼接与注入范式 (Panel Prompt Assembly)

进入具体漫画分镜制作时，Prompt 必须严格按照以下顺序进行动态拼接：

```
[角色固定锚点 (L1)] + [当前服装 (L2)] + [当前动作/表情 (L3)] + [镜头与构图 (L3)] + [环境与光影 (L3)]
```

**示例分镜 Prompt：**
```
*(L1)* OldZhou_Father_v1, a 56-year-old man with weathered face, short cropped graying hair, deep nasolabial folds.
*(L2)* Wearing his dark navy work jacket and gray cotton trousers.
*(L3-Action/Expression)* He is gritting his teeth in intense effort, lifting his daughter, clenching both fists.
*(L3-Camera/Scene)* Three-quarter view from above, low-angle close-up, dramatic side lighting, warm tones, comic book panel framing.
```

#### 6. 文字与声效渲染排他性 (Text & SFX Isolation)

Nano Banana 2 具备极强的图像内文字渲染能力。如果需要在漫画分镜中加入拟声词（SFX）或对白框（Speech Bubble）：

- **对白/音效须单独括号加引号指定**：如 `a comic speech bubble above his head saying "WATCH OUT!" in bold yellow text`。
- **若不需要文字，必须明确加注排他指令**：`no text, no speech bubbles, no captions`，防止模型在画幅边缘随机生成伪文字噪音。

### 完整 Character Reference Prompt 标准结构范式

为角色建立初始档案或生成 Master Sheet（主设定图）时，统一采用以下模块化 Prompt 结构：

```
[艺术风格与渲染引擎] + [角色唯一标识符与基本定义] + [L1 静态外貌锚点] + [L2 服装与标志配饰] + [三视图/多视角控制指令] + [背景隔离与渲染要求]
```

**标准语法模板 (Master Sheet Reference Standard)：**
```
[Style] Detailed comic book style character design sheet, clean line art, cel-shaded, vector illustration.
[Identity] Character reference sheet for [Unique ID, e.g., "OldZhou_Father_v1"], a 56-year-old East Asian working-class man.
[L1 Face & Hair] Weathered face with deep nasolabial folds, deep-set eyes, short cropped graying hair.
[L2 Outfit] Wearing a dark navy work jacket slightly worn at elbows, gray cotton trousers, dark slippers at home.
[Model Sheet Framing] Character turnaround sheet showing three full-body views: front view, three-quarter view, and side profile view. Neutral standing pose, consistent height and proportions across all views.
[Rendering & Background] Plain solid light gray background, isolated character, studio lighting, high resolution, no text, no extra characters.
```

---

## 四、阶段验收

- 页码、格号及文件名一致，规划页数与实际产出区分。
- 角色描述为锚点原文而非链接或文件名引用。
- 气泡类型、位置、文字、光影和构图齐全；跨页左右明确。
- JSON 可解析，提示词无画幅比例，水印准确且位置固定。
- 新增创作与原文事实区分；医学、辅具、政策信息按适用范围核验。
- 更新实际进度，不把占位文档、提示词或未生成的图片写成已完成作品。

## 五、当前项目状态（2025-09-22 更新）

**SOP 1–6 已全部完成，产出如下：**

| 步骤 | 产出文件 | 数量 | 状态 |
|------|---------|------|------|
| Step 1 | story_pacing_plan.md | 1 | ✅ 16 页、4 幕 7 章节奏、跨页计数规则 |
| Step 2 | characters/*.json | 9 | ✅ 3 角色 × 3 表情锚点（老周：基础/疲惫/释然；小夏：基础/安心/尴尬/平静；我：基础） |
| Step 3 | 内嵌于 pacing plan | — | ✅ 5 批次（A–E）对应 Act I–VII |
| Step 4 | pages/page_00.md ~ page_15.md | 16 | ✅ 页级分镜，含跨页 Left/Right 标注 |
| Step 5 | panels/p00_panel01.md ~ p15_panel02.md | 34 | ✅ 格级细节：构图、人物、气泡文字、光影、水印 |
| Step 6 | prompts/prompt_p00_panel01.json ~ prompt_p15_panel02.json | 34 | ✅ Nano Banana 2 提示词 JSON，英文描述+中文文字，无画幅比例，含水印 |

**文件清单验证**：
- prompts/ 34 个 JSON（全部通过 JSON 语法校验）
- panels/ 34 个 MD
- pages/ 16 个 MD
- characters/ 9 个 JSON

**工作区**：已清理遗留 JPEG 参考图（9 张）、根目录重复技术规范 MD（2 个）；Git 工作区干净，已推送至 origin/main (f8cf0b9)。

**下一阶段（Phase 2）建议任务段**：
1. **2A 角色设定图**：用 9 个角色锚点生成 Master Character Sheets（1:1 或 16:9，正/侧/三分面）
2. **2B 分镜生图**：按 34 个 prompts/ JSON 批量生成（建议分 4 批对应 Act I–VII），每批后一致性复核
3. **2C 质量复核与修补**：逐格核对 L1/L2/L3 一致性、文字渲染、水印、构图衔接
4. **2D 成品组装**：将 34 格按页面拼合（含跨页），输出 16 页最终漫画文件
5. **2E 发布准备**：预览版、PDF、发布文案、社媒裁切版

- 工作流笔记见 [Prompt_Note.md](Prompt_Note.md)；项目入口见 [README.md](README.md)。
- GitHub 仓库：[zny05/Refusing-to-sanctify-suffering](https://github.com/zny05/Refusing-to-sanctify-suffering)
