---
layout: tutorial-post
title: React - Esercizio 05
category: React
tags: [Javascript, React, front end, framework]
excerpt_separator: <!--more-->
tutorial_tile: Andiamo alla SPA
---

In questo esercizio inizieremo a capire cosa è una SPA e come realizzarla nella *React Way*
<!--more-->
Iniziamo a parlare si SPA (Single Page Application: [https://en.wikipedia.org/wiki/Single-page_application](https://en.wikipedia.org/wiki/Single-page_application)). Una SPA è un'applicazione web che, differentemente dalle classiche applicazioni basate su varie pagine web, sono realizzate su una pagina sola. Questo da il vantaggio di non avere più il fastidioso effetto di ricarica ogni volta che si cambia "pagina", ma implica il dover affrontare problemi come:

* gestire il "cambio pagina" con link che non redirezionano ad altre pagine
* gestire il comportamento dei pulsanti back / forward del browser
* cazzi&mazzi vari... :)

Date queste permessi verrebbe da chiedersi perchè farlo lo stesso. La riposta è: un po' per masochismo e un po' perchè fa figo.

Come sempre per prima cosa leggeremo dei tutorial e poi ne seguiremo uno per capire le basi.

* un buon pattern per gestire componenti senza stato:
  * [http://blog.andrewray.me/the-reactjs-controller-view-pattern/](http://blog.andrewray.me/the-reactjs-controller-view-pattern/)
* visto che ci siamo, iniziamo a cercare di capire cosa sembrano essere le best practice.. Come vedete, siamo in linea con il meglio:
  * [https://github.com/petehunt/react-howto](https://github.com/petehunt/react-howto)
  * [https://blog.risingstack.com/react-js-best-practices-for-2016/](https://blog.risingstack.com/react-js-best-practices-for-2016/)

### IL TUTORIAL

E dopo la teoria, ecco qualche riga di codice con la soluzione di routing cucita su React: react-router!

* [https://github.com/reactjs/react-router-tutorial/tree/master/lessons/01-setting-up](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/01-setting-up)

#### SEGUENDO IL TUTORIAL 01...

blablabla

### HERE WE GO!

E ora a noi! E qui senza aiuti!! Ecco cosa fare:

* basandosi sul codice prodotto con l'[Esercizio 04]({% post_url 2016-07-09-react-esercizio-04 %}) svilupperemo una SPA completa di navigazione
* leggere file README.TXT e seguire le istruzioni per installare GULP e le librerie necessarie
* seguire le norme imparate nel tutorial precedente per creare una semplice applicazione react/flux:
  * nell’applicazione ci sono 3 pagine:
    * main menu (page1)![image alt text]({{ site.baseurl }}public/images/image_0.png)
      * un click su un’icona casa/auto/posate porta alla corrispondente sezione di aggiunta spese
      * un click sull’icona calendario porta al riepilogo spese
    * aggiunta spesa (page2)![image alt text]({{ site.baseurl }}public/images/image_1.png)
      * la sezione aggiunta spese è composta da:
        * un form per aggiungere una nuova spesa / modificarne una esistente
        * un riepilogo di tutte le spese inserite
        * uso del form
          * nel form va inserito un importo in euro, una data (prevalorizzata al giorno corrente) e una nota
          * un click sul + verde conferma i dati e aggiunge la spesa nella lista sotto e al totale del mese
          * Un click sulla freccia rossa resetta i dati e riporta alla pagina principale
        * uso della lista
          * un click sulla x rossa cancella la spesa dalla lista e dal totale del mese
          * un click sulla matita carica i dati della spesa nel form e alla conferma li cambia nella lista e nel totale del mese
    * riepilogo spese (page3)![image alt text]({{ site.baseurl }}public/images/image_2.png)
        * un click sull’icona con la freccia rossa riporta alla pagina principale

#### RISORSE

Ecco le risorse utilizzate in questo esercizio:

* framework css utilizzato: [http://getskeleton.com/](http://getskeleton.com/)
* icone utilizzate: [https://www.iconfinder.com/iconsets/bitsies](https://www.iconfinder.com/iconsets/bitsies)
