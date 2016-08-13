---
layout: post
title: React - Esercizi 03
category: React
tags: [Javascript, React, front end, framework]
excerpt_separator: <!--more-->
---

### Esercizio 03 - Miglioriamo il Game

Esercizio 3
<!--more-->

* clonare il progetto react-flux-homeworks con :
*	git clone ssh://git@worky01:/home/git/react-flux-homeworks.git*
sul workspace

* creare un branch chiamato *tictactoe_***_proprionome_**

* leggere file README.TXT e seguire le istruzioni

* dopo aver letto il tutorial su:

    * [https://facebook.github.io/react/docs/thinking-in-react.html](https://facebook.github.io/react/docs/thinking-in-react.html)

        * importante il passaggio dello stato come proprietà e delle funzioni per manipolarlo

    * [http://blog.andrewray.me/flux-for-stupid-people/](http://blog.andrewray.me/flux-for-stupid-people/)

        * leggetelo solo per capire il tutorial successivo

    * [http://blog.andrewray.me/the-reactjs-controller-view-pattern/](http://blog.andrewray.me/the-reactjs-controller-view-pattern/)

        * ignorate pure FLUX, concentratevi su come i componenti

* seguire le norme imparate nel tutorial precedente per migliorare il gioco del tris in questo modo

    * disegnare un componente di controllo che contiene lo stato globale del gioco (la situazione di tutte le celle, giocatore di turno, vittoria)

    * modificare i componenti delle celle per utilizzare lo stato globale e non il proprio stato interno

    * utilizzare delle funzioni del componente globale per manipolare il suo stato, passate come proprietà (non usiamo FLUX)

    * OPZIONALE: aggiungere la logica di calcolo della vittoria, segnalazione vincitore e reset del gioco

    * OPZIONALE: agiungere grafica e miogliorare layout

* troverete la mia versione sotto il branch tictactoe_gabriele

* pushate il codice finito :)

* RISORSE UTILI:

    * https://facebook.github.io/react/docs/component-specs.html#lifecycle-methods

Scrivetemi pure per info
