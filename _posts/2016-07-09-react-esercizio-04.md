---
layout: tutorial-post
title: React - Esercizio 04
category: React
tags: [Javascript, React, front end, framework]
excerpt_separator: <!--more-->
tutorial_tile: FLUXiamoci!
---

In Questo esercizio inizieremo a capire un po' FLUX e come utilizzarlo per gestire i dati in un'applicazione React.
<!--more-->

Come si può leggere in quasi tutti i tutorial FLUX è un pattern architetturale che a volte è un po' eccessivo se i dati scambiati fra i componenti dall'applicazione non sono tantissimi. Ma per farci le ossa lo usaremo lo stesso anche nella nostra piccola APP. Per prima cosa leggeremo dei tutorial e poi ne seguiremo uno per capire le basi.

Eccoli:

* una breve introduzione a FLUX e al suo utilizzo:
  * [http://blog.andrewray.me/flux-for-stupid-people/](http://blog.andrewray.me/flux-for-stupid-people/)
* una panoramica completa su cosa è FLUX e sul suo utilizzo:
  * [http://fluxxor.com/what-is-flux.html](http://fluxxor.com/what-is-flux.html)

### IL TUTORIAL
Finalmente, dopo la teoria, scriviamo qualche riga di codice per tirare fuori un esempio completo di applicazione React / Flux!

* [https://tonyspiro.com/building-a-simple-react-application-using-the-flux-pattern/](https://tonyspiro.com/building-a-simple-react-application-using-the-flux-pattern/)

#### SEGUENDO IL TUTORIAL 01...

Purtroppo la configurazione iniziale del tutorial non funziona: ho configurato prendendo un po' dal repository linkato e un po' da lla doc ufficiale. Ecco il risultato finale:

```javascript
var gulp = require('gulp'),
    browserify = require('browserify'),
    babelify = require('babelify'),
    source = require('vinyl-source-stream'),
    uglify = require('gulp-uglify'),
    rename = require('gulp-rename'),
    eslint = require('gulp-eslint');

gulp.task('watch', function () {
  gulp.watch("./src/*.js", ['default']);
  gulp.watch("./src/*.jsx", ['default']);
  gulp.watch("./src/components/*.jsx", ['default']);
  gulp.watch("./src/dispatcher/*.js", ['default']);
  gulp.watch("./src/stores/*.js", ['default']);
});

gulp.task('default', ['bundle']);

gulp.task('build', ['lint']);

gulp.task('lint', ['compress'], function () {
    return gulp.src([
      '**/*.js',
      '**/*.jsx',
      '!node_modules/**',
      '!build/**',
      '!gulpfile.js'])
    .pipe(eslint())
    .pipe(eslint.format())
    .pipe(eslint.failAfterError());
});

gulp.task('compress', ['bundle'], function() {
  return gulp.src('./build/bundle.js')
  .pipe(uglify())
  .pipe(rename({suffix: '.min'}))
  .pipe(gulp.dest('build'));
});

gulp.task('bundle', function () {
    return browserify({
      entries: './src/app.jsx',
      extensions: ['.jsx', '.js'],
      debug: true
    })
    .transform(babelify, {presets: ['es2015', 'react']})
    .bundle()
    .pipe(source('bundle.js'))
    .pipe(gulp.dest('build'));
});
```

#### SEGUENDO IL TUTORIAL 02...

Nota: durante il tutorial ho incontrato questo codice:

```javascript
//ListItem.js
{
  //...
  getItems: function () {
    return this.items;
  }
}
```

che ho prontamente trasformato in


```javascript
//ListItem.js
{
  //...
  getItems: () => {
    return this.items;
  }
}
```

bhe, non fatelo, perchè non funziona! Le arrow function non sono adatte per i metodi..

#### SEGUENDO IL TUTORIAL 03...

Per far funzionare il tutorial ho dovuto modificare il codice del file app.jsx aggiungendo la dipendenza a ReactDOM e cambiando la chiamata del metodo **React.render** in **ReactDOM.render**

```javascript
//app.jsx
import React from 'react';
import ReactDOM from 'react-dom';
import AppRoot from './components/AppRoot'; // we'll create this next

ReactDOM.render(<AppRoot />,
  document.getElementById('app-root')
);
```

#### SEGUENDO IL TUTORIAL 04...

Quando crea il componente NewItemForm in *NewItemForm.jsx* usa il dom per recuperare le informazioni del from. Non mi piace.. Molto meglio la soluzione che fornivano nel primo tutorial con le funzioni di cambiamento valore..

```javascript
//NewItemForm.jsx
import React from 'react';
import AppDispatcher from '../dispatcher/AppDispatcher';
import uid from 'uid';

class NewItemForm extends React.Component {

  constructor(){
    super();
    this.state = {
      itemTitle : ''
    };
  }

  handleTextChange(e) {
    this.setState({itemTitle: e.target.value});
  }

  createItem(e){
    e.preventDefault();
    let id = uid();
    var itemTitle = this.state.itemTitle.trim();
    if (itemTitle == ''){
      return;
    }

    this.setState({itemTitle:''});

    AppDispatcher.dispatch({
      action: 'add-item',
      new_item: {
        id: id,
        name: itemTitle
      }
    });
  }
  render (){
    return <form onSubmit={this.createItem.bind(this)}>
      <input type="text" ref="item_title" value={this.itemTitle} onChange={this.handleTextChange.bind(this)}/>
      <button>Add new item</button>
    </form>;
  }
}

export default NewItemForm;
```

#### SEGUENDO IL TUTORIAL 05...

Ecco un altra cosa che non funziona.. Sembra che il **ListStore**, nonostante estendesse **EventEmitter**, non supporti le funzioni *this.on(..)* e *this.emit()* .. Quindi ho rimediato creando una specie di Singleton con i moduli javascript. Se avete in mente il module pattern è molto simile.

```javascript
//ListStore.js
import EventEmitter from 'events';

class ListStore extends EventEmitter {

  constructor(){
    super();
    this.items = [
      {
        name: 'Item 1',
        id: 0
      },
      {
        name: 'Item 2',
        id: 1
      }
    ];
  }

  getItems() {
    console.log('getItems()');
    return this.items;
  }

  addItem(new_item){
    console.log('addItem(new_item) - new_item:' + new_item);
    this.items.push(new_item);
  }

  removeItem(item_id){
    console.log('removeItem(item_id) - item_id:' + item_id);
    this.items = this.items.filter(function(curr){
      return curr.id !== item_id;
    });
  }

  emitChange(){
    console.log('emitChange()');
    this.emit('list-store-change');
  }

  addChangeListener(callback){
    console.log('addChangeListener(callback)');
    this.on('list-store-change', callback);
  }

  removeChangeListener(callback){
    console.log('removeChangeListener(callback)');
    this.removeListerner('list-store-change', callback);
  }
}

export default new ListStore(); //ecco il singleton
```

#### EXTRA!!!

Dopo aver finito il tutorial ho deciso di applicare uno dei consigli del primo tutorial: ho messo in piedi un action dispatcher

```javascript
//ListActions.js
import AppDispatcher from './AppDispatcher';

class ListActions {

  constructor(){
    super();
  }

  addItemAction(id, itemTitle) {
    console.log('addItemAction(id, itemTitle)');
    AppDispatcher.dispatch({
      action: 'add-item',
      new_item: {
        id: id,
        name: itemTitle
      }
    });
  }

  removeItemAcion(id){
    console.log('removeItemAcion(id)');
    AppDispatcher.dispatch({
      action: 'remove-item',
      id: id
    });
  }
}

export default new ListActions();
```

dopodichè ho dovuto modificare due file per allienarli:

```javascript
//ListActions.js
{
  //...
  removeItem(e){
    let id = e.target.dataset.id;
    ListActions.removeItem(id);
  }
}
```

```javascript
//NewItemForm.js
{
  //...
  createItem(e){
    //...
    this.setState({itemTitle : ''});
    ListActions.addItem(id, itemTitle);
  }
}
```

### HERE WE GO!

E ora a noi! E qui senza aiuti!! Ecco cosa fare:

* clonare il progetto react-flux-homeworksV2 con **git clone ssh://git@worky01:/home/git/react-flux-homeworksV2.git** sul workspace
* creare un branch chiamato *wimm_***_proprionome_**
* leggere file README.TXT e seguire le istruzioni per installare GULP e le librerie necessarie
* seguire le norme imparate nel tutorial precedente per creare una semplice applicazione react/flux:
  * creare una pagina di "aggiunta spesa" (page2)![image alt text]({{ site.baseurl }}public/images/image_1.png)
    * la sezione sarà composta da:
      * un form per aggiungere una nuova spesa / modificarne una esistente
      * un riepilogo di tutte le spese inserite
      * uso del **form**
          * nel form va inserito un *importo in euro*, una *data* (prevalorizzata al giorno corrente) e un campo *nota*
          * un click sul **+ verde** conferma i dati e aggiunge la spesa nella lista sotto
          * Un click sulla **freccia rossa** resetta i dati
      * uso della **lista**
          * un click sulla **x rossa** cancella la spesa dalla lista e dal totale del mese
          * un click sulla **matita** carica i dati della spesa nel form e alla conferma li cambia nella lista e nel totale del mese

#### RISORSE

Ecco le risorse utilizzate in questo esercizio:

* framework css utilizzato: [http://getskeleton.com/](http://getskeleton.com/)
* icone utilizzate: [https://www.iconfinder.com/iconsets/bitsies](https://www.iconfinder.com/iconsets/bitsies)
