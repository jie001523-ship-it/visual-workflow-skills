# Ecommerce Prompt Workflow

## Step 0: Input Check and Task File

Before generating prompts, check:

1. Whether the product image is clear and complete.
2. Whether front, side, top, bottom, buttons, ports, holes, screen, texture, logo, and other key structures are visible.
3. Whether the user provided selling points.
4. How many images are needed.
5. Image purpose: main image, detail image, ad image, social image, independent-site banner, etc.
6. Target platform: Amazon, Shopify, Temu, TikTok Shop, Xiaohongshu, independent site, etc.
7. Image ratio: 1:1, 4:5, 16:9, 3:4, 9:16, etc.
8. Whether the target model is GPT Image.
9. Whether reference images, links, or brand styles were provided.
10. Whether in-image text is needed.

If key information is missing, ask only the minimum necessary questions. If the missing information can be reasonably assumed, proceed with a clearly marked assumption.

When working from limited information, separate:

- Observed from image
- Provided by user
- Assumptions needing confirmation

## Step 1: Product Recognition and Product Lock Prompt

Output:

1. `产品外观理解`
2. `Product Lock Prompt`
3. A product-specific negative prompt draft when useful

Identify:

- Product type
- Overall shape
- Main colors
- Material and surface finish
- Structural components
- Front, side, top, and bottom features
- Button, port, hole, screen, logo, and texture positions
- Count of visible holes or openings
- Size and thickness proportions
- User-stated functional selling points

Never state uncertain structures as facts. Write `需用户确认` for unclear details.

The `Product Lock Prompt` must lock product shape, proportion, color, material, edge contour, front/side/top/bottom structures, button positions, port positions, hole count, logo position, and any critical visible details. It must also say that only scene, light, background, composition, camera angle, and atmosphere may change.

## Step 2: Selling Point Planning

Only plan sales logic and information hierarchy. Do not create visual concepts.

Do not include:

- Available expression methods
- Constraints
- Scene suggestions
- Visual direction
- Composition
- Lighting
- Props
- Background
- Style

Use this table:

| 图片序号 | 图片类型 | 核心卖点 | 用户要理解什么 | 信息优先级 |
|---|---|---|---|---|

Each image serves one core selling point.

## Step 3: Reference Style Analysis and Style Lock Prompt

Analyze only visual language from reference images, links, brands, or style descriptions.

Allowed analysis dimensions:

- Composition tendency
- Lighting method
- Color system
- Material presentation
- Scene type
- Camera language
- Visual temperament
- Post-production feel

Do not copy specific products, brand logos, packaging, people, text, props combinations, unique layouts, or highly recognizable compositions.

Output:

1. `参考风格拆解`
2. `Style Lock Prompt`

## Step 4: Hero Visual Prompt and Confirmation

Generate one hero/main visual prompt first. This prompt establishes the visual baseline for the whole set.

Use the prompt structure in [templates.md](templates.md):

- 图片目标
- 画面内容
- 产品锁定
- 风格锁定
- 卖点表达
- 构图与镜头
- 文字要求
- 负面词

Ask:

`这个方向是否确认？确认后我将提炼 Master Visual Direction 并进入第二张图。如果还需要调整，请告诉我具体修改方向。`

Stay in Step 4 until explicit confirmation.

## Step 5: Master Visual Direction

After hero visual confirmation, extract the actual visual direction used in the final confirmed hero prompt. Do not merely repeat `Style Lock Prompt`.

Must include:

- Final background color, material, and depth
- Lighting direction and whether there is rim light
- Product position in frame
- Camera distance
- Props, if any
- Text style, if any
- What later images may vary
- What later images may not vary

The `Master Visual Direction` is incomplete if it lacks both `允许变化的范围` and `不允许变化的内容`.

## Step 6: Subsequent Image Prompts

For each later image:

1. Reuse `Product Lock Prompt`.
2. Reuse `Style Lock Prompt`.
3. Reuse `Master Visual Direction`.
4. Use the current image's single selling point from Step 2.
5. Apply the user's current feedback or reference.
6. Output `V1`.
7. Revise based on feedback as `V2`, `V3`, etc.
8. Record the final prompt and revision reason after confirmation.
9. Move to the next image only after confirmation.

## Step 7: Prompt Asset Record

At task completion, output:

- Product name and type
- Image purpose
- Target platform
- Image ratio
- Model, default `GPT Image`
- Final `Product Lock Prompt`
- Final `Style Lock Prompt`
- Final `Master Visual Direction`
- Final negative prompt
- Per-image records: image number, type, selling point, user understanding target, final prompt, revision record, confirmation reason
