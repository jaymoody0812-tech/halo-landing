# Substack Auto-Publish Setup

Two steps to activate. Takes 5 minutes.

---

## Step 1 — Get your Substack email-to-post address

1. Go to substack.com/@jacobmoody2
2. Click **Dashboard** → **Settings** → **Publishing**
3. Scroll to "**Post via email**" — there will be a secret email like `draft-xxxxx@posts.substack.com`
4. Copy that address

---

## Step 2 — Set two GitHub Secrets

1. Go to: https://github.com/jaymoody0812-tech/halo-landing/settings/secrets/actions
2. Click **New repository secret** → add these two:

| Name | Value |
|------|-------|
| `SUBSTACK_EMAIL` | The `draft-xxxxx@posts.substack.com` address from Step 1 |
| `GMAIL_APP_PASSWORD` | A Gmail app password (Google Account → Security → 2-Step Verification → App passwords → create one, copy it) |

---

## How it works after setup

1. Write a new post as a `.md` file in the `posts/` folder (see the 3 existing examples)
2. First line must be `# Your Title Here`
3. Blank line, then the body
4. Push it (or drag-drop on GitHub)
5. GitHub automatically emails it to Substack → appears as a **draft** in your Substack dashboard
6. Open Substack, review it, hit Publish

---

## The 3 articles ready to post

These are already in `posts/` — they're written and ready:

- `01-origin.md` — "I built a mood tracker because I was trying not to disappear"
- `02-data.md` — "What the numbers actually say (and why half of it was silence)"
- `03-tools.md` — "Three tools I built. All free. Here's why."

To post any of these: go to **Settings → Secrets** (above), add the two secrets, then open the article on GitHub, edit one character (like adding a blank line at the end), and commit. The Action will fire and send it to Substack as a draft.

---

*The workflow file is at `.github/workflows/publish-to-substack.yml`*
