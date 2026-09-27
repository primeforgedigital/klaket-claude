---
name: video-ad
description: Make a short AI video ad with Klaket — a product video with an AI presenter or scenes only, 4 to 15 seconds, vertical, square or horizontal, with voiceover and captions in English, Spanish or Portuguese. Use when the user asks for a video ad, a TikTok/Reels/Shorts video, a UGC video, a product video or a video from a product photo or an idea.
---

# Video ads with Klaket

Klaket makes videos in two steps, and the user always approves the scene before the expensive part:
- `create_video` writes the script and makes the scene image (20 credits per scene).
- `render_video` makes the final video and uses most of the credits (the amount is in `render_cost_credits`).

## 1. Brief (ask at most one short question)
- **What**: a saved product (`list_products`, or `create_product` from 1–3 public photo links) or an idea of at least a sentence.
- **Language**: `pt-PT`, `pt-BR`, `es-ES`, `es-MX` or `en-US` — default to the user's language.
- **Length**: any whole number from 4 to 15 seconds (default 15; 7–10 s works well for TikTok hooks).
- **Format**: `9:16` for TikTok/Reels/Shorts (default), `1:1` feed, `16:9` YouTube/web.
- **Sound**: `voiceover` (narration, default), `person_speaking` (needs a `person_id` from `list_people`) or `none`.
- **Engine**: `seedance` (default, any language) or `kling` (keeps a person's exact face; a speaking person only in English).
If the brand name is unusual, pass `pronunciation` (e.g. written "Klaket", spoken "Kla quét") so the voice says it right; captions keep the written name.

## 2. Scenes
Call `create_video`, then `get_video` until `status` is `ready_for_approval`. Show the scene image(s), the spoken text and `render_cost_credits` next to `credits_available`, and **ask the user to approve**. If they want changes, use `update_video_scene` (text) and `redo_scene_image` (new image, 20 credits). If a scene has a `warning` about made-up text, mention it and offer a redo.

## 3. Final video
Only after a clear yes, call `render_video`. It takes about 3 to 8 minutes: check `get_video` every minute or two and give short progress updates. When `status` is `done`, share `video_url` and `studio_url`.

## Rules
- Never create a video of a real, identifiable person or celebrity — offer an AI presenter from `list_people` instead.
- Never invent product claims, reviews, prices or results.
- If a tool says the account has no plan or not enough credits, tell the user plainly and point them to klaket.io.

Reply in the user's language.
