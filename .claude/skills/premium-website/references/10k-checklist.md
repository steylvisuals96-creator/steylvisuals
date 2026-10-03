# $10.000-checklist

Score elke regel als ✅ / ⚠️ / ❌. Alles ❌ of ⚠️ moet gefixt worden of
expliciet aan de gebruiker gemeld.

## 1. Strategie
- [ ] Eén primaire CTA, zichtbaar boven de vouw op desktop én mobiel
- [ ] CTA komt minstens 2× terug (hero + einde)
- [ ] Kop zegt in < 3 seconden wat je doet en voor wie
- [ ] Bewijs aanwezig: portfolio, cijfers, testimonials of logo's

## 2. Custom design
- [ ] Voldoet aan de anti-AI-look regels in SKILL.md
- [ ] Consistent palet en fonts via CSS-variabelen
- [ ] Duidelijke typografische hiërarchie (H1 ≫ H2 ≫ body)
- [ ] Royale witruimte en een ritme tussen secties
- [ ] Echte, scherpe beelden (geen placeholders, geen pixelige assets)

## 3. Custom motion
- [ ] Minstens één "wow"-moment (hero-animatie, interactieve hotspot, parallax)
- [ ] Reveal-on-scroll op secties (IntersectionObserver, geen zware libraries nodig)
- [ ] Hover-states op alle klikbare elementen
- [ ] Respecteert `prefers-reduced-motion`
- [ ] Geen hapering: alleen `transform`/`opacity` animeren

## 4. Responsive
- [ ] Gecontroleerd met screenshots op 390, 820 en 1440 px breed
- [ ] Geen horizontale scroll
- [ ] Tap-targets ≥ 44px, tekst ≥ 16px op mobiel
- [ ] Mobiel menu werkt
- [ ] Video/hero schaalt correct (object-fit: cover)

## 5. Het werkt
- [ ] Formulier verstuurt echt (getest) naar inbox/CRM, met succes- en foutmelding
- [ ] Alle links en knoppen werken, geen 404's
- [ ] `<title>`, meta description, OG-image, favicon
- [ ] Live op eigen domein met HTTPS
- [ ] Laadt snel (afbeeldingen gecomprimeerd, lazy loading, video met poster)
