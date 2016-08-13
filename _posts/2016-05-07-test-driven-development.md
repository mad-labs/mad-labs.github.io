---
layout: post
title: Test Driven Development
category: sviluppo
tags: [Javascript, sviluppo, TDD, Test Driven Development]
excerpt_separator: <!--more-->
---

### Metodologia TDD - JavaScript testing con Jasmine

#### Test Driven Development

**test-driven development** (abbreviato in **TDD**), in italiano **sviluppo guidato dai test**[[1]](https://it.wikipedia.org/wiki/Test_driven_development#cite_note-1) o **sviluppo guidato dalle verifiche**[[2]](https://it.wikipedia.org/wiki/Test_driven_development#cite_note-2) è un modello di sviluppo del software che prevede che la stesura dei [test automatici](https://it.wikipedia.org/wiki/Automazione_del_collaudo_del_software) avvenga *prima* di quella del software che deve essere sottoposto a test, e che lo sviluppo del software applicativo sia orientato *esclusivamente*all'obiettivo di passare i test automatici precedentemente predisposti.
<!--more-->

Più in dettaglio, il TDD prevede la ripetizione di un breve ciclo di sviluppo in tre fasi, detto "ciclo TDD". Nella prima fase (detta "fase rossa"), il programmatore scrive un test automatico per la nuova funzione da sviluppare, che deve *fallire* in quanto la funzione non è stata ancora realizzata. Nella seconda fase (detta "fase verde"), il programmatore sviluppa la quantità *minima* di codice necessaria per passare il test. Nella terza fase (detta "fase grigia" o di [refactoring](https://it.wikipedia.org/wiki/Refactoring)), il programmatore esegue il refactoring del codice per adeguarlo a determinati standard di qualità.[[3]](https://it.wikipedia.org/wiki/Test_driven_development#cite_note-3)

L'invenzione del metodo (o la sua riscoperta[[4]](https://it.wikipedia.org/wiki/Test_driven_development#cite_note-4)) si deve a [Kent Beck](https://it.wikipedia.org/wiki/Kent_Beck), uno dei padri dell'[extreme programming](https://it.wikipedia.org/wiki/Extreme_programming) (XP) e delle [metodologie agili](https://it.wikipedia.org/wiki/Metodologie_agili). Il TDD è una delle 12 regole base dell'XP ma viene anche usato indipendentemente da questa metodologia;[[5]](https://it.wikipedia.org/wiki/Test_driven_development#cite_note-5) la sua applicazione è anche parte fondamentale dello sviluppo agile del software.[[6]](https://it.wikipedia.org/wiki/Test_driven_development#cite_note-6)

[https://it.wikipedia.org/wiki/Test_driven_development](https://it.wikipedia.org/wiki/Test_driven_development)

Il TDD si articola in brevi cicli che constano di tre fasi principali. La descrizione originale dei cicli TDD data da [Kent Beck](https://it.wikipedia.org/wiki/Kent_Beck)nel libro *Test-Driven Development by Example*[[7]](https://it.wikipedia.org/wiki/Test_driven_development#cite_note-Beck-7) è quella usata universalmente come riferimento.

### JASMIE - Behavior-Driven JavaScript

Jasmine is a behavior-driven development framework for testing JavaScript code. It does not depend on any other JavaScript frameworks. It does not require a DOM
[http://jasmine.github.io/](http://jasmine.github.io/)

Per il nostro progetto utilizzeremo la versione 2.2 di Jasmine: [http://jasmine.github.io/2.2/introduction.html](http://jasmine.github.io/2.2/introduction.html)

Una facile introduzione all’uso di Jasmine e alle tecniche TDD è reperibile qui:
[https://www.udacity.com/course/javascript-testing--ud549](https://www.udacity.com/course/javascript-testing--ud549)

Jamine utilizza un linguaggio di scrittura dei test derivante dalla BDD (Behavior-driven development), un’evoluzione della tecnica TDD che avvicina al business il modello di sviluppo, combinando quest’ultima con altre tecniche di design come la domain driven design e la Object Oriented analisys and design.

Essa si focalizza su:

* Where to start in the process
* What to test and what not to test
* How much to test in one go
* What to call the tests
* How to understand why a test fails

At the heart of BDD is a rethinking of the approach to the unit testing and acceptance testing that naturally arise with these issues. For example, BDD suggests that unit test names be whole sentences starting with a conditional verb ("should" in English for example) and should be written in order of business value.

La notazone di Jasmine deriva più precisamente da un noto strumento per TDD / BDD: RSpec ([https://en.wikipedia.org/wiki/RSpec](https://en.wikipedia.org/wiki/RSpec)), dove invece dell’utilizzo di linguaggio semi-formale per descrivere un test (solitamente una user story), viene utilizzato un linguaggio più tecnico, chiamato Specifica (o Spec per brevità).

A subcategory of behavior-driven development is formed by tools that use specifications as an input language rather than user stories. An example of this style is the RSpec tool that was also developed by Dan North. Specification tools don't use user stories as an input format for test scenarios but rather use functional specifications for units that are being tested. These specifications often have a more technical nature than user stories and are usually less convenient for communication with business personnel than are user stories.[2][22] An example of a specification for a stack might look like this:

> Specification: Hash
>
> When a new Hash is created
> Then it is empty
>
> When an element is added with a key
> Then it must Hash the correct information with that key
> And it must includes given key

Che può essere tradotta nel liguaggio di RSpec in questa forma:

{% highlight ruby %}
describe Hash do
  let(:hash) { Hash[:hello, 'world'] }

  it { expect(Hash.new).to eq({}) }

  it "hashes the correct information in a key" do
    expect(hash[:hello]).to eq('world')
  end

  it 'includes key' do
    hash.keys.include?(:hello).should be true
  end
end
{% endhighlight %}

Da qui si nota la somiglianza con Jasmine e i suoi costrutti.

[https://en.wikipedia.org/wiki/Behavior-driven_development](https://en.wikipedia.org/wiki/Behavior-driven_development)

NOTA:
Per utilizzare Jasmine senza webserver deve essere abilitato all’accesso a file locali

#### Firefox
> In the address bar type in "about:config"
> Set the "Security.fileuri.strict_origin_policy" to false
> see [http://kb.mozillazine.org/Security.fileuri.strict_origin_policy](http://kb.mozillazine.org/Security.fileuri.strict_origin_policy)

#### Chrome
> Load chrome with the "--allow-file-access-from-files" command line flag set
> see [http://www.chromium.org/developers/how-tos/run-chromium-with-flags
> see [here](http://www.chromium.org/developers/how-tos/run-chromium-with-flags)
](http://www.chromium.org/developers/how-tos/run-chromium-with-flags)

aprendolo con il flag:

```
--allow-file-access-from-files
```

Da bash:

```
$ google-chrome --allow-file-access-from-files
```
