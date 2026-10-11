# Randula & Thilina — Wedding Invitation

Digital wedding invitation website for **27 January 2027**, hosted free on Netlify.

**Live site:** https://randula-thilina.netlify.app/

## Guest links

`links.html` is a private helper page that makes a personal invitation link for each guest.
It is kept out of this repository on purpose, so the guest list stays private.

## What guests see

1. **Cover** — full-screen photo with the couple's names and date. A personal link shows *Dear {guest name}* on top.
2. **Open invitation** — a little fairy flies out of the button sprinkling dust, then the intro video plays full screen (with a **Skip** button at the top right).
3. **Sparkle reveal** — when the video ends, the invitation opens: welcome, events, our story gallery, venue map and RSVP.
4. **Music** — the song starts after the guest taps; the round button at the bottom right pauses / plays it.

## Files

```
index.html            the whole invitation (edit details in the "EDIT YOUR DETAILS HERE" block)
links.html            helper page to create personal links for each guest (kept on my computer, not in this repo)
assets/
  cover.jpg           opening cover photo (full screen)
  preview.jpg         WhatsApp / Facebook link preview (1200 x 630)
  intro.mp4           entrance video after "Open invitation" (keep under 10 MB)
  intro-poster.jpg    first frame shown while the video loads
  song.mp3            background song
  couple.jpg          welcome section photo (portrait, 3:4)
  band.jpg            wide photo band between sections
  events.jpg          events section photo
  rsvp.jpg            RSVP section photo
  story-1.jpg … story-8.jpg   "our story" gallery
```

To change a photo, replace the file with a new one **using the same name**.

## Edit details

Open `index.html`, find `EDIT YOUR DETAILS HERE` (near the bottom) and change:

| Setting       | What it is                                              |
|---------------|---------------------------------------------------------|
| `date`, `end` | ceremony start / end time (used for countdown and calendar) |
| `venue`, `mapQuery`, `mapLink` | venue name, embedded map, "Open in Maps" link |
| `rsvpFormUrl` | Google Form link opened by **Reply to the invitation** |
| `whatsapp`    | phone number shown under the RSVP button                |
| `introVideo`, `introPoster`, `song` | video, poster and music files     |
| `gallery`     | story photos with their titles and captions             |

Names and other text are written directly in the HTML. Also update the `og:` lines at the top if the site address changes.

## RSVP (Google Form)

1. Create a form at https://forms.google.com (name, attending, number of guests, phone, wishes).
2. In the form, open **Responses → Link to Sheets** so every reply lands in a spreadsheet.
3. Click **Send → link** and copy it into `rsvpFormUrl` in `index.html`.

The **Reply to the invitation** button opens the form in a new tab.

## Personal guest links

Each guest can get a link with their name, e.g.

```
https://randula-thilina.netlify.app/#Sachini-and-Family
```

The cover then shows **Dear Sachini and Family**. Hyphens become spaces; `?to=Name` also works.

To make links for everyone at once:

1. Open **links.html** (shared privately with the couple).
2. Paste the guest list, one name per line, and press **Create links**.
3. For each guest: **Preview**, **Copy link**, **Copy message**, or **WhatsApp** (opens WhatsApp with the full invitation message filled in).
4. Edit the WhatsApp message box if needed — `{name}` and `{link}` are replaced automatically.

The guest list is remembered in your browser, so you can come back later.

## Try it on your computer

Open a terminal in this folder and run:

```bash
python -m http.server 8000
```

Then open http://localhost:8000 (or http://localhost:8000/#Your-Name to test a personal link) and http://localhost:8000/links.html.
Opening `index.html` by double-clicking also works, but the video and music behave more like the real site through a local server.

## Publish changes

1. Save the code to GitHub:

   ```bash
   git add .
   git commit -m "Describe your change"
   git push
   ```

2. Update the live site on Netlify:
   - Make a folder with only `index.html`, `links.html` and the `assets` folder (do not include the `.git` folder).
   - Drag that folder onto the **Deploys** page of the Netlify project.

The site updates in a few seconds.

## Before sending to guests

- Open the link on your own phone (iPhone and Android): cover, fairy dust, video, Skip, music, map and RSVP.
- Open a personal link and check the *Dear …* name.
- Send a link to yourself on WhatsApp to check the preview card.
- Keep the video small (under 10 MB) so guests with slow data can open it quickly.