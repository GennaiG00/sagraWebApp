# Ordine dal telefono (QR) — pagina web

`index.html` è la pagina che si apre sul telefono del cliente quando scansiona il QR della cassa.
È un **unico file statico**: non c'è nessun server, nessun database, nessun dato che passa da internet.
Il menu arriva dentro l'indirizzo del QR, e nome, numero e piatti tornano alla cassa dentro il QR
che il telefono mostra a sua volta.

## Come funziona

1. In cassa: **Menu ☰ → QR per i clienti…** mostra il QR del menu (si può salvare come immagine e stampare).
2. Il cliente lo inquadra col telefono (anche con i dati mobili) → si apre questa pagina col menu.
3. Scrive nome e numero (tavolo o telefono), sceglie i piatti → la pagina mostra un secondo QR.
4. In cassa il **lettore USB** legge quel QR (tasto **F2** o pulsante "Leggi QR del cliente"):
   il carrello si riempie da solo, la cassa controlla e conferma come sempre.

## Mettere la pagina online (una volta sola, gratis)

La pagina deve avere un indirizzo https pubblico. Il modo più semplice è GitHub Pages:

1. Su github.com crea un repository **pubblico** (non quello del programma!), per esempio `sagra-ordina`.
   Non contiene nulla di riservato: solo questo file.
2. **Add file → Upload files** e carica `index.html`.
3. **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, cartella `/ (root)` → Save.
4. Dopo un minuto la pagina è su `https://TUOUTENTE.github.io/sagra-ordina/`.
5. In cassa, **Menu ☰ → QR per i clienti…**: scrivi quell'indirizzo nel campo in alto. Viene ricordato.

## Cose da sapere

- Se **cambi il menu** (piatti, nomi, prezzi, ordine) devi rigenerare e ristampare il QR. Un QR vecchio viene
  rifiutato dalla cassa con un messaggio chiaro. Segnare un piatto come esaurito invece non cambia il QR.
- Il QR dell'ordine usa solo lettere e numeri, così il lettore USB non sbaglia i simboli con la tastiera italiana.
- Il lettore USB deve essere in modalità "tastiera" (è quella di default). Se non preme Invio alla fine,
  la cassa elabora il codice da sola dopo mezzo secondo.
- La pagina usa la libreria QR di Project Nayuki (licenza MIT), inclusa nel file.
