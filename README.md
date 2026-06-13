# AI Workflow Skills

This repository collects three Codex skills for visual content production workflows: video direction, scene prompt refinement, and ecommerce image prompt generation.

## Skills

### video-director

`video-director` turns product ideas, selling points, rough concepts, or confirmed scripts into cinematic advertising treatments and AI video generation prompts.

It is designed for a two-phase workflow:

- Phase 1: create two distinct director treatments for user selection.
- Phase 2: convert the selected concept or script into a formatted `.xlsx` AI-video prompt workbook for tools such as Jimeng, Kling, Runway, or similar video generation systems.

Best for product ads, brand videos, creative concept development, AI video prompt planning, and director-level narrative treatment.

### scene-prompt-builder

`scene-prompt-builder` refines rough scene ideas, existing AI image or video prompts, reference-image descriptions, and spreadsheet scene cells into structured Chinese and English prompts.

It focuses on local scene improvement while preserving the existing direction. It enriches visual detail, product integration, atmosphere, material, action, environment, and prompt clarity.

Best for improving a single scene, repairing weak prompt text, expanding visual description, or polishing cells produced by `video-director`.

### ecommerce-image-prompts

`ecommerce-image-prompts` generates structured Chinese prompts for ecommerce product images, hero images, ad creatives, feature-benefit images, scene images, and product detail visuals.

It uses a staged workflow: product recognition, product lock prompt, selling-point planning, reference style analysis, hero prompt confirmation, master visual direction, and one-by-one prompt generation.

Best for Amazon, Shopify, TikTok Shop, Temu, Xiaohongshu, independent stores, product hero images, listing visuals, and GPT Image-ready ecommerce prompt production.

## Directory Structure

```text
skills/
  video-director/
  scene-prompt-builder/
  ecommerce-image-prompts/
```

Each skill folder contains a required `SKILL.md` file plus optional `agents/` and `references/` resources.
