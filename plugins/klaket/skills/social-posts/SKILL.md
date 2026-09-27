---
name: social-posts
description: Create ready-to-post social media posts for a product with Klaket — Instagram, Facebook or TikTok images with headline and button, plus caption, hashtags and ad copy. Use when the user asks for posts, social media creatives, an Instagram post, static ads or captions for something they sell.
---

# Social posts with Klaket

Klaket designs a batch of 4 posts around the product's real photos (feed, 4:5 and story sizes), with a caption, hashtags and ad copy. A batch costs 20 Klaket credits.

1. **Find the product.** Call `list_products`. If the product isn't there, ask for 1 to 3 public photo links (https, JPG/PNG/WebP) and a one-line description, then call `create_product`. Never invent product facts, prices or offers — Klaket only uses what the user gives.
2. **Ask only what's missing** (one short question at most): the language (`pt-PT`, `pt-BR`, `es-ES`, `es-MX` or `en-US`) and the goal (`launch`, `benefit`, `problem_solution`, `offer` or `lifestyle`). Default to the user's language and `benefit`. If the user mentioned an offer, a price or brand colours, pass them in `notes` / `brand_colors`.
3. **Create the batch** with `create_posts`. It takes about a minute: call `get_posts` with the returned `posts_id` until `status` is `ready`.
4. **Show the result**: the 4 post images, then the caption with hashtags, then the ad copy. Keep your own text short — the Klaket view already shows the posts.
5. **Offer the next step**: tweaks in the Klaket editor (the `studio_url`), another batch with a different goal, or a landing page for the same product (see the landing-page skill).

If a tool says the account has no plan or not enough credits, tell the user plainly and point them to klaket.io. Don't retry.

Reply in the user's language.
