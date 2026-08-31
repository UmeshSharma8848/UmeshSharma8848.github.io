# Umesh Sharma — Portfolio Site

A portfolio site for Umesh Sharma.
```
index.html          <- all the text, layout, and styling
resume.pdf          <- the file the "Download resume" buttons hand out
*.jpg               <- the photos on the page
README.md           <- this file
```

Live at https://umeshsharma8848.github.io

---

## How to change things

All of this works from github.com in a browser — no Git, no terminal, no editor.

### Replace your resume

**Add file → Upload files**, drop in the new PDF **named exactly `resume.pdf`**, commit.
GitHub replaces the old one. Both download buttons keep working because they point at
the name, not the file.

> If you upload `Resume_2027.pdf`, the buttons break. Rename it first.

### Add a photo to Beyond work

1. **Add file → Upload files**, drop the photo in, commit. Use a plain lowercase name
   with no spaces: `annapurna-trail.jpg`, not `IMG 2931 (1).jpg`.
2. Open `index.html` → pencil icon → find `<!-- ==== BEYOND WORK ==== -->`.
3. Copy a whole `<figure class="media">` block, paste it below, change the file name
   and the caption. Commit.

```html
<figure class="media">
  <div class="frame"><img src="annapurna-trail.jpg" alt="Describe the photo" loading="lazy"></div>
  <figcaption>Your caption here.</figcaption>
</figure>
```

`class="media"` is a tall portrait tile. `class="media media--wide"` is a landscape
tile spanning two columns. Mix them so the grid stays interesting.

### Add a video to Beyond work

Same section — a ready-made example sits in a comment block. Delete the `<!--` and
`-->` around it and point it at your files:

```html
<figure class="media media--wide">
  <div class="frame">
    <video controls preload="metadata" poster="clip-thumbnail.jpg">
      <source src="clip.mp4" type="video/mp4">
    </video>
  </div>
  <figcaption>Your caption here.</figcaption>
</figure>
```

Upload the `.mp4` like any other file. Two limits: GitHub rejects single files over
100 MB, and GitHub Pages is not built for streaming. **Keep clips under about 20 MB.**
For anything longer, upload to YouTube and paste the embed code in place of `<video>`.

### Swap the big background photo

Upload a new landscape photo, then in `index.html` find `url("rail-crossing.jpg")` —
it appears **twice** (CSS section 3, and the mobile block lower down). Change both.

### Change any text

Open `index.html` and edit between the tags. What you see on the page is what's in
the file. The comment banners — `<!-- ==== ABOUT ==== -->`, `<!-- ==== EDUCATION ==== -->`
and so on — mark where each section begins.

### Change the colors

Top of the file, CSS section 1, the `:root` block. Change `--navy` or `--blue` there
and the whole site follows. Don't hunt for colors anywhere else.

---

## Before you add many more photos

Compress them. The ones already up are 60–300 KB each, which is fine. Straight-off-the-phone
photos are often 4–8 MB and will make the page crawl on mobile data.
[squoosh.app](https://squoosh.app) does it free in a browser — export around 1500px wide.

Write real `alt` text for each one too. It's what a screen reader announces and what
shows if an image fails to load. "Describe the photo" is a placeholder, not alt text.

## Note on current content

The About section says you're *completing* your MS. Once the degree is conferred,
change that to "I hold an MS in Civil Engineering from Oklahoma State University."

Your phone number is deliberately not on the site — public pages get scraped by spam
bots. If you want it, add a line to the contact list in the footer.
