---
name: launch-kit
description: Prepare a full product launch kit with Klaket in one go — social posts plus a landing page for the same product, in the user's language. Use when the user is launching a product, opening a shop, starting a campaign, or asks for "everything I need to promote this".
---

# Product launch kit with Klaket

Goal: leave the user with posts to publish today and a page to send people to — from one conversation.

1. **Check credits first** with `get_account`: posts cost 20 credits and a landing page 100. If the balance is short, say what fits and let the user choose.
2. **Product**: `list_products`, or `create_product` from 1 to 3 public photo links and a short, factual description.
3. **Ask once** for anything missing: language, the page goal (`leads`, `whatsapp` with a number, or `sales` with a store link) and any real offer to feature.
4. **Start both jobs** — `create_posts` and `create_landing_page` — then check `get_posts` and `get_landing_page` until both are ready.
5. **Deliver in this order**: the 4 posts with caption and hashtags, then the landing page. Ask before calling `publish_landing_page`; once published, suggest putting the page link in the post caption and the bio.

Never invent facts, reviews, prices or results. Reply in the user's language.
