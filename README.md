# Tedesco con Martina — sito web

Sito statico a **pagina singola** (HTML/CSS/JS puro, nessuna build necessaria), pronto per essere pubblicato su **GitHub Pages**.

## Struttura del progetto

```
├── index.html            Pagina unica: Home, Lezioni 1:1, Supporto trasferimento,
│                          Testimonianze, FAQ, Contatti/Prenotazione
├── privacy-policy.html
├── cookie-policy.html
├── 404.html               Pagina errore personalizzata
├── robots.txt
├── sitemap.xml
└── assets/
    ├── css/style.css
    ├── js/main.js
    └── img/                Foto di Martina, favicon
```

## Come pubblicarlo su GitHub Pages (5 minuti)

1. Vai su [github.com](https://github.com) e crea un nuovo repository (es. `tedesco-con-martina`), impostalo come **pubblico**.
2. Apri il repository appena creato e clicca su **"uploading an existing file"** (o "Add file → Upload files").
3. Trascina dentro **tutti** i file e le cartelle di questo progetto (mantenendo la struttura sopra: `index.html`, `assets/`, ecc. devono stare nella root del repository, non dentro una sottocartella).
4. Clicca **Commit changes** per salvare.
5. Vai su **Settings → Pages** (menu a sinistra).
6. In "Build and deployment" → **Source**, scegli **Deploy from a branch**.
7. Seleziona il branch `main` e la cartella **/ (root)**, poi **Save**.
8. Dopo circa 1 minuto il sito sarà online su:
   `https://<tuo-username>.github.io/<nome-repo>/`

Se vuoi collegare un dominio personalizzato (es. `www.tedescoconmartina.it`), in **Settings → Pages → Custom domain** inserisci il dominio e configura un record CNAME presso il tuo provider DNS puntato a `<tuo-username>.github.io`.

## ⚠️ Cose da personalizzare prima di andare online

1. **Form di prenotazione (sezione "Contatti")** — attualmente, quando l'utente invia il modulo, si apre il suo programma di posta con un'email precompilata indirizzata a `info@tedescoconmartina.it`. È una soluzione che funziona subito, senza bisogno di un server, ma dipende dal fatto che l'utente abbia un client di posta configurato sul dispositivo. Se preferisci un form che consegna i messaggi direttamente (senza aprire il programma di posta), puoi collegarlo in pochi minuti a un servizio gratuito come [Formspree](https://formspree.io): basta cambiare l'attributo `action` del tag `<form id="booking-form">` in `index.html` con l'endpoint che Formspree ti fornisce.
2. **Indirizzo email** — sostituisci `info@tedescoconmartina.it` con il tuo indirizzo reale (cercalo in `index.html`, sia nell'attributo `data-to` del form sia nei link `mailto:`).
3. **Social** — nel footer, i link "LinkedIn" e "WhatsApp" puntano a `#`. Inseriscici i tuoi URL reali.
4. **Testimonianze** — nella sezione "Cosa dicono i miei studenti" ci sono 3 recensioni di **esempio**, chiaramente marcate. Sostituiscile con recensioni reali dei tuoi studenti (con il loro consenso).
5. **Dominio** — nei tag `<link rel="canonical">` e `<meta property="og:url">`, oltre che in `sitemap.xml` e `robots.txt`, è usato il dominio segnaposto `https://tedescoconmartina.example/`. Sostituiscilo con il tuo dominio reale una volta che lo conosci (URL GitHub Pages o dominio personalizzato).
6. **Privacy Policy e Cookie Policy** — sono **modelli generici di partenza**, non una consulenza legale. Falle rivedere da un consulente privacy o generale con un servizio dedicato (es. iubenda), soprattutto se in futuro colleghi il form a Formspree o aggiungi Google Analytics: entrambi comportano trattamenti di dati che vanno dichiarati correttamente.

## Cosa contiene la pagina

- **Hero** con presentazione generale
- **Servizi** — panoramica dei due percorsi (lezioni / trasferimento), con link di ancoraggio alle rispettive sezioni
- **Chi sono** — la tua storia
- **Lezioni 1:1** — caratteristiche, metodo, argomenti trattati, statistiche
- **Supporto al trasferimento** — cosa include, percorso in 4 fasi
- **Testimonianze** — carosello (da compilare con recensioni reali)
- **FAQ** — incluse le domande su durata delle lezioni di conversazione (30 minuti) e personalizzazione per professione (medico, estetista, ingegnere, studenti, ecc.)
- **Contatti** — form di prenotazione consulenza gratuita

Nessuna emoji o icona grafica è presente nel design: la gerarchia visiva è affidata a tipografia, colore e spaziatura.

## Note tecniche (SEO / AEO)

- HTML statico e semantico, indicizzabile dai motori di ricerca e leggibile dagli answer engine (ChatGPT, Perplexity, Google AI Overview)
- Dati strutturati JSON-LD (schema.org: `ProfessionalService`, `Course`, `Service`, `FAQPage`)
- `robots.txt` + `sitemap.xml` inclusi
- Header sticky, menu mobile, animazioni "reveal" allo scroll, contatori statistici animati, pulsante "torna su"
- Completamente responsive, focus da tastiera visibile, rispetta `prefers-reduced-motion`
