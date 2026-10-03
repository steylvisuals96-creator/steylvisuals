---
name: premium-website
description: "Bouw of upgrade een premium website ('$10.000-website') zonder code, met Claude als bouwer. Gebruik deze skill wanneer de gebruiker vraagt om een website, landingspagina, homepage of sectie te bouwen, te herontwerpen, 'premium' of 'high-end' te maken, een PRD/briefing voor een site te schrijven, scroll-animaties of motion toe te voegen, of een site live te zetten op een eigen domein. Werkt volgens de 5 pijlers: strategie, custom design, custom motion, mobiel responsive en 'het werkt echt' (formulier → CRM/e-mail, eigen domein)."
---

# Premium Website Builder ($1.000 → $10.000)

Gebaseerd op de video "Build a $10,000 website with Claude Code" (WeAreNoCode,
https://www.youtube.com/watch?v=qTWOkhytG0M). De kern: een site is pas $10.000
waard als hij **niet alleen mooi is, maar een doel dient, uniek oogt, beweegt,
overal werkt en technisch echt aangesloten is**.

## Standaardcontext (SteylVisuals)

Tenzij de gebruiker iets anders zegt, bouw je voor **SteylVisuals**: vastgoedvideo's
die opvallen én converteren. De huidige site is één statisch bestand (`index.html`)
met assets in `images/`, `logo/` en `videos/`. Lees `index.html` eerst en hergebruik
bestaande kleuren, lettertypes en teksten in plaats van nieuwe te verzinnen.

## De 5 pijlers (elke build moet ze alle 5 halen)

1. **Strategie.** Elke pagina heeft één primair doel en één primaire CTA.
   Voorbeelden: e-mail verzamelen, gesprek boeken, offerte aanvragen, app downloaden.
   Geen doel = geen build. Vraag het als het niet duidelijk is.
2. **Custom design.** Mag er niet uitzien als een standaard template of een
   "typische AI-site". Zie *Anti-AI-look regels* hieronder.
3. **Custom motion.** Beweging met een reden: scroll-animaties, reveal-on-scroll,
   parallax, hover-states, interactieve hotspots (bv. een klik die iets opent of
   van kleur wisselt). Subtiel en vloeiend, nooit schokkerig.
4. **Mobiel responsive.** Goed op desktop, telefoon én tablet. Controleer het
   echt (zie stap 5), neem het niet aan.
5. **Het werkt echt.** Formulieren versturen echt data naar een CRM, mailtool of
   inbox; links en knoppen werken; de site draait op een eigen domein.

## Werkwijze

### Stap 1: Strategie-intake (kort)
Leg vast, uit het gesprek of met hooguit 3 vragen:
- Doel en primaire CTA van de pagina
- Doelgroep (bv. makelaars, projectontwikkelaars, luxury vastgoed)
- Hero-visual: één sterk beeld of één sterke video waar de hele site omheen
  ontworpen wordt. In de video was dat één foto (een Lamborghini in een showroom),
  waaruit de hele stijl volgde.

### Stap 2: Schrijf een PRD (product requirements document)
Bouw nooit vanaf een prompt van één zin. Schrijf eerst een PRD met
`references/prd-template.md` en laat de gebruiker hem kort bevestigen bij een
nieuwe site. Bij een kleine aanpassing mag je meteen bouwen.
Houd de eerste versie klein: **3 secties** is genoeg om de stijl neer te zetten:
1. Hero (visual + belofte + CTA)
2. Story-sectie (bv. beeldverhaal, portfolio, "zo werkt het")
3. Call-to-action-sectie (formulier of boekingsknop)

### Stap 3: Bouw versie 1
- Volg de PRD exact. Gebruik echte assets uit de repo en geen placeholders als
  er echt materiaal is.
- Zet kleuren en fonts als CSS-variabelen op `:root`.
- Gebruik semantische HTML, alt-teksten en lazy loading voor media.
- Video in de hero: `autoplay muted loop playsinline` plus een poster-afbeelding.

### Stap 4: Upgrade van $1.000 naar $10.000
Loop `references/10k-checklist.md` volledig door en verbeter alles wat faalt.
Dit is de stap die het verschil maakt. Sla hem niet over.

### Stap 5: Controleer responsiveness met echte screenshots
Maak met Playwright (Chromium staat al klaar) screenshots op deze 3 breedtes en
bekijk ze:
- Desktop 1440×900
- Tablet 820×1180
- Telefoon 390×844

Let op horizontale scroll, overlappende tekst, te kleine knoppen (<44px) en een
CTA die onder de vouw verdwijnt op mobiel. Fix alles en controleer opnieuw.

### Stap 6: Laat het echt werken
- **Formulier:** koppel aan een echte bestemming (Formspree, Netlify Forms,
  Web3Forms, of via Zapier/webhook naar een CRM zoals HubSpot of Brevo).
  Vraag de gebruiker welke dienst hij gebruikt. Verzin geen endpoint en zet
  geen API-sleutels in de code.
- **Deploy en domein:** statische sites kunnen naar GitHub Pages, Netlify of
  Vercel. Leg de DNS-stappen uit (A/CNAME-records bij de registrar) en
  controleer HTTPS.
- **SEO-basis:** `<title>`, meta description, Open Graph-afbeelding, favicon.

## Anti-AI-look regels

Vermijd:
- Paarse/blauwe gradients als standaardkeuze, glassmorphism-kaartjes overal
- Drie identieke feature-kaartjes met emoji-iconen
- Generieke stockteksten ("Unlock your potential", "Elevate your brand")
- Alles gecentreerd en even groot

Doe wel:
- Eén dominante visual en veel witruimte (of "zwartruimte")
- Een duidelijke typografische hiërarchie: grote, karaktervolle koppen naast
  rustige bodytekst
- Een asymmetrische layout en ritme tussen secties
- Een beperkt palet (2–3 kleuren plus één accent)
- Copy die specifiek is voor de klant (wat, voor wie, resultaat)

## Output naar de gebruiker
Lever na elke build:
1. Wat er gebouwd of veranderd is (kort)
2. De checklist-score uit `references/10k-checklist.md`, met wat nog openstaat
3. De mobiel/tablet/desktop-screenshots
4. Wat de gebruiker zelf nog moet doen (formulierdienst kiezen, DNS instellen)
