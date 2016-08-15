---
layout: post
title: React - Esercizio 05
category: React
tags: [Javascript, React, front end, framework]
excerpt_separator: <!--more-->
---

### Esercizio 05

Esercizio 5
<!--more-->

* basandosi sul codice prodotto con l'[Esercizio 04]({% post_url 2016-07-09-react-esercizio-04 %}) svilupperemo una SPA completa di navigazione
* leggere file README.TXT e seguire le istruzioni
* dopo aver letto i tutorial su:
    * [http://blog.andrewray.me/flux-for-stupid-people/](http://blog.andrewray.me/flux-for-stupid-people/)
    * [http://blog.andrewray.me/the-reactjs-controller-view-pattern/](http://blog.andrewray.me/the-reactjs-controller-view-pattern/)
    * [http://www.cosenonjaviste.it/sviluppare-applicazioni-con-react-e-flux/](http://www.cosenonjaviste.it/sviluppare-applicazioni-con-react-e-flux/)
* seguire le norme imparate nel tutorial precedente per creare una semplice applicazione react/flux:
    * l’applicazione è una SPA (Single Page Application: [https://en.wikipedia.org/wiki/Single-page_application](https://en.wikipedia.org/wiki/Single-page_application))
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
* troverete la mia versione (quasi finita) sotto il branch wimm_gabriele
* pushare il codice finito :)
* RISORSE:
    * framework css utilizzato: [http://getskeleton.com/](http://getskeleton.com/)
    * icone utilizzate: [https://www.iconfinder.com/iconsets/bitsies](https://www.iconfinder.com/iconsets/bitsies)

Scrivetemi pure per info
