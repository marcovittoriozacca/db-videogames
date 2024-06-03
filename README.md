Creare lo schema e-r con tutte le entità necessarie a gestire le informazioni di un archivio di E-sports. (https://www.drawio.com/)
Ciascun videogame ha un nome, una trama, una data di rilascio ed è prodotto da una software house, la quale, a sua volta, è identificata da un nome, una partita iva, città e nazione.
I videogames possono essere disponibili su diverse piattaforme (PlayStation 4, PlayStation 5, XBox One, XBox Serie X, Windows, Nintendo Switch, Google Stadia, ...) e hanno diverse categorie (avventura, strategia, RPG, sparatutto, calcio, ...) e classificazioni PEGI (PEGI 7, PEGI 12, PEGI 18, Violenza, Paura, Gioco d'azzardo, ...)
Periodicamente, vengono organizzati dei tornei a cui possono partecipare tutti i videogiocatori del mondo.
Ogni torneo è caratterizzato da un nome, l'anno e la città in cui si svolge. I giocatori, al momento dell'iscrizione, devono fornire nome, cognome, nickname di gioco, e città di provenienza.
I videogames possono essere recensiti dai giocatori, i quali oltre al titolo e al testo, possono valutare i videogame con un rating da 1 a 5.
Ogni anno vengono votati i migliori videogiochi, che possono così vincere diversi premi (gioco dell'anno, miglior narrativa, miglior colonna sonora, miglior gioco indipendente, gioco più atteso, ...)

# SPIEGAZIONE RELAZIONI

### Tabella Videogames - Software_Houses. One To Many
- Una software house può produrre molteplici videogiochi, ma un videogame è sviluppato da una sola software house.

### Tabella Videogames - Classifications (PEGI). One To Many
- Una classificazione PEGI (ad esempio PEGI 18) può essere applicata a molteplici videogames, e un videogame può avere molteplici classificazioni (es: PEGI 18, VIOLENZA, PAURA).

### Tabella Videogames - Platforms. Many To Many (pivot: platform_videogame)
- Un videogame può essere presente su molteplici piattaforme (xbox, playstation, switch etc...) e una piattaforma può avere molti videogames disponibili su di essa.

### Tabella Videogames - Category. Many To Many (pivot: category_videogame)
- Un videogame può essere associato a molteplici categorie (azione, avventura, horror...) e una categoria specifica può essere presente su più videogames

### Tabella Videogames - Awards. Many To Many (pivot: award_videogame)
- Un videogame può vincere molteplici premi nel corso degli anni, un premio può essere assicuati a più videogames nel corso degli anni (es: GOTY nel 2022 gioco X nel 2023 gioco Y)

### Tabella Videogames - Tournaments. One to Many
- Un videogame può essere presente a più tornei, ma un torneo viene svolto su un singolo gioco alla volta.

### Tabella Tournaments - Players. Many to Many (pivot: player_tournament)
- In un torneo sono presenti molteplici giocatori, così come un giocatore può partecipare a più tornei
  
### Tabella Players - Reviews. One to Many
- Un giocatore può scrivere più recensioni, ma una recensione è associata ad un singolo giocatore

### Tabella Reviews - Ratings. One to Many
- Un voto può essere associato a più recensioni, ma una recensione ha solo un voto per volta

### Tabella Reviews - Videogames. One to Many
- Una recensione può appartenere ad un singolo videogame alla volta, ma un videogame può ricevere molteplici recensioni