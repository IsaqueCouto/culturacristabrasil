# Cultura Cristã Brasil — Site Context

## What this is
Single-page institutional website for Cultura Cristã Brasil (CCB), a Brazilian Christian ministry. Built in plain HTML/CSS/JS — no framework, no build step.

**Live domain:** https://www.culturacristabrasil.com.br  
**Hosting:** ValueHost.com.br (cPanel shared hosting)  
**Deploy:** Push to `main` on GitHub → GitHub Actions auto-deploys via FTP

---

## File Structure
```
index.html          ← entire site (HTML + CSS + JS all inline)
assets/
  fonts/            ← Mundial (300–900) + Toska (400, 700)
  logo/             ← Logo__7.svg (navbar + footer)
  images/           ← real photos go here when available
.github/
  workflows/
    deploy.yml      ← FTP deploy on push to main
```

---

## Design System (CSS Variables)
```css
--navy:        #102a37   /* main dark background */
--navy-deep:   #0b1e29   /* footer background */
--teal:        #266882   /* primary brand color */
--teal-light:  #3598b9
--teal-pale:   #58b6e7
--green-start: #178e64   /* gradient accent */
--green-end:   #51d081
--orange:      #ffa300   /* highlight */
--white:       #e8f4fb   /* off-white body bg */
--text-dark:   #0e2230
--text-body:   #3a5060
```

## Fonts
- **Mundial** — primary font (weights: 300 light, 400 regular, 600 demibold, 700 bold, 900 black)
- **Toska** — accent serif (weights: 400 regular, 700 bold)

---

## Page Sections (in order)
1. **Navbar** — fixed, dark navy, logo + 6 links + PT|EN toggle + hamburger
2. **Hero** — `#hero` — full viewport, title "ESTRATÉGIA / VISÃO / CHAMADO", 3 animated cards
3. **Sobre** — `#sobre` — 2-col: text + stats (15+ anos, 200k seguidores, 500+ igrejas) + auditorium image
4. **Especialistas** — `#especialistas` — 4 cards: Celso Flor, Simone Cardoso, Pedro de Jesus, Humberto Cardoso
5. **Parceiros** — `#parceiros` — horizontal scroll of 9 partner logos (text abbreviations for now)
6. **Acompanhe** — `#blog` — 3 video cards (placeholder thumbnails)
7. **Contato** — `#contato` — 2-col: contact info + form
8. **Footer** — logo, nav links, YouTube/Instagram/Facebook icons

---

## Placeholder Content (needs replacing with real data)
- Specialist avatars — initials only, no photos
- Partner logos — text abbreviations (IBB, CPAD, SEJAM, etc.)
- Video thumbnails — CSS gradients, no real images
- Contact info — placeholder phone/email/address
- Photo cards in hero — decorative CSS, no real photos

---

## Deploy Workflow
```bash
# Make changes to index.html
git add .
git commit -m "describe the change"
git push
# → GitHub Actions deploys to ValueHost automatically (~30s)
```

## GitHub Secrets Required (set in repo Settings → Secrets)
- `FTP_HOST` — FTP server from ValueHost (e.g. ftp.culturacristabrasil.com.br)
- `FTP_USER` — FTP username from cPanel
- `FTP_PASS` — FTP password from cPanel
