# Tedesco con Martina — sito web

Sito statico a **pagina singola** (HTML puro — CSS e JavaScript sono incorporati direttamente in ogni file, quindi non servono cartelle esterne né build). Pronto per essere pubblicato su **GitHub Pages**.

## Struttura del progetto

```
├── index.html            Pagina principale: Home, Lezioni 1:1, Supporto trasferimento,
│                          Testimonianze, FAQ, Contatti/Prenotazione (Calendly + form)
├── privacy-policy.html
├── cookie-policy.html
├── 404.html               Pagina errore personalizzata
├── robots.txt
└── sitemap.xml
```

Ogni pagina `.html` contiene già al suo interno tutto lo stile grafico e le interazioni (menu mobile, animazioni, form): basta aprirla per vederla esattamente come nell'anteprima, senza bisogno di altre cartelle.

## Come pubblicarlo su GitHub Pages (5 minuti)

1. Vai su [github.com](https://github.com) e crea un nuovo repository (es. `tedesco-con-martina`), impostalo come **pubblico**.
2. Apri il repository appena creato e clicca su **Add file → Upload files**.
3. Trascina dentro tutti i file di questo progetto (`index.html`, `privacy-policy.html`, `cookie-policy.html`, `404.html`, `robots.txt`, `sitemap.xml`) — devono stare nella root del repository, non dentro una sottocartella.
4. Clicca **Commit changes** per salvare.
5. Vai su **Settings → Pages** (menu a sinistra).
6. In "Build and deployment" → **Source**, scegli **Deploy from a branch**.
7. Seleziona il branch `main` e la cartella **/ (root)**, poi **Save**.
8. Dopo circa un minuto il sito sarà online su:
   `https://<tuo-username>.github.io/<nome-repo>/`

Se vuoi collegare un dominio personalizzato (es. `www.tedescoconmartina.it`), in **Settings → Pages → Custom domain** inserisci il dominio e configura un record CNAME presso il tuo provider DNS puntato a `<tuo-username>.github.io`.

## ⚠️ Cose da personalizzare prima di andare online

1. **Calendly** — i pulsanti "Prenota una consulenza/lezione gratuita" e il pulsante dedicato nella sezione "Contatti" puntano già al tuo link: `https://calendly.com/tedescoconmartina/30min`. Se in futuro lo cambi, cerca `calendly.com/tedescoconmartina` in `index.html` e sostituiscilo ovunque compare (6 occorrenze).
2. **Modulo di contatto** — sotto al pulsante Calendly resta un form alternativo per chi preferisce scrivere prima: all'invio si apre il client di posta dell'utente con un'email precompilata verso `info@tedescoconmartina.it`. Cambia questo indirizzo con la tua email reale (cercalo in `index.html`, sia nell'attributo `data-to` del form sia nei link `mailto:`). Se preferisci che il form consegni i messaggi direttamente senza aprire il programma di posta, collegalo a un servizio gratuito come [Formspree](https://formspree.io).
3. **Social** — nel footer, i link "LinkedIn" e "WhatsApp" puntano a `#`. Inseriscici i tuoi URL reali.
4. **Testimonianze** — nella sezione "Cosa dicono i miei studenti" ci sono 3 recensioni di **esempio**, chiaramente marcate. Sostituiscile con recensioni reali dei tuoi studenti (con il loro consenso).
5. **Dominio** — nei tag `<link rel="canonical">`, `<meta property="og:url">` e `<meta property="og:image">`, oltre che in `sitemap.xml` e `robots.txt`, è usato il dominio segnaposto `https://tedescoconmartina.example/`. Sostituiscilo con il tuo dominio reale una volta che lo conosci (URL GitHub Pages o dominio personalizzato). In particolare, `og:image` deve restare un URL reale e pubblico (non funziona con immagini incorporate) — assicurati che punti al tuo dominio definitivo.
6. **Privacy Policy e Cookie Policy** — sono **modelli generici di partenza**, non una consulenza legale. Falle rivedere da un consulente privacy o generale con un servizio dedicato (es. iubenda), soprattutto se in futuro colleghi il form a Formspree o aggiungi Google Analytics.

## Cosa contiene la pagina

- **Hero** con presentazione generale
- **Servizi** — panoramica dei due percorsi (lezioni / trasferimento), con link di ancoraggio alle rispettive sezioni
- **Chi sono** — la tua storia
- **Lezioni 1:1** — caratteristiche, metodo, argomenti trattati, statistiche animate
- **Supporto al trasferimento** — cosa include, percorso in 4 fasi
- **Testimonianze** — carosello (da compilare con recensioni reali)
- **FAQ** — incluse le domande su durata delle lezioni di conversazione (30 minuti) e personalizzazione per professione (medico, estetista, ingegnere, studenti, ecc.)
- **Contatti** — pulsante di prenotazione diretta su Calendly + form alternativo

Nessuna emoji o icona grafica: la gerarchia visiva è affidata solo a tipografia, colore e spaziatura.

## Note tecniche (SEO / AEO)

- HTML semantico, indicizzabile dai motori di ricerca e leggibile dagli answer engine (ChatGPT, Perplexity, Google AI Overview)
- Dati strutturati JSON-LD (schema.org: `ProfessionalService`, `Course`, `Service`, `FAQPage`)
- `robots.txt` + `sitemap.xml` inclusi
- Header sticky, menu mobile, animazioni "reveal" allo scroll, contatori statistici animati, pulsante "torna su"
- Completamente responsive, focus da tastiera visibile, rispetta `prefers-reduced-motion`
