# BainzaPlan

Visualizzatore rapido del piano di allenamento ciclistico stagionale. Single-file HTML, nessun server, funziona su iPhone (PWA) e browser Windows.

---

## Cos'è

BainzaPlan non è un tracker — per quello c'è Bainzuretta. È un **visualizzatore**: apri l'app, vedi subito la settimana in corso con le uscite previste, e puoi scorrere avanti e indietro nel piano senza dover cercare il file Word ogni volta.

---

## File inclusi

| File | Descrizione |
|---|---|
| `BainzaPlan.html` | L'app completa, un unico file HTML |
| `BainzaPlan_Template.docx` | Template Word per scrivere il piano nella forma corretta |
| `piano_bainza.txt` | Piano attuale già convertito nel formato dell'app |

---

## Come si usa

### Prima volta

1. Apri `BainzaPlan.html` in Safari (iPhone) o in qualsiasi browser (Windows/Mac)
2. Tocca l'ingranaggio ⚙ in alto a destra
3. Carica il file `.txt` oppure incolla il testo del piano
4. Tocca **Salva piano** — i dati restano sul dispositivo, nessun server coinvolto

### Su iPhone come app

In Safari: **Condividi → Aggiungi a schermata Home**. L'app si apre a schermo intero come una app nativa, senza barra del browser.

### Aggiornare il piano

Modifica il template Word seguendo il formato (vedi sotto), poi ricaricami il file `.docx` in chat con scritto "aggiornami il piano" — ti genero il nuovo `.txt` pronto da incollare.

---

## Formato del piano

Il piano è un file `.txt` con una sintassi semplice. Ogni riga ha un significato preciso:

```
BLOCCO: Nome blocco | anno
SETTIMANA: gg/mm - gg/mm | ETICHETTA
GIO gg/mm | km | D+ (opzionale) | tag
NOTE: testo libero (facoltativo)
```

### Esempio completo

```
BLOCCO: Verso 11 Luglio | 2026

SETTIMANA: 22/06 - 28/06 | CARICO STRUTTURALE
LUN 22/06 | 25-30 km | facile
MER 24/06 | 30-35 km | 400-600 D+ | medio
SAB 27/06 | 100-110 km | 1800-1900 D+ | PICCO
NOTE: Settimana chiave di costruzione vera

SETTIMANA: 29/06 - 05/07 | SCARICO INTELLIGENTE
LUN 29/06 | 25-30 km | facile
MER 01/07 | 25-30 km | medio leggero
SAB 04/07 | 80-95 km | 300-500 D+ | pianura
```

### Giorni della settimana riconosciuti

`LUN` `MAR` `MER` `GIO` `VEN` `SAB` `DOM`

### Tag riconosciuti (colorano la card)

| Tag | Colore | Quando usarlo |
|---|---|---|
| `PICCO` | Rosso | Uscita lunga o di punta della settimana |
| `CARICO` | Arancione scuro | Settimana di carico strutturale |
| `SCARICO` | Giallo ocra | Settimana di recupero attivo |
| `TAPER` | Verde | Settimana di affilatura pre-gara |
| `facile` | Verde chiaro | Uscita di recupero |
| `medio` | Giallo | Uscita a intensità moderata |

I tag possono stare nell'etichetta della settimana (`SETTIMANA: ... | CARICO`) e/o nella riga del giorno. Se nella settimana c'è almeno un giorno `PICCO`, il bordo della card diventa rosso.

### Regole pratiche

- Usa sempre il trattino normale `-` negli intervalli (non `–` o `—`)
- L'anno nel `BLOCCO` è opzionale: se omesso usa l'anno corrente. Mettilo esplicito se il piano attraversa fine anno
- Le sezioni di nutrizione/strategia gara non vanno nel file `.txt`, restano solo nel Word
- Una sola riga `NOTE:` per settimana

---

## Navigazione nell'app

**Vista "Questa settimana"** — si apre automaticamente sulla settimana in corso. Le frecce `‹ ›` scorrono alle settimane precedenti o successive. Su iPhone si può anche fare swipe sinistra/destra sulla card. Tornando dalla Timeline, si riallinea sempre alla settimana corrente.

**Vista "Timeline"** — mostra tutti i blocchi e le settimane in sequenza, con la barra colorata a sinistra che indica il tipo di carico.

**Countdown** — sotto la card della settimana compaiono i chip con i giorni mancanti ai prossimi eventi `PICCO` nel piano.

---

## Dati e privacy

Il piano è salvato in `localStorage` del browser, solo sul dispositivo dove lo carichi. Non viene inviato a nessun server. Se usi l'app su iPhone e su PC, dovrai caricare il file `.txt` su entrambi separatamente (o usare la funzione di sync cloud dalla sheet ⚙ se configurata).

---

## Versione

`BainzaPlan 1.2` — parte dell'ecosistema MEM Software
