# Your Portfolio

A personal portfolio site for showcasing thumbnail, graphic design, and colour grading work — built to run on GitHub Pages, with an admin panel so you can update everything yourself with no coding.

## What's in this folder

```
index.html         → your public portfolio site
admin.html         → your private editing panel (bookmark this one, don't share the link publicly)
data.json          → the content file — your name, bio, contact info, and work list live here
assets/            → your profile photo and project images
```

## Part 1 — Get it online (10 minutes, one time)

1. Go to [github.com/new](https://github.com/new) and create a new repository.
   - Name it `yourusername.github.io` (using your actual GitHub username) — this gives you the cleanest possible URL: `https://yourusername.github.io`
   - Set it to **Public**
   - Don't add a README, .gitignore, or license — just create the empty repo
2. On the new repo's page, click **Add file → Upload files**.
3. Drag in every file and folder from this download (`index.html`, `admin.html`, `data.json`, and the whole `assets` folder). Commit the upload.
4. Go to **Settings → Pages** (left sidebar).
5. Under **Build and deployment → Source**, choose **Deploy from a branch**. Under **Branch**, choose `main` and folder `/ (root)`. Save.
6. Wait a minute or two, then visit `https://yourusername.github.io` — your site is live.

## Part 2 — Edit your content (no coding)

Open `https://yourusername.github.io/admin.html` in your browser. The first time, it'll ask you to connect:

1. **GitHub username** — your username
2. **Repository name** — `yourusername.github.io` (whatever you named it above)
3. **Branch** — leave as `main`
4. **Personal access token** — this is the one slightly technical step, and you only do it once:
   - On GitHub: **Settings → Developer settings → Personal access tokens → Fine-grained tokens**
   - **Generate new token** → give it any name → set an expiration (a year is fine)
   - **Repository access** → **Only select repositories** → choose your portfolio repo
   - **Permissions → Repository permissions → Contents** → set to **Read and write**
   - **Generate token**, copy it immediately (GitHub only shows it once), and paste it into admin.html

Click **Connect**. From here on, admin.html remembers your login on this device, so you won't need to repeat this step.

Once connected, you can:
- Update your name, role, headline, bio, and specifications
- Upload a new profile photo
- Add, edit, remove, and reorder your work — each project gets a title, category, description, image, and optional link
- Fill in WhatsApp, LinkedIn, Email, Telegram, and Instagram — any left blank simply won't appear on your site

Press **Save changes**. It commits directly to your GitHub repo, and your live site updates automatically within about a minute. Refresh the site to see it.

## A few honest notes

- **Keep your token private.** Anyone who has it could edit your repo. It's stored only in your browser's local storage on this device — never sent anywhere except to GitHub itself. Use the **Disconnect** button if you're on a shared computer, and avoid opening admin.html on devices you don't trust.
- **admin.html is technically visible to anyone** who finds the URL, since it's a public repo — but without your token, nobody can actually save anything through it. If that bothers you, don't link to it from your public site (this build doesn't) and only you need to know the address.
- **Image size:** keep photos under ~2MB each for fast uploads and a fast-loading site. Compress large camera photos first if needed.
- **Replaced images aren't deleted** from the repo automatically — if you swap a project's image repeatedly, old versions quietly stay in the `assets/work` folder. Harmless, but you can delete them manually on GitHub if you want a tidy repo.
- **Social share preview:** the text that shows up when your link is shared (title/description) is set once in `index.html`'s `<head>` and isn't controlled by admin.html. The defaults are generic and safe to leave — but if you want to customize them, that's the one edit that involves opening the actual file (on GitHub.com, click `index.html` → pencil/edit icon → adjust the `og:title` / `og:description` lines near the top → commit).

## If you'd rather skip the admin panel

You can always edit `data.json` directly on GitHub.com: open the file, click the pencil (edit) icon, change the text, and commit. To add images without the admin panel, open the `assets/work` folder and use **Add file → Upload files**, then reference the new filename in `data.json`.

## The particle cube

The rotating grid in the hero is your Three.js particle simulation, adapted to sit in the page rather than fill the screen, recoloured to match the site's black-and-white palette, and set to settle from scattered points into a precise grid. It's decorative — if it ever fails to load (slow connection, old browser), the rest of the site still works normally.
