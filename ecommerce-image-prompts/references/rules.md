# Ecommerce Prompt Rules

## Negative Prompt Rules

Negative prompts must include both:

1. General negative terms
2. Product-specific negative terms

General examples:

- 不要模糊
- 不要错误文字
- 不要多余 logo
- 不要画面脏乱
- 不要过度卡通
- 不要过度变形
- 不要比例失真
- 不要产品被遮挡
- 不要主体不清晰
- 不要水印

Product-specific negative terms must mirror `Product Lock Prompt`.

Examples:

- If the product has one Type-C port on the right side, write: `不要在左侧、顶部或底部新增接口，不要将 Type-C 改为其他接口类型。`
- If the product has no screen, write: `不要新增屏幕或发光显示区域。`
- If the product is matte plastic, write: `不要把材质改成金属、玻璃、皮革或布料。`

## GPT Image Rules

Default to Chinese natural-language prompts.

Use structured sections such as:

- 图片目标
- 画面内容
- 产品锁定
- 风格锁定
- 卖点表达
- 构图与镜头
- 文字要求
- 负面词

Avoid parameter-style prompt fragments such as:

- `--ar 1:1`
- `--v 6`
- `--style raw`
- `8k`
- `ultra realistic`
- `cinematic lighting`

Use ratio as natural language instead, such as: `画面比例为 1:1，适合 Amazon 主图。`

## Reference Image Rules

When the user provides competitor or brand references, say clearly that references are for visual style only.

Allowed:

- Lighting
- Composition tendency
- Color relationship
- Shot scale
- Background complexity
- Visual atmosphere
- Product presentation logic
- Commercial photography feel

Forbidden:

- Copying competitor products
- Copying brand logos
- Copying text content
- Copying exact layout details
- Copying people or poses
- Copying packaging
- Copying prop combinations
- Copying highly recognizable scene structures
- Saying `做一张一模一样的图`

Recommended wording:

`参考图只作为视觉风格参考，借鉴其光影、构图、色彩和画面气质，不复刻具体产品、品牌元素、人物、文字、道具组合或版式。`

## Product Image Update Rules

If the user updates the product image during the workflow:

1. Re-run Step 1 and produce a new `Product Lock Prompt`.
2. Compare old and new product differences.
3. If only color changed, update color while keeping structure locked.
4. If structure changed, tell the user previous prompts may need synchronized revision.
5. Ask whether `Master Visual Direction` should be updated.
6. Do not delete old records. Mark them as `基于旧版产品图生成`.

## Multi-SKU Rules

For multiple colors, variants, or materials:

1. Choose one main SKU and complete the full workflow first.
2. For other colors, update only color descriptions in `Product Lock Prompt` when structure is unchanged.
3. Share `Style Lock Prompt` and `Master Visual Direction` across SKUs when appropriate.
4. Record each SKU separately in `Prompt Asset Record`.
5. If material differs between SKUs, describe that SKU's material separately.

## Version Management

Every prompt revision must use version labels:

- `V1：初始版本`
- `V2：根据用户反馈修改背景色`
- `V3：根据用户反馈调整构图`

Record revision reason and final confirmation reason in the asset record.

## Progress Management

Add a short status line in each workflow reply.

Examples:

- `当前进度：Step 1 完成 | Step 2 卖点规划完成 | 等待您确认后进入 Step 3`
- `当前进度：图1 Final 确认 | 图2 V1 已输出 | 等待您的反馈`
