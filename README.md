# Sito Farmakoff

Sito statico di una pagina, pensato per GitHub Pages (come ottica-vitali).
Non usa database né account: chiunque apre il link vede il sito completo.

## File

- `index.html`: la pagina (italiano e inglese, pulsante IT/EN).
- `contenuti.json`: tutti i testi e i dati. È l'unico file da modificare per gli aggiornamenti.
- `covers/`: copertine delle uscite (800x800, JPG).
- `farmakoff-oblo.jpg`: immagine di apertura.
- `fk01-front-vector.svg`: schema tecnico di sfondo.
- `.nojekyll`: dice a GitHub Pages di pubblicare i file così come sono.

## Pubblicazione su GitHub Pages

1. Crea un repository nuovo (consigliato: un account o un'organizzazione GitHub dedicata a Farmakoff, così l'indirizzo non contiene il tuo nome).
2. Carica tutti i file di questa cartella nella radice del repository, `.nojekyll` compreso.
3. Settings → Pages → Source: "Deploy from a branch", branch `main`, cartella `/ (root)`.
4. Dopo un minuto il sito è online su `https://<account>.github.io/<repository>/`.

## Dominio personalizzato (quando sarà scelto)

1. Crea nel repository un file `CNAME` con dentro solo il dominio, per esempio `farmakoff.com`.
2. Dal pannello del registrar del dominio aggiungi i record DNS indicati da GitHub Pages.
3. In Settings → Pages attiva "Enforce HTTPS".

## Aggiornare i contenuti

Modifica solo `contenuti.json` (date nel formato AAAA-MM-GG, link completi con https://):

- `releases`: una voce per uscita. Le uscite con data futura compaiono come "In arrivo".
  Campi: `title`, `date`, `type`, `cover` (es. `covers/nome.jpg`), `spotify`, `presave`, `text`, `text_en`.
- `transmissions`: il registro di bordo. Ogni trasmissione compare solo dalla sua data.
- `events`: i live. La sezione Live compare solo se c'è almeno un evento futuro.
- `links`: canali social e Spotify dell'artista.

La fonte dei dati resta la Cartella Farmakoff: Claude prepara il `contenuti.json` aggiornato, poi va caricato nel repository.
La pagina contiene anche una copia dei contenuti: se `contenuti.json` non si carica, mostra quella.
