# Legarea Explicită a Funcțiilor

[slide hideTitle]

# Explicit Binding

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-16-17-explicit-binding-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Legarea ne permite să modificăm contextul unei funcții, schimbând ținta indicată de cuvântului cheie `this`.

**Explicit binding** este ceea ce se întâmplă atunci când folosim `call()`, `apply()` sau `bind()` pe o funcție. 

Acest lucru ne permite să legăm o funcție de un anumit obiect și să o folosim ca și cum ar fi o metodă a acelui obiect.

Acest lucru schimbă în esență contextul lui `this`. 

Cu alte cuvinte, legăm funcția de un context la alegerea noastră.

Să ne uităm la un exemplu în care este folosită funcșia `call()`:

```js live
function speak(message) {
    console.log(`My name is ${this.name}. ${message}`);
}

let person = {
    name: 'John'
};

speak.call(person, 'This is my story...');
```
În mod normal `this` indică **obiectul global** sau **fereastra** și ar fi trebuit să returneze `undefined` pentru `this.name`.

Am legat în mod explicit obiectul **person** de funcția `speak()`, folosind `call()`.

Aceasta este o funcție externă, dar totuși se comportă ca și cum `speak()` este o metodă care aparține obiectului person.

[/slide]

[slide hideTitle]

# Schimbarea Contextului: Call()

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-18-19-changing-the-context-call-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

`call()` apelează o funcție cu o valoare dată de `this` și argumente opționale. Ea schimbă contextul funcției la obiectul dat.

```js
functionName.call(objectToBind, additionalArguments);
```

Puteți avea 0, 1 sau mai multe argumente și atunci când apelați obiectul le puteți adăuga astfel: `function.call(object, argument1, argument2, argumentN)`;

Metoda `call()` nu face o copie a funcției, ci o execută imediat.

```js live
let praise = function(...praises) {
    console.log(`This is ${this.name}.`);

    let compliments = praises.reduce((acc, curr) => {
        let el = `-- ${curr}\n`;
        return acc + el;
    }, `He is:\n`).trim();
    return compliments;
}

let dog = {
    name: 'Rex',
}

console.log(praise.call(dog,
    'A good boy', 'My best friend'));


let cat = {
    name: 'Charlie'
}

console.log(praise.call(cat,
    'A good companion', 'A goofball'));
```

În exemplul de mai sus, puteți vedea că am folosit aceeași funcție care nu aparținea niciunui obiect și am legat acele obiecte de ea.

De fiecare dată când am folosit `call()` contextul lui `this` a fot diferit.

[/slide]

[slide hideTitle]

# Schimbarea contextului: Apply()

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-20-changing-the-context-apply-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

`apply()` și `call()` au același scop. Cu toate aceste, `call()` acceptă o listă de argumente, în timp ce `apply()` acceptă matrice.

Pentru a ilustra acest lucru folosind exemplul anterior:

Folosind `call()`:

```js
console.log(praise.call(dog,
    'A good boy', 'My best friend'
));
```

Folosind ``apply()``:

```js
console.log(praise.apply(dog,
    ['A good boy', 'My best friend']
));
```

Dacă aveți o matrice de argumente, puteți utiliza în continuare `call()` folosind operatorul spread:

```js
functionName.call(thisContext, ...[yourArray]);
```

[/slide]


[slide hideTitle]

# Exemplu pentru Apply()

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-21-apply-example-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

```js live
const firstPerson = {
    name: 'Peter',
    prof: 'Fisherman',
    shareInfo: function() {
        console.log(`${this.name} works as a ${this.prof}`);
    }
};

const secondPerson = {
    name: 'George',
    prof: 'Manager'
};
firstPerson.shareInfo.apply(secondPerson);
// George works as a Manager
```

[/slide]

[slide hideTitle]

# Schimbarea Contextului: Bind()

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-22-changing-the-context-bind-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

`bind()` creează o **funcție nouă** și are setat `this` la orice valoare furnizată de noi.

Funcția nu este executată direct, atunci când utilizăm `bind()`. 

În esență, această funcție permite obiectelor să împrumute metode de la alte obiecte fără ca noi să facem manual copii ale acelei metode.

Să ne imaginăm că avem un **student** cu metoda `study()`:

```js
let student = {
    alias: `Motivated student`,
    subject: 'Web Development',
    study: function(hours) {
        console.log(`${this.alias} studies 
      ${this.subject} ${hours} hours a day`);
    }
};
```

Avem și un profesor cu metoda `teach()`:

```js
let professor = {
    alias: `Grumpy professor`,
    subject: 'Mathematics',
    teach: function(hours) {
        console.log(`${this.alias} teaches ${this.subject} ${hours} hours a day`)
    }
};
```

Acum imaginați-vă că studentul a avansat atât de mult încât acum a dobândit metoda `teach()`. 

Folosiți `bind()` pentru a împrumuta metoda de la obiectul **professor**.

```js
let teach = professor.teach.bind(student, 2);
teach();
// Motivated student teaches Web Development for 2 hours a day
```

Folosind `bind(student, 2)` am trecut obiectul **student** ca prim argument, schimbând contextul lui `this` de la **professor** la **student** și am trecut **2** ca al doilea argument.

Urmăriți acest exemplu:

```js live
let student = {
    alias: `Motivated student`,
    subject: 'Web Development',
    study: function(hours) {
        console.log(`${this.alias} studies 
      ${this.subject} ${hours} hours a day`);
    }
};

let professor = {
    alias: `Grumpy professor`,
    subject: 'Mathematics',
    teach: function(hours) {
        console.log(`${this.alias} teaches ${this.subject} ${hours} hours a day`)
    }
};

let teach = professor.teach.bind(student, 2);
teach();
```

Acest lucru este cunoscut drept împrumutare de funcții în JavaScript. 

[/slide]

[slide hideTitle]

# Exemplu pentru Bind()

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-23-bind-example-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

```js live
const x = 42;
const getX = function() {
    return this.x;
}
const module = {
    x,
    getX
};
const unboundGetX = module.getX;
console.log(unboundGetX()); // undefined
const boundGetX = unboundGetX.bind(module);
console.log(boundGetX()); // 42
```

[/slide]

[slide hideTitle]

# Problemă cu Soluție: Area and Volume Calculator

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-26-solution-area-and-volume-calculator-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="Area and Volume Calculator" taskId="js-advanced-function-context-Area-and-Volume-Calculator" executionType="tests-execution" executionStrategy="javascript-unit-tests-with-mocha" requiresInput] [code-editor language=javascript]

```
function calculator(area, vol, input) {
    // Scrieți codul dvs. aici
}
```
[/code-editor]
[task-description]
# Descriere

Scrieți o funcție care **calculează** **aria** și **volumul** unei figuri **definite** prin **coordonatele sale** (**x**, **y**, **z**). 

Funcțiile **area** și **vol** sunt **transmise ca parametri** pentru funcția voastră:

```js
function area() {
  return this.x * this.y;
};
```

```js
function vol() {
  return this.x * this.y * this.z;
};
```

## Intrare
Veți primi 3 parametri - funcțiile **area** și **vol** și **un șir care conține coordonatele figurii**.

**Pentru mai multe informații verificați exemplele.**


## Ieșire
Rezultatul trebuie să fie **returnat** sub forma unei **matrice de obiecte**. Fiecare obiect are **două proprietăți**: **aria** și **volumul** figurii.

```js
[
  { area: ${area1}, volume: ${volume1} },
  { area: ${area2}, volume: ${volume2} },
  ...
]

```

**Notă: trimiteți numai funcția**.

# Exemple
## Exemplul 1

## Intrare 

```js
area, vol, '[ 
{"x":"1","y":"2","z":"10"}, 
{"x":"7","y":"7","z":"10"}, 
{"x":"5","y":"2","z":"10"} 
]'
```

## Ieșire

```js
[
  { area: 2, volume: 20 }, 
  { area: 49, volume: 490 },
  { area: 10, volume: 100 }
]
```

## Exemplul 2
## Intrare

```js
area, vol, '[ 
{"x":"10","y":"-22","z":"10"}, 
{"x":"47","y":"7","z":"-5"}, 
{"x":"55","y":"8","z":"0"}, 
{"x":"100","y":"100","z":"100"}, 
{"x":"55","y":"80","z":"250"} 
]' 
```

## Ieșire

```js
[
  { area: 220, volume: 2200 },
  { area: 329, volume: 1645 },
  { area: 440, volume: 0 },
  { area: 10000, volume: 1000000 },
  { area: 4400, volume: 1100000 }
]
```

[/task-description]
[code-io /]
[tests]
[test]
[input]
function area() \{
    return this.x \* this.y\*156;
\};
function vol() \{
    return this.x \* this.y \* this.z;
\};
let actual = result(area, vol,'\[\{"x":"1","y":"2","z":"10"\},\{"x":"7","y":"7","z":"10"\},\{"x":"5","y":"2","z":"10"\}\]');
let expected = \[
  \{ area: 312, volume: 20 \},
  \{ area: 7644, volume: 490 \},
  \{ area: 1560, volume: 100 \}
\];
assert.deepEqual(actual,expected,"The returned value is not correct")
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
function area() \{
    return this.x \* this.y\*3;
\};
function vol() \{
    return this.x \* this.y \* this.z/16;
\};
let actual = result(area, vol,'\[\{"x":"1","y":"2","z":"10"\},\{"x":"7","y":"7","z":"10"\},\{"x":"5","y":"2","z":"10"\}\]');
let expected = \[
  \{ area: 6, volume: 1.25 \},
  \{ area: 147, volume: 30.625 \},
  \{ area: 30, volume: 6.25 \}
\]
assert.deepEqual(actual,expected,"The returned value is not correct")
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
function area() \{
    return this.x \* this.y;
\};
function vol() \{
    return this.x \* this.y \* this.z;
\};
let actual = result(area, vol,'\[\{"x":"1","y":"2","z":"10"\},\{"x":"7","y":"7","z":"10"\},\{"x":"5","y":"2","z":"10"\}\]');
let expected = \[
  \{ area: 2, volume: 20 \},
  \{ area: 49, volume: 490 \},
  \{ area: 10, volume: 100 \}
\];
assert.deepEqual(actual,expected,"The returned value is not correct")
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
function area() \{
    return this.x \* this.y;
\};
function vol() \{
    return this.x \* this.y \* this.z;
\};
let actual = result(area, vol,'\[\{"x":"10","y":"-22","z":"10"\},\{"x":"47","y":"7","z":"-5"\},\{"x":"55","y":"8","z":"0"\},\{"x":"100","y":"100","z":"100"\},\{"x":"55","y":"80","z":"250"\}\]');
let expected = \[
  \{ area: 220, volume: 2200 \},
  \{ area: 329, volume: 1645 \},
  \{ area: 440, volume: 0 \},
  \{ area: 10000, volume: 1000000 \},
  \{ area: 4400, volume: 1100000 \}
\];
assert.deepEqual(actual,expected,"The returned value is not correct")
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]
