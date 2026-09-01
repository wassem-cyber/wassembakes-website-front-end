---
name: reel-drop
description: The full launch checklist for a new Wassem Bakes reel — the blog post/recipe, the photos, the social captions, and the BabyChat comment→DM automation (keyword spellings, rotating public replies, DM with a button, the link, and a closer DM). Invoke when Wassem says he's dropping/posting a new reel, launching a recipe, or "setting up the automation" for a post.
---

# Reel Drop Skill

Everything that has to happen when Wassem posts a new reel, in one place, so nothing gets missed and it's done the same way every time. Voice and brand rules come from the `sensible-brand` skill — read it first. Blog/recipe mechanics come from the `blog-post` and `recipe` skills.

A reel drop has **four deliverables**. Do them in this order.

## 1. Blog post / recipe

- If the reel is a recipe → use the `recipe` skill. Otherwise → `blog-post` skill.
- Always include cups **and** grams in recipe ingredient tables (Amount column + Weight column). Simplicity is the point.
- The post URL is the link the BabyChat automation will send. Note it.

## 2. Photos

- Hero (post-hero) + recipe-card flatlay, each at 480/800/1200w responsive variants.
- Add the `image` field to `blog/posts.json` so the blog index card shows a thumbnail.
- Pull originals from the Drive folder Wassem shares; skip any cover/thumbnail that has text baked in (those are for social, not the site).

## 3. Social captions

- One per platform: Instagram, TikTok, YouTube (title + description), Snapchat.
- Wassem's voice, from `sensible-brand`. No food-blogger preamble.
- Include the blog URL and 3–5 relevant hashtags (e.g. #glutenfreebaking #veganbaking #eggfreebaking).

## 4. BabyChat automation (the comment → DM flow)

This is the money step. One automation does the whole flow. Set it up in Studio → BabyChat → Automations → + New.

### The flow it runs
Someone comments the keyword → public reply under their comment (rotated, so it looks human) → DM them the **ask** with a button → they tap the button → the same automation sends the **link** → (optional) a **closer** DM.

### a) Trigger words — several spellings
Real people misspell. List the correct word plus the common typos, comma-separated, all lowercase. Aim for 6–10.

Example for "chocolate":
```
chocolate, chocolat, choclate, choclat, chocolatte, chocholate, chocalate, choco, choc, recipe
```
Rules for generating spellings: drop a letter (choclate), double a letter (chocolatte), swap common vowels (chocalate), phonetic (chocholate), plus short forms (choc, choco) and the generic fallback ("recipe").

### b) Public replies — rotate many, so Instagram doesn't flag you
Instagram flags an account that posts the **same** comment reply over and over. So write **~20 short, warm, varied** public replies. The automation rotates through them. Keep each under ~90 characters, at most one emoji, no link.

Bank of styles to vary across (mix them, don't repeat a pattern):
- "Just sent it to your DMs! 💌"
- "Check your DMs 👀"
- "In your inbox now 🧡"
- "Sent! Go peek at your messages"
- "DM'd you — enjoy!"
- "It's in your DMs, friend 🙌"
- "Just slid it into your DMs"
- "Sent your way ✨"
- "Check your inbox 💛"
- "On its way — check DMs"
- …generate ~20 total, no two alike.

The Studio editor takes all of these in one **"Public replies — one per line"** box, up to **20**. Paste the whole bank.

### c) The DM ask — 10 variations, no link, with a button
The **first DM must not contain the link** (Instagram flags one-way link blasts). It asks a question and offers a button they tap. Write **~10** warm variations that rotate.

Ask examples (vary them):
- "You want the recipe for the chocolate bars? Tap below 👇"
- "Ready for the recipe? Hit the button 👇"
- "Want me to send it over? Tap below"
- "Say the word and it's yours 👇"
- …generate ~10 total.

**Button text (what they tap):** short, first-person, e.g. `Yes, send it over!` (≤20 chars). Tapping it sends that text back — the two-way reply is what keeps the account safe — and the same automation then delivers the link.

The Studio editor takes these in one **"DM message — one per line"** box, up to **10**. Paste them all.

### d) The link
Fill **"When they tap, send this link"** in the *same* automation: label (e.g. `Get the recipe`) + the blog URL from step 1. Optional message sent with it (e.g. `Here you go 🧡`). Never make a second automation for the link — it lives here.

### e) The closer DM (optional last touch)
After the link, a short warm closer keeps the relationship going without being pushy. Best practice: **gratitude + one low-pressure CTA**, and keep the CTA on-platform (Instagram likes engagement).

Keep it content-agnostic — a drop might be a recipe OR just a tip, so avoid "if you make it/bake it." Use "try it / give it a go / try it out."

Good closers (pick/rotate):
- "Thanks so much for the support 🧡 Tag me @wassembakes when you try it — I repost every one!"
- "Thanks for the support 🧡 If you give it a go, tag @wassembakes — I repost every one!"
- "Really appreciate you 🧡 Tag me @wassembakes when you try it out!"
- "Want one of these every week? Join the newsletter 👉 wassembakes.com"
- Soft cross-sell only when it fits: a related recipe, the recipe builder, or the bakery.

Default recommendation: **"Thanks so much for the support 🧡 Tag me @wassembakes when you try it — I repost every one!"** (warm, drives a tag, works for a recipe or a tip, no hard sell).

Enter it in the editor's **"Closer DM (optional)"** box. It's sent a moment after the link. Leave blank to skip.

## Voice
All copy — public replies, DMs, captions, closer — follows `sensible-brand`: warm, plainspoken, no hype, no flattery, Wassem's real voice from his reels. Vary wording heavily in the reply/DM banks; identical repetition is what gets flagged.

## Checklist to run every drop
1. Blog post / recipe published (cups + grams).
2. Photos: hero + flatlay variants, `image` in posts.json.
3. Captions: IG / TikTok / YouTube / Snapchat.
4. BabyChat automation: keyword spellings · up to 20 public replies · up to 10 DM variations + button · link · closer.
5. Give Wassem the exact copy to paste into Studio for anything the tools can't set directly.
