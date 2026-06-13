# Phase 2 AI-Video Prompt Workbook

Phase 2 creates an `.xlsx` workbook for AI video generation. It is not a mechanical shot conversion. It is a director-level visual rewrite that turns a confirmed Phase 1 direction or user-provided script into executable visual instructions.

## Mandatory Gate Before Work

Before generating Phase 2, ask whether the user has product or character descriptions.

- If images are provided, ask for matching text descriptions: appearance, clothing, materials, colors, and key visual traits.
- If text descriptions are provided, integrate them directly.
- If the user says none, create suitable assumptions and label them `AI自主设定，建议用户确认`.
- If information is insufficient, ask questions before output.

## Non-Negotiable Boundaries

You may complete or optimize:

- Action details
- Environmental details
- Light and shadow design
- Composition
- Camera design
- Prop details
- Rhythm and lens split

You must not change:

- Core creative idea
- Product selling points
- Brand information
- Character identity or setting
- Core narrative event
- Narrative logic

## Lens Split Logic

Phase 1 time ranges are narrative beats, not final shot counts. Split each beat into independent AI-video shots only when the narrative needs it.

Create a new shot only for:

- New information
- Scene change
- Character action change
- Emotional change
- Visual focus shift
- Rhythm progression need

Do not divide time mechanically. Shot duration is determined by content:

- Complex action: longer
- Emotional hold: longer
- Dense information: shorter
- Transition shot: can be very short

Keep the total duration of split shots near the original narrative beat duration. Prefer within about `±10%`, but natural viewing rhythm matters more than exact math.

## Prompt Structure

Each lens prompt must include:

- 时间
- 景别: 大全景 / 全景 / 中景 / 中近景 / 近景 / 特写 / 大特写
- 画面风格 / 影调
- 场景环境, specific and concrete
- 主体描述: appearance + clothing + posture + expression
- 主体动作: beginning, process, ending
- 光影描述: light direction + light quality + light effect + shadow traits
- 构图: 三分法 / 中心构图 / 框架式构图 / 对称构图 / 引导线构图, or another deliberate composition
- 运镜方式: specific start point, direction, speed, end point
- 情绪动机: why this camera movement exists and which emotion it serves
- 转场: transition type, action, rhythm, narrative purpose, only when useful
- 音效: sound effects only, no background music

## Shot Quality Standard

Every shot must have:

- Focus: the viewer knows what to look at.
- Action: the frame is not a still photo.
- Layers: foreground, subject, background.
- Purpose: the shot has a narrative reason to exist.

Final test: can the prompt produce a complete mental image? If the reader must guess, complete the missing details.

## Workbook Content Modules

The workbook must include:

1. 创意概念简介
2. 人物设定prompt, if people appear
3. 产品设定prompt
4. 通用负面提示词
5. 大镜头 sections with numbered lens prompts

Use this fixed negative prompt unless the user requests otherwise:

```text
低质量，模糊，画面闪烁，画面抖动，鬼影，拖影，噪点，人物变形，五官畸形，多余肢体，多余手指，动作不自然，身份漂移，场景跳变，细节缺失，渲染错误，水印，文字，字幕，Logo
```

## Excel Layout Standard

Use the user's sample image as a layout reference, not a content reference.

Required sheet and layout:

- Sheet name: `AI视频Prompt`
- Column A: narrow label/index column.
- Column B: wide main content column.
- Columns A:B may be merged for section bars and large prompt bodies when useful.
- Keep extra columns available but visually secondary.
- Freeze panes is optional; readable layout is mandatory.

Global reference block:

- Row 1: gray filled title bar with bold `【全局参考】`.
- Following rows: `人物`, `产品`, `负面提示词`.
- Use large row heights and wrapped text.
- Leave enough white space so dense descriptions do not feel cramped.

Major-shot section:

- Use a dark gray bar with white bold text.
- Format: `大镜头一 · 0-4s · 序曲：土地在喘息`.
- One major-shot bar separates each narrative block.

Lens rows:

- Use IDs such as `L1-1`, `L1-2`, `L2-1`.
- Put the ID in the narrow left column.
- Put all prompt detail in the wide merged/right content area.
- Use bold field labels followed by values.
- Use line breaks between fields.
- Set vertical alignment to top.
- Enable wrap text.
- Set generous row height so no content is hidden.

Field labels inside each lens cell:

```text
时间：
景别：
画面风格 / 影调：
场景环境：
主体描述：
主体动作：
光影描述：
构图：
运镜方式：
情绪动机：
转场：
音效：
```

Visual formatting:

- Section header gray fill.
- Major-shot bars dark gray fill with white bold text.
- Thin grid borders.
- Prompt labels bold.
- Header rows may use gray fill.
- No clipped text.
- No content covered by overlapping objects.
- File should read like a director's working prompt sheet, not a generic data table.

## Output Behavior

After generating the workbook, respond only with a concise sentence telling the user the `.xlsx` path. Do not paste the whole workbook content into chat unless the user asks.
