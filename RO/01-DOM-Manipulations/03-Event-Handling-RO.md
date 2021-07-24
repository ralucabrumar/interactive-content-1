# Gestionarea Evenimentelor

[slide hideTitle]

# Handler de Evenimente

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-19-20-event-handler-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Înregistrarea unui eveniment este făcută printr-o funcție de apel invers. 

Există 3 moduri de a înregistra un eveniment:

- Folosind Atribute HTML

- Folosind proprietățile evenimentelor DOM

- Folosind un handler DOM de evenimente 

[/slide]

[slide hideTitle]

# Ascultător de Evenimente

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-21-event-listener-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Pentru a putea folosi funcția noastră **handler**, avem nevoie de metoda `.addEventListener()`.

Primul parametru este **tipul evenimentului**, care este un șir case-sensitive ce reprezintă tipul de eveniment pe care dorim să-l ascultăm. 

Al doilea parametru este funcția **handler**. Acesta îi spune funcției să ruleze, atunci când evenimentul are loc. 

Al treilea parametru este opțional. Este o valoare Booleană care specifică dacă evenimentul trebuie să fie executat în faza de capturare sau în faza de bubbling.

Valoarea ei inițială este false. 

O altă metodă utilă despre care trebui să știm este metoda `.removeEventListener()`.

Ea elimină un handler de evenimente care a fost atașat anterior cu metoda `addEventListener()`.


```js
addBtn.addEventListener('click', handler, false);
```

O altă metoda este metoda `.removeEventListener()`.

Ea elimină din țintă ascultătorul de evenimente înregistrat anterior. 

```js
addBtn.removeEventListener('click', handler);
```
[/slide]

[slide hideTitle]

# Atașarea Evenimentelor de Tip Click

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-22-attaching-click-event-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Aici avem un exemplu pentru utilizarea tipului "**click**" și a funcției "**clickMe**", ca handler de evenimente.

La fiecare click pe buton, "**number**" va fi incrementat cu unu.

```js
const button = document.getElementsByTagName('button')[0];
button.addEventListener('click', clickMe);

function clickMe(e) {
    const target = e.currentTarget;
    const targetText = target.textContent;
    target.textContent = Number(targetText) + 1;
}
```

[/slide]

[slide hideTitle]

# Atașarea Evenimentelor de Tip Hover și Input

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-23-24-attaching-hover-event-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

## Atașarea unui Eveniment Hover

Aici avem un exemplu de folosire a tipului "**mouseOver**" și o declarare de funcție. 

Codul va rula dacă dacă trecem cu mouse-ul peste buton.

Rezultatul va fi o schimbare a culorii de fundal a butonului și schimbarea culorii textului din interiorul butonului. 

```js
const button = document.getElementsByTagName('div')[0];
button.addEventListener('mouseover', function(e) {
    const style = e.currentTarget;
    const {
        backgroundColor
    } = style;
    if (backgroundColor === 'white') {
        targetStyles.backgroundColor = '#234465';
        targetStyles.color = 'white';
    } else {
        targetStyles.backgroundColor = 'white';
        targetStyles.color = '#234465';
    }
});
```

## Atașarea unui Eveniment Input

În acest exemplu, folosim tipul "**input**" pentru a demonstra cum putem activa un buton când scriem ceva în câmpul de intrare. 

Inițial, butonul este **dezactivat** în HTML. 

De îndată ce scriem ceva în câmpul de intrare, butonul va fi **activat** datorită acestei linii de cod din funcția handler: `button.setAttribute('disabled', 'false');`.

```js
const inputField = document.getElementsByTagName('input')[0];
const button = document.getElementsByTagName('button')[0];
inputField.addEventListener('input', function () {
    button.setAttribute('disabled', 'false');
});
```

[/slide]

[slide hideTitle]

# Ștergerea Evenimentelor

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-25-remove-events-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Aici avem o implementare mai profundă a metodelor `.addEventListener()` și `.removeEventListener()`.

Primul ascultător de evenimente (`focus`, `focusEvent`) va aduce în prim plan câmpul de intrare al parolei, dacă apăsăm pe acest câmp. 

Al doilea ascultător de evenimente `blur`, (event) va elimina **focalizarea** dacă dăm click pe un alt câmp input.

La final, al treilea ascultător de evenimente atașat butonului va elimina primul ascultător de evenimente, atunci când apăsăm pe buton.

În acest moment, pierdem efectul **de focalizare**.


```js
const password = document.querySelector('input[type="password"]');
const button = document.querySelector('button');
password.addEventListener('focus', focusEvent);
function focusEvent (event){
    event.target.style.background = '#234465';
}
password.addEventListener('blur', (event) => {
    event.target.style.background = '';
});
button.addEventListener('click', () => {
    password.removeEventListener('focus', focusEvent);
});
```

[/slide]

[slide hideTitle]

# Evenimente Multiple

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-26-multiple-events-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Putem adăuga mai multe evenimente aceluiași element, fără a suprascrie evenimentele existente. 

```js
element.addEventListener('click', function);
element.addEventListener('click', myFunction);
element.addEventListener('mouseover', mySecondFunction);
element.addEventListener('mouseout', myThirdFunction);
```

[/slide]

[slide hideTitle]

# SetInterval() şi ClearInterval()

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-27-setinterval-clearinterval-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

În JavaScript, putem **porni** sau **opri** cronometrul.

Metoda `setInterval()` apelează o funcție sau evaluează o expresie la intervale de timp specifice (în milisecunde).

`setInterval()` va continua să apeleze funcția până când `clearInterval()` este apelată sau fereastra este închisă. 

În exemplul de mai jos, intervalul este 1000 millisecunde sau 1 secundă.

Metoda `clearInterval()` șterge cronometrul setat cu metoda `setInterval()`.


```js
let intervalID = setInterval(
    function() {
        console.log('1 sec. passed');
    }, 1000
);
```

Folosiți metoda `.clearInterval()` pentru a șterge un cronometru existent. 

```js
clearInterval(intervalID);
```

[/slide]

[slide hideTitle]
# Problemă cu Soluție: Add Delete

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-28-29-solution-two-add-delete-items-NEW-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="Add Delete" taskId="Js-Advanced-Dom-Manipulations-Add-Delete" executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]
```
function addItem(){
  // Scrieți codul dvs. aici
}
```
[/code-editor]
[task-description]
# Descriere

**Aici este un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/JS-Advanced-DOM-Manipulations-Lab-02.Add-Delete.zip) **pentru această sarcină.**

Extindeți problema anterioară pentru a afișa un link `[Delete]` după fiecare element din listă. 

Dând click, vom șterge elementul, fără să primim vreo confirmare. 

## Exemplu
[image assetsSrc="Dom-Manipulation(4).gif" /]

[/task-description]
[code-io /]
[tests]
[test open]
[input]
document.body.innerHTML = \`
\<h1\>List of Items\</h1\>
\<ul id="items"\>
\</ul\>
\<input type="text" id="newText" /\>
\<input type="button" value="Add"  onclick="addItem()"\>
\`;

document.getElementById('newText').value = 'First';
result();

document.getElementById('newText').value = 'Second';
result();

let items = \$('\#items li');

// Verify items where added with delete links
expect(items.get(0).innerHTML).to.contains('First', "Element wasn't added.");
expect(items.get(0).innerHTML).to.contains('\<a href="\#"\>\[Delete\]\</a\>', "Delete link wasn't added.");
expect(items.get(1).innerHTML).to.contains('Second', "Element wasn't added.");
expect(items.get(1).innerHTML).to.contains('\<a href="\#"\>\[Delete\]\</a\>', "Delete link wasn't added.");

// Setup event
var clickEvent = document.createEvent('MouseEvents');
clickEvent.initEvent('click', true, true);
items.eq(1).find('a').get(0).dispatchEvent(clickEvent);

expect(\$('\#items li').length).to.equal(1, "Correct element wasn't deleted.");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = \`
\<h1\>List of Items\</h1\>
\<ul id="items"\>
\</ul\>
\<input type="text" id="newText" /\>
\<input type="button" value="Add"  onclick="addItem()"\>
\`;

document.getElementById('newText').value = 'First';
result();

document.getElementById('newText').value = 'Second';
result();

let items = \$('\#items li');

// Verify items where added with delete links
expect(items.get(0).innerHTML).to.contains('First', "Element wasn't added.");
expect(items.get(0).innerHTML).to.contains('\<a href="\#"\>\[Delete\]\</a\>', "Delete link wasn't added.");
expect(items.get(1).innerHTML).to.contains('Second', "Element wasn't added.");
expect(items.get(1).innerHTML).to.contains('\<a href="\#"\>\[Delete\]\</a\>', "Delete link wasn't added.");

// Setup event
var clickEvent = document.createEvent('MouseEvents');
clickEvent.initEvent('click', true, true);
items.eq(1).find('a').get(0).dispatchEvent(clickEvent);

expect(\$('\#items li').length).to.equal(1, "Correct element wasn't deleted.");
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]

# Delegarea Evenimentelor 

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-32-33-34-event-delegation-pros-and-cons-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Capturarea și bubbling-ul ne permit să implementăm un tipar de gestionare a evenimentelor numit **delegarea evenimentelor**.

Dacă avem o mulțime de elemente care sunt gestionate în același fel, atunci, în loc să asignăm un handler pentru fiecare dintre ele, putem pune un singur handler pentru predecesorul lor comun. 

În handler, folosim `event.target` pentru a vedea unde a avut loc, de fapt, evenimentul și astfel îl putem gestiona. 

În acest exemplu, adăugăm un ascultător pentru părinte, acesta fiind elementul `<ul>`.

Apoi, în instrucțiunea "if", adăugăm o condiție, astfel încât dacă dăm click pe elementul `<li>`, metoda `console.log()` va afișa un mesaj care ne spune exact pe ce element am dat click.


```js
<ul id="parent-list">
    <li id="post-1">Item 1</li>
    <li id="post-2">Item 2</li>
</ul>
```

```js
document.getElementById('parent-list')
    .addEventListener('click', function(event) {
        if (event.target && event.target.nodeName == 'LI') {
            console.log(
                'List item', event.target.id,
                ' was clicked!');
        }
    });
```

## Avantaje și dezavantaje 

**Avantaje:**

- Cod de calitate

- Economie de memorie

- Performanță mai bună

- Mai puține manipulări DOM

**Dezavantaje:**

- Nu toate evenimentele trec prin procesul de bubbling

- Copilul oprește propagarea 

- Poate încărca mult CPU-ul


[/slide]

