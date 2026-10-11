# Randula & Thilina — Wedding Invitation

Digital wedding invitation website for **27 January 2027**, hosted free on GitHub Pages.

**Live site:** https://mihiniii.github.io/randula-thilina/

## Guest links

`links.html` is a helper page that makes a personal invitation link for each guest:
https://mihiniii.github.io/randula-thilina/links.html

Guest names are saved only in the browser of the person using the page, never on GitHub.

## What guests see

1. **Cover** — full-screen photo with the couple's names and date.
2. **Open invitation** — a little fairy flies out of the button sprinkling dust, then the intro video plays full screen (with a **Skip** button at the top right). On iPhone a **Watch full screen** button appears.
3. **Sparkle reveal** — when the video ends, the invitation opens: names with the guest's name, welcome note, countdown, events, our story gallery, venue map and RSVP.
4. **Music** — the song starts with the video and keeps playing; the round button at the bottom right pauses / plays it.
5. **Petals** — soft petals fall once the invitation is open.

## Files

```
index.html            the whole invitation (edit details in the "EDIT YOUR DETAILS HERE" block)
links.html            helper page to create personal links for each guest (not for guests)
assets/
  cover.jpg           opening cover photo (full screen)
  preview.jpg         WhatsApp / Facebook link preview (1200 x 630)
  intro.mp4           entrance video after "Open invitation" (no sound, keep under 10 MB)
  intro-poster.jpg    first frame shown while the video loads
  song.mp3            background song
  couple.jpg          photo beside the names (portrait, 3:4)
  band.jpg            wide photo band between sections
  events.jpg          events section photo
  rsvp.jpg            RSVP section photo
  story-1.jpg … story-8.jpg   "our story" gallery (arch frames)
  bq1.png, bq2.png    watercolour flower bouquets
```

To change a photo, replace the file with a new one **using the same name** (lowercase, `.jpg`).

## Edit details

Open `index.html`, find `EDIT YOUR DETAILS HERE` (near the bottom) and change:

| Setting       | What it is                                              |
|---------------|---------------------------------------------------------|
| `date`, `end` | ceremony start / end time (used for countdown and calendar) |
| `venue`, `mapQuery`, `mapLink` | venue name, embedded map, "Get directions" link |
| `rsvpFormUrl` | Google Form link opened by **Reply to the invitation** |
| `whatsapp`    | phone number shown under the RSVP button                |
| `introVideo`, `introPoster`, `song` | video, poster and music files     |
| `gallery`     | story photos with their titles and captions             |

Names, the welcome note and other text are written directly in the HTML. Also update the `og:` lines at the top if the site address changes.

## RSVP (Google Form)

1. Create a form at https://forms.google.com (name, attending, number of guests, phone, wishes).
2. In the form, open **Responses → Link to Sheets** so every reply lands in a spreadsheet.
3. Click **Send → link** and copy it into `rsvpFormUrl` in `index.html`.

The **Reply to the invitation** button opens the form in a new tab.

## Personal guest links

Each guest can get a link with their name, e.g.

```
https://mihiniii.github.io/randula-thilina/#Sachini-and-Family
```

The invitation then says *request the honour of the presence of* **Sachini and Family**. Hyphens become spaces; `?to=Name` also works. No push is needed to make new links.

To make links for everyone at once:

1. Open **links.html** (link above).
2. Paste the guest list, one name per line, and press **Create links**.
3. For each guest: **Preview**, **Copy link**, **Copy message**, or **WhatsApp** (opens WhatsApp with the full invitation message filled in).
4. Edit the WhatsApp message box if needed — `{name}` and `{link}` are replaced automatically.

The guest list and message are remembered in your browser, so you can come back later.

## Try it on your computer

Open a terminal in this folder and run:

```bash
python -m http.server 8000
```

Then open http://localhost:8000 (or http://localhost:8000/#Your-Name to test a personal link) and http://localhost:8000/links.html.

## Publish changes

Work only inside the cloned `rt-site` folder. GitHub Pages updates the live site automatically after every push:

```powershell
cd C:\Users\LENOVO\Downloads\rt-site
git status
git add -A
git commit -m "Describe your change"
git push
```

The site updates in 1–2 minutes. A phone that opened it before may show the old version for up to 10 minutes; check in a private tab.

## Before sending to guests

- Open the link on your own phone (iPhone and Android): cover, fairy dust, video, Skip, music, petals, map and RSVP.
- Open a personal link and check the guest's name.
- Submit the Google Form once and check the response arrives.
- Send a link to yourself on WhatsApp to check the preview card.
- Send to a few people first, then to everyone in small batches.