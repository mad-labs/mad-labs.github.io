---
layout: tutorial-post
title: React - Esercizio 02
category: React
tags: [Javascript, React, front end, framework]
excerpt_separator: <!--more-->
tutorial_tile: Un Giocooo! Un Giocooo!
---

Adesso che sappiamo leggere e seguire un turorial su React è il momento di impegnarsi un po' per diventare indipendenti. Sarebbe carino riuscire a fare un semplice gioco utilizzando React?
<!--more-->

Il gioco è il fantastico e mai noiso (see, certo..) gioco del *TRIS*!! O come lo chiamano gli anglofili: *Tic Tac Toe*!! Ora leggeremo dei tutorial per rinfrescarci le basi e apprendere come scomporre una pagina nei suoi singoli componenti. Poi creeremo una specie di gioco del *TRIS*, molto, molto semplice :)

Ecco i tutorial:

* Un bel tutorial sui concetti di base, giusto per rinfrescarli:
  * [http://blog.andrewray.me/reactjs-for-stupid-people/](http://blog.andrewray.me/reactjs-for-stupid-people/)
* ecco un altro tuorial introduttivo: notare la parte in cui scompone una pagina html in componenti React
  * [https://blog.risingstack.com/the-react-way-getting-started-tutorial/](https://blog.risingstack.com/the-react-way-getting-started-tutorial/)
  leggete pure fino a *React loves ES6*, il resto sono argomenti che affronteremo più avanti!!

### HERE WE GO!

E ora a noi! Via con il tris! Ecco i passi per eseguire questo esercizio :

* create un file chiamato ***index.html***, che sarà il nostro template, con questo contenuto:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta charset="utf-8">
    <link rel="stylesheet" href="basic.css">
    <title>Tic Tac Toe Tutorial</title>
  </head>
  <body>
    <div id="content"></div>
    <div class="wrapper">
      <header class="header">Psychedelic Tic Tac Toe!</header>
      <article class="main">
        <table id='board'>
          <tbody>
            <tr>
              <td>X</td><td>X</td><td>X</td>
            </tr>
            <tr>
              <td>X</td><td>X</td><td>X</td>
            </tr>
            <tr>
              <td>X</td><td>X</td><td>X</td>
            </tr>
          </tbody>
        </table>
      </article>
      <aside class="aside aside-1">Player X</aside>
      <aside class="aside aside-2">Palyer O</aside>
      <footer class="footer">by MadLabs</footer>
    </div>
    <script src="build/app.js"></script>
  </body>
</html>
```
e un file chiamto ***basic.css*** per creare lo stile:

```css
* {
  margin: 0;
  padding: 0;
}

.wrapper {
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  -webkit-flex-flow: row wrap;
  flex-flow: row wrap;
  font-weight: bold;
  text-align: center;
}

.wrapper > * {
  padding: 10px;
  flex: 1 100%;
}

.header {
  background: tomato;
}

.main {
  text-align: center;
  background: deepskyblue;
  order: 2;
  flex: 3 0px;
}

.aside {
  flex: 1 auto;
}

.aside-1 {
  order: 1;
  background: gold;
}

.aside-2 {
  order: 3;
  background: hotpink;
}

.footer {
  background: lightgreen;
  order: 4;
}

body {
  padding: 2em;
}

table {
  border-collapse: collapse;
  border-spacing: 0;
}

#board {
  padding: 0px;
  margin: 0 auto;
  margin-top: 25px;
  margin-bottom: 25px;
}

#board tr td {
  width: 80px;
  height: 80px;
  border: 1px solid #1c1c1c;
  font-family: Helvetica;
  font-size: 30px;
  text-align: center;
}

#board tr td:hover {
  background: #e4e4e4;
  cursor: pointer;
}
```

***et voilà*** abbiamo il nostro template!!

* clonare il progetto react-flux-homeworks con **git clone ssh://git@worky01:/home/git/react-flux-homeworks.git** sul workspace
  * il progetto contiene un template in html da utilizzare per l'esercizio
* creare un branch chiamato *tictactoe_***_proprionome_**
* leggere file README.TXT e seguire le istruzioni per installare le dipendenze e l'ambiente
* ora seguendo le norme imparate nel tutorial precedente per creare un gioco del tris con react
  * partendo dal mockup html scomporre e disegnare i componenti React
  * creare un albero dei componenti
  * implementare l’interfaccia di gioco in React in modo che il click sulle celle VUOTE segni il simbolo di uno dei due giocatori alternativamente:
    * il primo click segna **X** su una casella
    * il secondo click segna **O** su una casella
    * se la cella è già occupata non deve essere inserito nessun simbolo

***et voilà*** abbiamo il nostro Giocooo!!

#### RISORSE

Un paio di link utili alla realizzazione dell'esercizio sono:

* [html-tags-vs.-react-components](http://snip.ly/7DTB#https://facebook.github.io/react/docs/jsx-in-depth.html#html-tags-vs.-react-components)
* [lifecycle-methods](https://facebook.github.io/react/docs/component-specs.html#lifecycle-methods)
