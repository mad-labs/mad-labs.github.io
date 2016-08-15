---
layout: tutorial-post
title: React - Esercizio 03
category: React
tags: [Javascript, React, front end, framework]
excerpt_separator: <!--more-->
tutorial_tile: Miglioriamo il Giocoo!
---

Ora che abbiamo le basi per il nostro gioco, non ci resta che migliorarlo!
<!--more-->

Come migliorare quello che sembra perfetto? Bhè, quello non so, ma il nostro GAME fa abbastanza schifo da poterci mettere mano!
Giusto per finfrescarci la memoria e leggere altri siti interessati, ecco dei tutorial golosi da guardare:

* questo turorial, citato negli scorsi, spiega come scomporre un html in componenti React e come passare i dati e le funzioni per controllare lo stato ai componenti:
  * [https://facebook.github.io/react/docs/thinking-in-react.html](https://facebook.github.io/react/docs/thinking-in-react.html)

### HERE WE GO!

E ora a noi! E qui senza aiuti!! Ecco cosa fare:

* basandosi sul codice prodotto con l'[Esercizio 02]({% post_url 2016-06-25-react-esercizio-02 %}) incrementeremo le funzionalità del gioco.
* seguire le norme imparate nel tutorial precedente per migliorare il gioco del tris in questo modo
  * disegnare un componente di controllo che contiene lo stato globale del gioco
    * la situazione di tutte le celle
    * giocatore di turno
    * vittoria
  * modificare i componenti delle celle per utilizzare lo stato globale e non il proprio stato interno
  * utilizzare delle funzioni del componente globale per manipolare il suo stato, passate come proprietà (non usiamo FLUX)
  * OPZIONALE: aggiungere la logica di calcolo della vittoria, segnalazione vincitore e reset del gioco
  * OPZIONALE: agiungere grafica e miogliorare layout


#### RISORSE

Un paio di link utili alla realizzazione dell'esercizio sono:

* [html-tags-vs.-react-components](http://snip.ly/7DTB#https://facebook.github.io/react/docs/jsx-in-depth.html#html-tags-vs.-react-components)
* [lifecycle-methods](https://facebook.github.io/react/docs/component-specs.html#lifecycle-methods)
