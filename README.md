# Fair&Frei Café — Bilingual site with daily-menu carousel

Pure GitHub, no CMS, no OAuth, no build step. Everything is edited directly
through github.com (mobile browser works fine — the GitHub *app* does not
support uploading files, so always use the browser instead).

## File map
```
index.html              → the whole site
content/site.json        → static bilingual text (hero, concept, values,
                            notice, address, footer) — edit occasionally
content/menu/
  slot-1.jpg              → today's menu, photo 1
  slot-1-de.txt           → caption, German
  slot-1-en.txt           → caption, English
  slot-1-alt-de.txt       → image alt text, German (for accessibility)
  slot-1-alt-en.txt       → image alt text, English
  slot-2.jpg / slot-2-*.txt   → photo 2, same pattern
  slot-3.jpg / slot-3-*.txt   → photo 3, same pattern
```

## For the cafe owner — changing today's menu (do this daily)
All from a phone browser (Safari/Chrome), not the GitHub app:

1. Go to the repo on github.com, open the `content/menu` folder.
2. **To change a photo:** open `slot-1.jpg` → tap the pencil/edit icon isn't
   available for images, so instead: tap **Add file → Upload files**, choose
   the new photo from your camera roll, and when GitHub asks about the
   filename, make sure it's still exactly `slot-1.jpg` (it will ask to
   replace the existing file — confirm that). Repeat for `slot-2.jpg` /
   `slot-3.jpg`.
3. **To change the caption:** open `slot-1-de.txt`, tap the pencil (edit)
   icon, delete the old sentence, type the new one, tap **Commit changes**.
   Do the same for `slot-1-en.txt` (English version) and the two `-alt-`
   files (a short plain description of the photo, for people using screen
   readers).
4. **To hide a slide today** (e.g. only 2 dishes instead of 3): open that
   slot's `-de.txt` and `-en.txt` files and delete all the text so the file
   is empty, then commit. The carousel automatically skips empty slots —
   nothing else needs to change.
5. **To bring a hidden slide back:** just type the caption text back in.

There is no JSON to edit for daily changes — every file here is a single
plain sentence, so there's nothing to break.

## For the technical friend — editing permanent site text
Open `content/site.json` in GitHub's web editor. It's one JSON object with
a `de` block and an `en` block — every piece of static text (hero, concept,
values, the membership notice, address, footer) lives in both, side by
side. Keep the quotes and commas intact; this file is only touched
occasionally, not daily, so it's fine for it to require more care.

## Hosting
Already live at `https://fair-frei.github.io/` once these files are in the
`main` branch of that repo, Pages source set to `main` / root, in Settings →
Pages. No further setup needed — this version has no login system at all,
since editing happens through normal GitHub accounts with repo write access
(add the cafe owner as a **Collaborator** in Settings → Collaborators so she
can commit).

## Adding photos for the first time
`slot-1.jpg` through `slot-3.jpg` don't exist yet in this package — upload
the real dish photos the same way as step 2 above. Until a photo exists,
that slide shows a "Foto folgt / Photo coming soon" placeholder instead of
a broken image.
