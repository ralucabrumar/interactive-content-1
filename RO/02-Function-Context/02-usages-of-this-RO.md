# Utilizarea lui "this"

[slide hideTitle]

# "this" într-o Metodă

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-8-9-this-in-a-method-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Când se află în interiorul unei metode, `this` este folosit pentru a accesa informațiile, stocate în obiect, care "deține" obiectul:

```js live
let cat = {
    name: 'Muffins',
    breed: 'British Shorthair',

    info: function() {
        return `${this.name} is a ${this.breed}.`
    },
    whatIsThis: function() {
        return this;
    }
}
console.log(cat.info());
console.log('******************');
console.log(cat.whatIsThis());
```

Exemplul de mai sus ilustrează modul în care `this` este folosit pentru a recupera valorile stocate în proprietățile obiectului **cat**.

De fiecare dată când folosim `this` într-o metodă, se referă la obiectul în sine și, prin urmare `cat.whatIsThis()` returnează obiectul cat.

De asemenea, puteți prelua valorile proprietăților obiectului înlocuind `this` cu numele obiectului.

```js
info: function() {
        return `${this.name} is a ${this.breed}.`
    },
    whatIsThis: function() {
        return cat;
    }
```

Aceasta nu este o practică bună și va face codul mai greu de întreținut.
 
Imaginați-vă că în viitor poate veți dori să schimbați numele obiectului, dar veți uita să efectuați aceste modificări în metodele voastre.

**Notă:** Încercarea de a returna **name** sau **breed** fără `this` va avea consecințe nedorite.

Dacă nu există nicio variabilă cu același nume în afara domeniul proiectului, rezultatul va fi **undefined**. 

Dacă există o variabilă cu același nume deja definită și dacă se află în domeniul său de aplicare, valoarea acesteia va fi returnată.

[/slide]

[slide hideTitle]

# "this" se Referă la Obiectul Părinte

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-10-this-refers-to-the-parent-object-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Luați în considerare exemplul de mai jos:

```js live
// Definirea unei funcții
function printContext() {
    console.log(this === global);
}
// Crearea unui obiect numit user
let user = {
    count: 10,
    printContext: printContext,
    printAnotherContext: function() {
        console.log(this === global);
    }
}

user.printContext();

let globalFunction = user.printAnotherContext;

globalFunction();

user.printAnotherContext();
```

Să vedem ce se întâmplă în codul pas cu pas pentru a-l înțelege mai bine.

Mai întâi, definim o funcție `printContext()` care verifică dacă `this===global` (`this===window` dacă este rulată în browser) și imprimă rezultatul pe consolă.

Apoi, vom crea un obiect **user** cu două metode:

- `printContext: printContext` - stochează funcția **printContext** definită la pasul 1 într-o metodă cu același nume

- `printAnotherContext: function() { console.log(this === global); }` - metoda **printAnotherContext** verifică dacă  `this === global` și imprimă rezultatul pe consolă

Apelarea funcției `user.printContext();` invocă metoda care aparține obiectului **user**. Returnează **false**, deoarece `this` este utilizat în cadrul metodei unui obiect și returnează obiectul propriu-zis.

`let globalFunction = user.printAnotherContext;` 

Acum, definim o nouă funcție și îi atribuim metoda **printAnotherContext** care aparține de obiectul **user**.

Returnează **true**, deoarece acum `this` este apelat de funcția **globalFunction** și nu din metoda obiectului **user**.

`this` este într-adevăr echivalent cu **global**.

- `user.printAnotherContext();` va returna **false** deoarece `printAnotherContext()` este o metodă a obiectului **user** și `this` va returna obiectul propriu-zis, la fel ca în cazul metodei **printContext**

**Să rezumăm:**

- Folosit în metode, `this` face referire la obiectul căruia îi aparține metoda

- Folosit într-o funcție, `this` face referire la obiectul **global** cum ar fi **window** în browser sau **global** în Node

[/slide]

[slide hideTitle]

# În Evenimente

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-11-in-events-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Atunci când este utilizat într-un handler de eveniment, `this` indică elementul specific din care a fost declanșat evenimentul.

Aici, creăm un fișier HTML și atașăm următorul handler de eveniment la un element cu id-ul "button".
```js
function solve() {
    let button = document.getElementById('button');

    button.addEventListener('click', function(e) {
        console.log(this);
    });
}
```

Când se face referire la `this` din interiorul unui eveniment, acesta returnează elementul din care a fost apelat evenimentul.

În cazul nostru, button va fi elementul care a apelat funcția `solve()`.

Îl puteți testa singuri creând un fișier HTML cu următorul exemplu de cod:

```js
<html>
   <body>
      <p>Welcome to your code playground!</p>
      <button id="button">Click me</button>
      <script>
         function solve() {
             let button = document.getElementById('button');
         
             button.addEventListener('click', function (e) {
                 console.log(this);
             });
         }
         solve();
      </script>
   </body>
</html>
```

Dacă faceți clic pe butonul din exemplu, în consolă va fi afișat următorul rezultat:

[image assetsSrc="function-context-04.png" /]

[/slide]

[slide hideTitle]

# În Clase

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-12-this-in-classes-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Când este utilizat în clase, valoarea lui `this` se referă la instanța clasei pe care o inițializați utilizând cuvântul cheie `new`.

```js live
class Vehicle {
    constructor(make, model) {
        this.make = make;
        this.model = model;
        this.displayInfo = function() {
            console.log(`The vehicle is a ${this.make} ${this.model}.`);
        }
    }
};

let car = new Vehicle('Toyota', 'Corolla');
car.displayInfo();
```

În exemplul de mai sus, accesăm proprietățile clasei **car** folosind `this.`.

Amintiți-vă că am aflat anterior despre utilizarea cuvântului cheie `this` în obiecte, acesta comportându-se în același mod.

Acest lucru se datorează faptului că clasele sunt șabloane pentru crearea obiectelor.

[/slide]
