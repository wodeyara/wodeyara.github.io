# Anirudh Wodeyar — academic website

A simple, fast academic website plus a Markdown blog. It is just plain HTML, CSS,
and a little JavaScript — no frameworks, no build step — so it is easy to host for
free and easy to edit. Blog posts are written in **Markdown** (the same simple format
you can write and preview in RStudio).

## What's in this folder

| File / folder | What it is |
|------|------------|
| `index.html` | The home page (about, research, publications, contact). Edit text here. |
| `blog.html` | The blog index — automatically lists every post. You don't normally edit this. |
| `post.html` | Displays a single blog post. You don't normally edit this. |
| `posts/` | Your blog posts live here: one `.md` (Markdown) file per post, plus `posts.json`. |
| `posts/posts.json` | The list of posts (title, date, summary). Add one entry per new post. |
| `style.css` | The look and feel (colors, fonts, layout). |
| `marked.min.js` | The little library that turns your Markdown into a web page. Leave it alone. |
| `profile.jpg` | **You add this** — your headshot. Until you do, the site shows your initials "AW". |
| `cv.pdf` | **You add this** — your CV. The "CV" links open it. |
| `.nojekyll` | A small empty file that tells GitHub to serve the site as-is. Leave it alone. |
| `README.md` | This guide. |

---

## Part 1 — Add your photo and CV (optional but recommended)

1. **Photo:** put a square-ish headshot named exactly `profile.jpg` into this folder.
   (If you prefer a `.png`, name it `profile.png` and change `src="profile.jpg"` to
   `src="profile.png"` near the top of `index.html`.)
2. **CV:** drop a PDF named exactly `cv.pdf` into this folder.

That's it — the site automatically picks them up. If you skip these, the page still
works: it shows your initials instead of a photo, and the CV link simply won't open
anything yet.

---

## Part 2 — Preview it on your own computer first

Just **double-click `index.html`** — it opens in your web browser and looks exactly
as it will online. Edit the text in `index.html`, save, and refresh the browser to
see changes. No tools required.

---

## Part 3 — Put it online for free with GitHub Pages

GitHub Pages hosts simple websites like this one for free, at an address such as
`https://yourusername.github.io`. Below is the **no-command-line** way, which is the
easiest if you have not done this before.

### Step 1 — Make a free GitHub account
Go to <https://github.com> and sign up (skip if you already have one). Pick a
username you are happy with — **it becomes part of your website address.**

### Step 2 — Create a repository with a special name
1. Click the **+** in the top-right of GitHub → **New repository**.
2. For **Repository name**, type your username followed by `.github.io`, all lowercase.
   For example, if your username is `awodeyar`, name it exactly:
   ```
   awodeyar.github.io
   ```
   > This exact name is what tells GitHub to publish it as your personal website at
   > `https://awodeyar.github.io`.
3. Set it to **Public**.
4. Leave everything else unchecked and click **Create repository**.

### Step 3 — Upload these files
1. On the new repository page, click the **uploading an existing file** link
   (or **Add file → Upload files**).
2. Open this `academic-website` folder in Finder, select **all the files inside it**
   (including your `profile.jpg`, `cv.pdf`, and the `.nojekyll` file), and **drag them
   into the browser** upload area.
   - If you don't see `.nojekyll` in Finder, press **Cmd+Shift+.** to show hidden files.
3. Scroll down and click **Commit changes**.

### Step 4 — Turn on GitHub Pages
1. In the repository, go to **Settings** (top menu) → **Pages** (left sidebar).
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Set the branch to **`main`** and the folder to **`/ (root)`**, then click **Save**.

### Step 5 — Visit your site 🎉
Wait about 1–2 minutes, then open:
```
https://yourusername.github.io
```
(using your real username). Done — your website is live.

---

## How to make changes later

1. In your repository on GitHub, click the file you want to change (e.g. `index.html`).
2. Click the **pencil ✏️ icon** to edit it in the browser.
3. Make your edits and click **Commit changes**.
4. The live site updates automatically within a minute or two.

To **add a new publication**, copy one of the `<li>…</li>` blocks inside the
`<ol class="pub-list">` list in `index.html`, paste it at the top, and change the text.

To **change colors**, edit the variables at the very top of `style.css` (the
`--accent` line controls the main blue).

---

## Writing a new blog post

Posts are plain **Markdown** files in the `posts/` folder. Writing one takes two steps.

### Step 1 — Write the post
Create a new file in the `posts/` folder named with lowercase letters, numbers, and
hyphens — for example `posts/my-new-idea.md`. Write your post in Markdown. A quick
cheat-sheet:

```markdown
This is a normal paragraph. Leave a blank line between paragraphs.

## A subheading

Some **bold text**, some *italics*, and a [link](https://example.com).

- a bullet
- another bullet

> A quoted line.

![A caption for an image](../posts/my-figure.png)
```

> **Tip:** Don't put the post's title at the top of the Markdown — the title and date
> come from `posts.json` (next step), so the page adds them for you automatically.
>
> To include a **picture**, drop the image file into the `posts/` folder and reference
> it as `![caption](../posts/filename.png)`. Videos work too:
> `<video src="../posts/clip.mp4" controls></video>`.

You can preview the Markdown as you write it right inside **RStudio** (open the `.md`
file and use its visual/preview mode).

### Step 2 — Add it to the list
Open `posts/posts.json` and add an entry at the **top** of the list (newest first).
Copy an existing block and change the four fields. For example:

```json
[
  {
    "slug": "my-new-idea",
    "title": "My new idea",
    "date": "2026-06-15",
    "summary": "One sentence describing the post, shown on the blog index."
  },
  ... (the existing posts stay below) ...
]
```

- **`slug`** must match the file name without `.md` (here, `my-new-idea`).
- **`date`** is `YYYY-MM-DD`.
- Remember the comma between entries (every entry except the last one needs a trailing comma).

That's it. Commit both files (the new `.md` and the updated `posts.json`) and your post
appears on the blog within a minute or two. **No other file needs to change.**

> **Previewing the blog on your own computer:** because blog posts load dynamically,
> simply double-clicking `blog.html` will show a "local preview note" instead of the
> posts — that's expected and only happens locally. The blog works perfectly once it is
> on GitHub. (If you want a true local preview, ask your browser to open the folder
> through a small local web server.)

---

## Optional — use your own domain (anirudhwodeyar.com)

If you later want the site to appear at your own domain instead of
`yourusername.github.io`:

1. In your repository: **Settings → Pages → Custom domain**, enter your domain, **Save**.
2. At your domain registrar (where you bought the domain), add the DNS records GitHub
   shows you (four `A` records for the apex domain, or a `CNAME` record for `www`).
3. Tick **Enforce HTTPS** once it becomes available.

GitHub's full guide: <https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site>

---

## A note on the publication list

The publications in `index.html` were compiled from your Google Scholar profile.
Please skim them once for accuracy — especially **author order** on co-authored papers —
and feel free to add direct links by wrapping a title in a link, like:
`<a href="https://doi.org/...">Title here.</a>`
