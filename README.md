# Randula & Thilina — Wedding Invitation

Digital wedding invitation website, hosted free on GitHub Pages.

## Files

```
index.html          the whole invitation (edit details in the "EDIT YOUR DETAILS HERE" block)
assets/
  preview.jpg       WhatsApp / Facebook link preview (1200 x 630) — replace with your own
  couple.jpg        couple photo (portrait, 3:4 works best)
  gallery-1.jpg … gallery-6.jpg
  hero.mp4          background video at the top (10–20 s, muted, under 10 MB)
  intro.mp4         entrance video after the doors open (optional)
  song.mp3          background song
```

Any file that is missing simply shows the built-in placeholder (or the built-in melody / animated intro), so the site never breaks.

## Edit details

Open `index.html`, find `EDIT YOUR DETAILS HERE` and change names, date, venue, `mapLink`, `mapQuery`, WhatsApp number, story, events and the welcome note.
Also update the `og:` lines at the top if your GitHub Pages address is different.

## RSVP with Google Forms (replies go straight into a Google Sheet)

1. Go to https://forms.google.com and create a form with these 5 questions, in this order:
   - **Full name** (Short answer, required)
   - **Attending** (Multiple choice) with exactly two options: `Joyfully accepts` and `Regretfully declines`
   - **Number of guests** (Short answer)
   - **Phone number** (Short answer)
   - **Wish for the couple** (Paragraph)
2. In the form, open **Responses → Link to Sheets** so every reply lands in a spreadsheet.
3. Click the **⋮ menu → Get pre-filled link**, type anything into every question (e.g. `a`), choose `Joyfully accepts`, then **Get link → Copy link**.
4. Send that copied link to Claude (or fill it in yourself): the link contains `entry.123456789=` numbers, one per question.
   In `index.html` set:
   - `action` to the form link with `viewform...` replaced by `formResponse`
     (e.g. `https://docs.google.com/forms/d/e/1FAIpQL.../formResponse`)
   - `name`, `attending`, `guests`, `phone`, `message` to the matching `entry.…` numbers.
5. Commit and push. Guests now tap **Send RSVP**, see a thank-you message, and their reply appears in your Google Sheet.

If `action` is left empty, the RSVP button falls back to WhatsApp.

## Publish on GitHub Pages

1. Create a new **public** repository on GitHub named `randula-thilina`.
2. Upload these files (or push them from your computer):
   ```bash
   git init
   git add .
   git commit -m "Wedding invitation"
   git branch -M main
   git remote add origin https://github.com/Mihiniii/randula-thilina.git
   git push -u origin main
   ```
3. In the repository: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
4. After about a minute the site is live at:
   **https://mihiniii.github.io/randula-thilina/**

Every time you change something, commit and push again; the site updates in a minute.

## Before sending to guests

- Open the link on your own phone: doors, music, video, map and the RSVP button.
- Send it to yourself on WhatsApp to check the preview card.
- Keep videos small (under 10 MB) so guests with slow data can open it quickly.
