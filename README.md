# Vymotion — Design System

Sistema di base grafico di Vymotion: token (colori, tipografia, forme, spaziature), font e linee guida per documenti (volantini, email, schede, presentazioni) e UI.

Questa repo è la **sorgente di verità** del brand. I file in `tokens/` contengono i valori canonici; questo README descrive il *perché* di ogni scelta.

---

## Struttura

```
design-system/
├── README.md                  → questa guida
├── tokens/
│   ├── vymotion-tokens.css     → variabili CSS + classi-firma pronte
│   └── vymotion-tokens.json    → stessi token, machine-readable
├── fonts/
│   └── LeagueGothic-Italic.woff2
└── assets/                     → loghi vettoriali (da aggiungere)
```

---

## 1. Identità del brand

Vymotion è un centro fitness dall'estetica **premium, dinamica e geometrica**. Il linguaggio visivo è costruito su **forme angolari e diagonali** (parallelogrammi, chevron, tagli obliqui) che evocano movimento e direzione. La palette è essenziale — verde performance, nero, grigio neutro su fondo bianco — e l'effetto è atletico ma sobrio, professionale ma energico.

Il motivo ricorrente è la **diagonale a ~45°**: presente nel monogramma, nei parallelogrammi, nelle frecce-chevron e nel taglio delle immagini fotografiche. È la firma visiva del brand e va mantenuta coerente su tutti i documenti.

---

## 2. Logo e marchio

Tre asset:

- **Marchio orizzontale** — monogramma "M" + wordmark "VYMOTION" affiancati. Uso primario su header e intestazioni.
- **Monogramma "M"** — la lettera costruita con tre elementi angolari. Uso come icona, favicon, watermark, elemento decorativo a grande scala.
- **Wordmark "VYMOTION"** — lettering condensato maiuscolo, spaziatura ampia.

Versioni colore: **nero (#1D1D1B)** su fondo chiaro; **bianco** su fondo scuro/foto; **verde (#588652)** come accento. Mantenere un'area di rispetto attorno al logo pari almeno all'altezza del monogramma. Non distorcere, non ruotare, non applicare ombre.

---

## 3. Colori

Palette canonica, tre colori + bianco:

| Token | Hex | Uso |
|-------|-----|-----|
| Verde Performance | `#588652` | Colore primario. Accenti, CTA, parole-chiave nei titoli, forme |
| Nero | `#1D1D1B` | Testo principale, logo, titoli (nero caldo, non puro) |
| Grigio Neutro | `#9D9D9C` | Testo secondario, didascalie, forme di sfondo, divisori |
| Bianco | `#FFFFFF` | Sfondo dominante |

**Regola d'oro:** il verde è accento, mai riempimento totale. Il brand respira sul bianco.

Colori di stato (UI): arancione `#E8923A` = attenzione, rosso `#D64545` = allerta, grigio = non disponibile.

Livelli abbonamento (secondari): Base = verde, Plus = teal, Pro = viola-magenta (gli ultimi due da confermare dagli asset).

> Nota: l'app cliente usa ancora `#578552`; il valore di brand ufficiale è `#588652` — da uniformare.

---

## 4. Tipografia

- **League Gothic Italic** — font display/titoli. Usato **CORSIVO + MAIUSCOLO**, letter-spacing ~−0.02em, line-height condensato. È il carattere-firma. Per H1, titoli di sezione, headline. Tecnica brand: **evidenziare in verde una o più parole-chiave** del titolo.
- **Inter** — font corpo/UI. Body text, etichette, dati. Pesi: Regular, Medium, SemiBold.

Mai usare League Gothic per il corpo del testo.

---

## 5. Forme ed elementi grafici

Il sistema di forme è il cuore del brand:

- **Parallelogramma diagonale** — forma-base inclinata ~45°, angoli morbidi. Versione **verde piena** (accento attivo) e **grigio trasparenza** (sfondo/profondità, spesso come "ombra" sfalsata dietro un altro elemento).
- **Chevron / frecce a "V"** — tre frecce in successione con **opacità decrescente**. Evocano avanzamento e direzione.
- **Immagine in cornice diagonale** — le foto sono ritagliate in **parallelogramma a 45°**, con un parallelogramma grigio sfalsato dietro per dare profondità. Trattamento ufficiale: mai foto in rettangolo dritto.
- **Angoli arrotondati morbidi** su forme decise.

---

## 6. Trattamento fotografico

Stile: **palestra reale, atletica, autentica**. Persone che si allenano, alta energia, emozione genuina. Palette foto coerente col brand: toni verdi militari/oliva, neri, grigi. Luce naturale, ambienti grezzi/industriali. Sempre ritagliate in **cornice diagonale**. Evitare stock patinato e colori fuori palette.

---

## 7. Layout e spaziatura

- Generoso uso del **bianco**.
- Composizioni su **assi diagonali** (~45°).
- Scala spaziatura a 4px; padding di riferimento **24px**.
- Gerarchia chiara: un elemento dominante per composizione, accenti verdi mirati, resto in nero/grigio su bianco.

---

## 8. Tono di voce

Vymotion **dà del tu**. Registro **tecnico ma accessibile**, **data-oriented**.

- Il tecnicismo è al servizio della chiarezza, non dell'esibizione. Termini precisi sempre resi comprensibili a chiunque.
- Si parla con numeri e misure concrete, ma il dato è sempre contestualizzato, mai secco.
- Regola pratica: se introduci un termine tecnico, aggiungi mezza frase che lo traduce. Es: *"Il tuo recupero (quanto il corpo è pronto ad allenarsi di nuovo) è ottimale."*
- Da evitare: gergo senza spiegazione, motivazionale urlato, familiarità eccessiva.

Sintesi: **competente · diretto · concreto · mai criptico**.

---

## Come usare i token

**CSS** — importa il file e usa le variabili:

```css
@import url("tokens/vymotion-tokens.css");

.titolo {
  font-family: var(--vy-font-display);
  font-style: italic;
  text-transform: uppercase;
  color: var(--vy-black);
}
.parola-chiave { color: var(--vy-green); }
```

Classi-firma già pronte nel CSS: `.vy-display`, `.vy-accent`, `.vy-parallelogram`, `.vy-shape-layered`, `.vy-photo-diagonal`, `.vy-btn`.

**JSON** — per strumenti che leggono i token come dati (`tokens/vymotion-tokens.json`).

---

*Vymotion Design System · v1.0.0*
