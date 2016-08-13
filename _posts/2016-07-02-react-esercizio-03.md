---
layout: post
title: React - Esercizio 03
category: React
tags: [Javascript, React, front end, framework]
excerpt_separator: <!--more-->
---

### Esercizio 03 - Miglioriamo il Game

Ora che abbiamo le basi per il nostro gioco, non ci resta che migliorarlo!
<!--more-->

* basandosi sul codice prodotto con l'[Esercizio 02]({% post_url 2016-06-25-react-esercizio-02 %}) incrementeremo le funzionalità del gioco.
* dopo aver letto il tutorial su:
    * [https://facebook.github.io/react/docs/thinking-in-react.html](https://facebook.github.io/react/docs/thinking-in-react.html)
        * importante il passaggio dello stato come proprietà e delle funzioni per manipolarlo
* seguire le norme imparate nel tutorial precedente per migliorare il gioco del tris in questo modo
    * disegnare un componente di controllo che contiene lo stato globale del gioco
      * la situazione di tutte le celle
      * giocatore di turno
      * vittoria
    * modificare i componenti delle celle per utilizzare lo stato globale e non il proprio stato interno
    * utilizzare delle funzioni del componente globale per manipolare il suo stato, passate come proprietà (non usiamo FLUX)
    * OPZIONALE: aggiungere la logica di calcolo della vittoria, segnalazione vincitore e reset del gioco
    * OPZIONALE: agiungere grafica e miogliorare layout
* troverete la mia versione sotto il branch tictactoe_gabriele
* pushate il codice finito :)
* RISORSE UTILI:
    * https://facebook.github.io/react/docs/component-specs.html#lifecycle-methods

Scrivetemi pure per info
