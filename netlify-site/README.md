# Arnab Sen — Portfolio (with live editable admin panel)

## What this is
A website where you can log into `/admin` on your live site, click to edit any
text, and upload photos/CV/certificates — and it publishes for every visitor
automatically. Powered by Decap CMS (free, works with your existing Netlify +
GitHub setup).

## One-time setup (do this once in your Netlify dashboard — no code)

1. **Push these files to your GitHub repo** (the one already connected to
   Netlify). Keep the folder structure exactly as-is:
   ```
   index.html
   admin/index.html
   admin/config.yml
   content/hero.json
   content/about.json
   content/contact.json
   content/education.json
   content/skills.json
   content/projects.json
   content/gallery.json
   content/certificates.json
   images/uploads/   (empty folder — this is where uploaded photos land)
   ```

2. **Check your default branch name.** If your GitHub repo's default branch
   is `master` instead of `main`, open `admin/config.yml` and change the line
   `branch: main` to `branch: master`.

3. **Turn on Netlify Identity:**
   - Netlify dashboard → your site → **Site configuration** → **Identity** → **Enable Identity**

4. **Turn on Git Gateway** (lets Identity users publish content without a
   personal GitHub account):
   - Same Identity settings page → **Git Gateway** → **Enable Git Gateway**

5. **Restrict signups to invite-only** (so strangers can't create admin accounts):
   - Identity settings → **Registration** → set to **Invite only**

6. **Invite yourself:**
   - Identity tab (top of your site's Netlify dashboard, next to Deploys) →
     **Invite users** → enter your email
   - Check your email, click the invite link, set a password

7. **Go to `yoursite.netlify.app/admin`**, log in, and you'll see all 8
   sections listed on the left. Click any one to edit text or upload files,
   then hit **Publish** — Netlify rebuilds and your live site updates in
   under a minute.

## Editing day-to-day
Just visit `/admin` any time, log in, click a section, change what you want,
click Publish. No code, no GitHub interface needed after today.

## Notes
- Uploaded images/files are stored in `images/uploads/` in your GitHub repo —
  Netlify serves them from there automatically.
- The contact form on the site currently only shows an on-screen confirmation;
  it does not email you. Ask if you'd like this wired up to a free service.
- If a section shows "No ___ added yet," it just means that content file is
  empty — add an entry from `/admin` and it'll appear.
