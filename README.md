# Iridescence Live 2026 — The Comeback (concert website)

Single-page static site. No build step, no dependencies — plain HTML/CSS.

## Structure

```
iridescence-live-site/
├── index.html          # all content lives here
├── css/styles.css      # all styling (colors/type tokens at the top in :root)
└── assets/
    ├── img/            # hero.jpg, about.jpg (B&W artist portraits)
    └── fonts/          # Anton-Regular.ttf (SIL Open Font License)
```

## Run locally

Open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

## Before launch — checklist

Search `index.html` for these and replace:

1. **Selar ticket links** — `https://selar.com/YOUR-REGULAR-TICKET-SLUG` and
   `https://selar.com/YOUR-VIP-TICKET-SLUG`. Create the event on Selar
   (tickets.selar.com), copy each ticket link, paste here. Also update the
   placeholder prices (₦5,000 / ₦15,000) and remove the "prices are
   placeholders" note.
2. **Contact email** — `hello@iridescencelive.com` appears in the sponsor CTA
   (mailto link) and the venue facts. Swap for the real email, or change the
   sponsor button to a WhatsApp link:
   `https://wa.me/234XXXXXXXXXX?text=Sponsorship%20enquiry%20—%20Iridescence%20Live`
3. **Venue address** — "Full address to be announced" in the venue section.
4. **Social links** — footer Instagram / YouTube / WhatsApp point to `#`.
5. **Sponsor logos** — as sponsors sign on, replace a dashed
   `<div class="slot">Your brand here</div>` with
   `<div class="slot filled"><img src="assets/img/sponsor-name.png" alt="Sponsor name"></div>`
   and add to styles.css:
   `.slot.filled{border-style:solid}.slot img{max-height:60%;max-width:70%;filter:grayscale(1);opacity:.85}`
6. **Partner logos** — same idea for the "Our partners" chips
   (Maeyo Music, Creotribe, ClearEye Media, Nirvana) once logo files arrive.
7. **Iridescence logo** — currently the wordmark is styled text in the nav
   (`.logo`). Swap for an `<img>` when the logo file is ready.

## Deploy (pick one, all free)

- **Netlify**: drag the whole folder onto https://app.netlify.com/drop — done.
- **Vercel**: `npx vercel` from this folder, or import via dashboard.
- **GitHub Pages**: push to a repo → Settings → Pages → deploy from branch.

Then point the domain (e.g. iridescencelive.com) at it via your registrar's
DNS. All three hosts give free HTTPS.

## Design tokens

Colors and fonts are CSS variables at the top of `styles.css` (`:root`) —
change `--grad`, `--cream`, etc. in one place to restyle the whole page.
The display font is Anton (OFL licensed); body text uses the system font stack.
