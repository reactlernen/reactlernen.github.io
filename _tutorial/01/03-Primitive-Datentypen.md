---
layout: tutorial

lecture: "1"
lecture_title: "JavaScript und ECMAScript"

sublecture: "3"
sublecture_title: "Primitive Datentypen"

date: 2020-05-22
categories: tutorial update

author: Pawel Sawicki
---

![Essen kann viele Werte annehmen](/assets/food.jpg)

## Ein leckeres Gericht zum Essen

Nun sitzt Du vor dem Computer und arbeitest Dich durch das JavaScript Tutorial durch. Du kriegst Hunger und rufst beim Bestellservice an:
> Hallo, ist da Leckerfood? Ich habe sehr großen Hunger. Bitte liefern Sie mir schnellstmöglich ein leckeres <em>Gericht</em> zum Essen.

Endlich klingelt der Liferant an der Tür. In der Hoffnung auf ein leckeres **Gericht**, machst Du auf.

Zu Deiner Überraschung überreicht Dir der Lieferant einen Korb voller **Steine**. Das ist sicherlich nicht, was Du erwartet hast.

Akzeptable ***Werte*** für ein *Gericht* sind unter anderem: ***Pizza***, ***Burger***, ***Pommes***, ***Fischbrötchen***, ***...***

<p class="definition">
Der <em>Datentyp</em> (kurz: <em>Typ</em>) einer <em>Variable</em> sagt aus, welche Werte für diese Variable möglich sind.
</p>

Mit diesem Beispiel hast Du mit ***Gericht*** einen ***Datentyp*** kennengelernt. Variablen vom Typ *Gericht* können die Werte ***Pizza***, ***Burger***, ***Pommes***, ***Fischbrötchen***, **u.ä.** annehmen. ***Steine*** ist ein ungültiger Wert, der zu Unmut führt.

## Primitive Datentypen in JavaScript

Auch in JavaScript könnten wir einen Datentypen wie *Gericht* definieren. Dies ist jedoch ein recht komplexes Unterfangen, wenn man bedenkt, aus wievielen Zutaten ein Gericht bestehen kann. In JavaScript gibt es einige elementare Datentypen, ***Primitive Datentypen*** genannt, die man direkt nutzen kann um Sachverhalte zu beschreiben.
<p class="info">
Aus den <em>Primitiven Datentypen</em> können auch komplexere Datentypen zusammengestellt werden, wie bspw. das hier genannte <em>Gericht</em>. Nur Geduld, im Laufe des Tutorials werden wir Beispiele dazu sehen.
</p>

<p class="definition">
In JavaScript bezeichnet man die <i>kleinsten</i> <i>vordefinierten</i> Datentypen, die <i>nicht weiter teilbar</i> sind, als <em>Primitiver Datentyp</em>. Dazu gehört: <em>number</em>, <em>string</em> und <em>boolean</em>.
</p>

Im Folgenden soll auf die am häufigst verwendeten *Primitive Datentypen* eingegangen werden.

### Zahlen und numerische Größen &#x2192; number

In JavaScript nutzt man den Datentyp ```number``` um Zahlen und numerische Größen zu beschreiben.

```javascript
// (1) Die Kreiszahl pi ist eine reelle Zahl und somit eine number
const pi = 3.141592;

// (2) Der radius ist ebenfalls eine reele Zahl und somit eine number
let radius = 5.0;

// (3) Die ganzzahlige Konstante 2 ist ebenfalls eine number
// (4) Mit numbern lässt es sich rechnen.
const flaeche = 2 * pi * radius; // (5) Die flaeche ist ebenfalls eine number
```
1. Hier deklarieren und definieren wir die Konstante *pi* (&#x3C0;). &#x3C0; ist eine reelle Zahl. JavaScript nutzt den Datentypen ```number``` um reelle Zahlen intern zu repräsentieren. Beachte, dass man in JavaScript anstatt des Kommas einen Punkt ```.``` schreibt.
2. Hier deklarieren und definieren wir die Variable *radius* explizit als reelle Zahl, obwohl nach dem Komma (Punkt) kein Bruch kommt. Da bei dem intern verwendeten Datentyp ```number``` nicht zwischen ganzen und reellen Zahlen unterschieden wird, dient das an dieser Stelle nur der Lesbarkeit: Die Variable *radius* akzeptiert auch Nachkommastellen.
3. Der Konstante Wert *2* ist ebenfalls eine ```number```.
4. In JavaScript sind die üblichen Rechenoperationen auf Zahlen möglich: ```+``` (addieren), ```-``` (substrahieren), ```*``` (multiplizieren), ```/``` (dividiren) und ```**``` (exponieren). Auch ```%``` (Modulo) ist möglich.
5. Das Resultat einer Rechnung auf dem Datentypen ```number``` ist ebenfalls eine ```number```.


<p class="info">
Wie in der Mathematik üblich, gilt auch in JavaScript: <em>Punkt- vor Strichrechnung</em>. Sofern man explizit Anderweitiges mag, hat man die Möglichkeit mit <em>(</em> und <em>)</em> zu klammern.
</p>
```javascript
const x = 3 + 5 * 2;    // ergibt für x: 13
const y = (x + 3) / 8;  // ergibt für y: 2
```

<p class="info">
Neben den Grundrechenoperationen finden wir weitere nützliche <em>Funktionen</em> zur Anwendung auf dem Datentypen <em>number</em> im Modul <a href="https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/Math#Methods"><em>Math</em></a>.
</p>

Lass uns die Hypotenuse ***c*** eines rechtwinkligen Dreieckes, mit den gegebenen Seiten **a** und **b**, unter Verwendung des [Satzes des Pythagoras](https://de.wikipedia.org/wiki/Satz_des_Pythagoras), berechnen:
```javascript
const a = 5;    // Gegeben: Seite a vom Typ number
const b = 8;    // Gegeben: Seite b vom Typ number

const c = Math.sqrt(a**2 + b**2);   // ergibt für c: 9.433981132056603
```

### Alphanumerische Zeichen und Zeichenketten &#x2192; string

In JavaScript fasst man einzelne Buchstaben (allgemeiner: Zeichen) oder deren An­ei­n­an­der­rei­hung (Worte, Sätze, Bezeichner uvm.) unter dem Datentyp ***string***, was auf Deutsch so viel wie ***Zeichenkette*** bedeutet, zusammen. 

Zeichenketten werden i.d.R. immer dann genutzt, wenn was ausgegeben werden soll.

Gehen wir von unserem Beispiel mit dem Gericht aus:
```javascript
const SEATTIGUNG_SEHR_HUGRIG = -1;  // (1) numerische Konstanten
const SAETTIGUNG_HUNGER = 0;
const SAETTIGUNG_KANN_MEHR = 1;
const SAETTIGUNG_SATT = 2;

let gericht = 'Pizza';              // (2) Das gelieferte Gericht.

let satt = SAETTIGUNG_HUNGER;       // (3) Ich habe Hunger!

if (gericht === 'Pizza') {          // (4) strings können verglichen werden.
    satt = SAETTIGUNG_SATT;
} else if (gericht === 'Burger' || gericht === 'Fischbrötchen') {
    satt = SAETTIGUNG_KANN_MEHR;
} else if (gericht === 'Pommes') {
    satt = SAETTIGUNG_HUNGER;
} else {
    satt = SEATTIGUNG_SEHR_HUGRIG;
}

let freude;
if (satt === SAETTIGUNG_SATT) {
    freude = 'Lecker ' + gericht + '. Ich bin satt.'; // (5) string Verkettung
} else if (satt === SAETTIGUNG_KANN_MEHR) {
    freude = "Mmm " + gericht + ". Ich könnt's immer essen."; // (6) string Verkettung
} else if (satt === SAETTIGUNG_HUNGER) {
    freude = `Mmm ${gericht}. Was für kleine Portion.`; // (7) template string
} else {
    freude = `Oh, nein! Was ist ${gericht}?. Das esse ich nicht.`;
}

console.log(freude); // Ausgabe: Lecker Pizza. Ich bin satt.
```

1. Hier sehen wir einige Konstanten vom Datentyp ***number***, die dazu genutzt werden unser Sättigungsgefühl zu kodieren.
2. Die Deklaration der Variable ***gericht*** vom Datentyp ***string***. Initial nimmt die Variable den Wert ```'Pizza'``` an. Beachte hier die umschließenden ***einfachen Hochkomma***: ```'```
3. Hier wird die numerische Variable ***satt*** deklariert und definiert. 
4. Ein *string* kann mit einem anderen *string* verglichen werden. Hierzu nutzt man den ```===``` Vergleichsoperator.
5. Mehrere *strings* können zu einem resultierenden *string* ***verkettet*** werden. Hierzu nutzt man den ```+``` Operator.
6. *strings* können alternativ auch mit ***doppelten Hochkomma*** ```"``` umschloßen werden. Dies ist dann sinnvoll, wenn der *string* einfache Hochkomma beinhaltet.
7. Anstatt *strings* zu verketten, kann man den *string* auch mit sogenannten ***backticks*** ``` ` ``` umschließen um auf den Kontext zuzugreifen: `${eineVariable}`.
