# Umesh Sharma — portfolio site

A single-page static site. No build step, no framework, nothing to install.

```
index.html      <- all the text, layout, and styling
resume.pdf      <- the file the "Download resume" buttons hand out
images/         <- every photo and video on the page
README.md       <- this file
```

**The `images` folder must be uploaded too.** If only `index.html` goes up, every
photo on the page breaks. They are separate files, linked by name.

## Putting it online

1. Create a GitHub repository named exactly `umeshsharma8848.github.io`
   (your username + `.github.io`). That name gets you `https://umeshsharma8848.github.io`
   with no `/repo-name/` on the end.
2. **Add file → Upload files**, then drag in `index.html`, `resume.pdf`, and the
   `images` folder together. Dragging the folder keeps the structure. Commit.
3. Repo → **Settings** → **Pages** → Source: branch `main`, folder `/ (root)` → Save.
4. Wait a minute, then load the URL.

Every change you commit goes live within a minute or two. There is no publish step.

---

## How to change things

All of this works from github.com in a browser — no Git, no terminal, no editor.

### Replace your resume

**Add file → Upload files**, drop in the new PDF **named exactly `resume.pdf`**, commit.
Both download buttons keep working because they point at the name, not the file.

> If you upload `Resume_2027.pdf`, the buttons break. Rename it first.

### Add a photo to Beyond work

1. Upload the photo into `images/`. Use a plain lowercase name with no spaces:
   `annapurna-trail.jpg`, not `IMG 2931 (1).jpg`.
2. Open `index.html` → pencil icon → find `<!-- ==== BEYOND WORK ==== -->`.
3. Copy a whole `<figure class="media">` block, paste it below, change the file name
   and the caption.

```html
<figure class="media">
  <div class="frame"><img src="images/annapurna-trail.jpg" alt="Describe the photo" loading="lazy"></div>
  <figcaption>Your caption here.</figcaption>
</figure>
```

`class="media"` is a tall portrait tile. `class="media media--wide"` is a landscape
tile that spans two columns. Mix them so the grid stays interesting.

### Add a video to Beyond work

Same section — there's a ready-made example sitting in a comment block. Delete the
`<!--` and `-->` around it, then point it at your files:

```html
<figure class="media media--wide">
  <div class="frame">
    <video controls preload="metadata" poster="images/clip-thumbnail.jpg">
      <source src="images/clip.mp4" type="video/mp4">
    </video>
  </div>
  <figcaption>Your caption here.</figcaption>
</figure>
```

Upload the `.mp4` to `images/` like any other file. Two limits worth knowing:
GitHub rejects single files over 100 MB, and GitHub Pages is not built for streaming.
**Keep clips under about 20 MB.** For anything longer, upload it to YouTube and paste
the embed code in place of the `<video>` tag instead.

### Swap the big background photo

Upload a new landscape photo to `images/`, then in `index.html` find
`url("images/rail-crossing.jpg")` — it appears **twice** (CSS section 3, and the
mobile block lower down). Change both.

### Change any text

Open `index.html` and edit between the tags. What you see on the page is what's in
the file. The comment banners — `<!-- ==== ABOUT ==== -->`, `<!-- ==== EDUCATION ==== -->`
and so on — mark where each section begins.

### Change the colors

Top of the file, CSS section 1, the `:root` block. Change `--navy` or `--blue` there
and the whole site follows. Don't hunt for colors anywhere else.

---

## Before you add many more photos

Compress them. The ones already in `images/` are about 150–300 KB each, which is fine.
Straight-off-the-phone photos are often 4–8 MB and will make the page crawl on mobile
data. [squoosh.app](https://squoosh.app) does it free in a browser — export around
1500px wide.

Also write real `alt` text for each one. It's what a screen reader announces and what
shows if the image fails to load. "Describe the photo" is a placeholder, not alt text.

## Note on current content

The About section says you're *completing* your MS. Once the degree is conferred,
change that to "I hold an MS in Civil Engineering from Oklahoma State University."

Your phone number is deliberately not on the site — public pages get scraped by spam
bots. If you want it, add a line to the contact list in the footer.
