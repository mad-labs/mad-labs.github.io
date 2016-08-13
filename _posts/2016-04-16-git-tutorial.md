---
layout: post
title: Introduzione a GIT
category: git
tags: [tool, sorce control system, GIT]
excerpt_separator: <!--more-->
---

### GIT

GIT
[Guida tascabile Git](http://rogerdudler.github.io/git-guide/index.it.html)
<!--more-->

Scaricare Git

- andare sul motore di ricerca a cercare Git Download oppure andare direttamente al sito https://git-scm.com/download

- selezionare il sistema operativo sul quale bisogna installare il Git

- compare una finestrella con conferma di download. Attenzione! Il tipo di sistema di default è di 64 bit. Se non è quello indicato dal pc, fare annulla e selezionare, in una lista sottostante, il file con il tipo di sistema adeguato

Installare Git

- doppio click sull'eseguibile scaricato e fare click su Esegui

- Ti chiede di consentire al programma di apportare modifiche. Fare click su Sì

- Nella WIZARD Setup: Next, Next, Next, Next, selezionare 'Use Git from Git Bash only' e fare Next, Next, selezionare la seconda opzione e fare Next, selezionare MinTTY e fare Next, Install

Copiare progetto git

* Aprire il file Git Bash all’interno della cartella Git come **Amministratore **(in genere è in Programmi. Con Windows si può ricercarlo dalla barra di ricerca nello Start Menu)

* Raggiungere la cartella dove si vuole copiare il progetto (con l’utilizzo dei comandi **cd**, **ll** o **ls** per visualizzare i file presenti)

* Digitare *git clone git@worky01:/home/git/serverSideEventTut.git* (indicando la password, disponibile nel file Indirizzo Host Git)

Salvare password dell’utenza al server con Git Bash

* ssh-keygen

* ssh-copy-id nome_utente@nome_server

la consolle ti chiederà di effettuare una prova d'accesso. Fare:

* ssh nome_utente@nome_server

Push nuovo repository in remoto

* ssh git@worky01

* git init --bare /home/git/testTutorial.git

* cd testTutorial/ (nome cartella da aggiungere al remoto)

* git remote add origin git@worky01:/home/git/testTutorial.git

* git add .

* git commit

* git push --set-upstream origin master
