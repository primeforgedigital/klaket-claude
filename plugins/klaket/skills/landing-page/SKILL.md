---
name: landing-page
description: Build and publish a product landing page with Klaket, hosted at klaket.io, with a lead form, a WhatsApp button or a link to the user's store. Use when the user wants a landing page, a sales page, a product page, a page to collect leads, or a link to put in their bio or ads.
---

# Landing pages with Klaket

Klaket writes and designs a complete landing page for a saved product and hosts it for the user. A page costs 100 Klaket credits and stays private until it is published.

1. **Find the product** with `list_products` (or create it with `create_product` from 1 to 3 public photo links).
2. **Pick the goal** and collect only what it needs:
   - `leads` — a contact form; leads are emailed to the account owner. Needs nothing else.
   - `whatsapp` — a WhatsApp button; ask for the number in international format (e.g. +351912345678).
   - `sales` — a button to the user's store; ask for the https link.
   Also pass the brand name, an offer or colours only if the user gave them. Never invent prices, discounts, reviews or results.
3. **Create the page** with `create_landing_page`. It takes 1 to 2 minutes: call `get_landing_page` with the `page_id` until `status` is `ready`.
4. **Before publishing, ask the user.** Publishing puts the page on the public internet at its klaket.io link. When they agree, call `publish_landing_page` and share the `public_url`. They can unpublish any time (`published: false`).
5. Mention that the page can be edited in the Klaket editor (`editor_url`).

Reply in the user's language.
