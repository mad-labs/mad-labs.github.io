---
layout: post
title: React - Esercizio 02
category: React
tags: [Javascript, React, front end, framework]
excerpt_separator: <!--more-->
---

### Esercizio 02 - Un game con React

Adesso che sappiamo leggere e seguire un turorial su React è il momento di impegnarsi un po' per diventare indipendenti. Sarebbe carino riuscire a fare un semplice gioco utilizzando React?
<!--more-->

Ecco i passi per eseguire questo esercizio :

* clonare il progetto react-flux-homeworks con **git clone ssh://git@worky01:/home/git/react-flux-homeworks.git** sul workspace
  * il progetto contiene un template in html da utilizzare per l'esercizio
* creare un branch chiamato *tictactoe_***_proprionome_**
* leggere file README.TXT e seguire le istruzioni per installare le dipendenze e l'ambiente
* leggere i tutorial su:
    * [http://blog.andrewray.me/reactjs-for-stupid-people/](http://blog.andrewray.me/reactjs-for-stupid-people/)
        * questo tutorial serve per avere un’idea su cosa sia React e su come si usa
    * [https://facebook.github.io/react/docs/thinking-in-react.html](https://facebook.github.io/react/docs/thinking-in-react.html)
        * di questo tutorial sono importanti due concetti:
            * scomporre le interfacce in componenti
            * passare ai componenti "figlli" le proprietà e le funzioni per modificare lo stato dei componenti “padri”
* seguire le norme imparate nel tutorial precedente per creare un gioco del tris con react
    * partendo dal mockup html scomporre e diseganre i componenti React
    * creare un albero dei componenti
    * implementare l’interfaccia di gioco in React in modo che il click sulle celle VUOTE segni il simbolo di uno dei due giocatori alternativamente:
        * il primo click segna **X** su una casella
        * il secondo click segna **O** su una casella
        * se la cella è già occupata non deve essere inserito nessun simbolo
* troverete la mia versione sotto il branch tictactoe_gabriele
* pushate il codice finito :)
* RISORSE UTILI:
    * [https://facebook.github.io/react/docs/component-specs.html#lifecycle-methods](https://facebook.github.io/react/docs/component-specs.html#lifecycle-methods)

Scrivetemi pure per info
