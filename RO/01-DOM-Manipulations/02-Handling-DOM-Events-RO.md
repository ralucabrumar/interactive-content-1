# Gestioneare Evenimentelor DOM

[slide hideTitle]

# Propagarea Evenimentelor 

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-11-12-dom-events-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Propagarea evenimentelor este un mod de a descrie "**stiva**" de evenimente care sunt declanșate în browser.  

În browser vom avea 3 faze ale propagării evenimentelor: 

- **Capturing**: evenimentul se deplasează spre element

- **Target**: evenimentul ajunge la elementul țintă 

- **Bubbling**: evenimentul pornește dinspre element 


Atunci când dăm click pe elementul `<A>`, evenimentul merge mai întâi în lanț către element, această fiind numită **fază de capturare**, apoi ajunge la țintă și declanșează faza numită **țintă**, iar apoi merge în sus, ceea ce se numește **bubbling**, apelând handleri în drumul său. 

Pentru a prinde un eveniment în **faza de capturare**, trebuie să setăm opțiunea de captură a handler-ului la **true**.

În timpul acestei faze, doar capturatorii găsiți pe drumul dinspre fereastră spre părintele evenimentului țintă sunt apelați. 

Dacă acest parametru este omis, valoarea sa inițială este **false**, iar ascultătorul nu este un **capturator**.


```js
el.addEventListener('click', listener, true);
```

Când un eveniment are loc pentru un element, handler-ul este rulat mai întâi pentru acesta, apoi pentru părintele acestuia, iar apoi pentru toate, în drumul său către alți predecesori. Acest lucru se numește **bubbling**.

În acest exemplu, handler-ul este asignat elementului `<div>`, dar pornește și dacă dăm click pe o etichetă imbricată cum ar fi `<em>` sau `<code>`.

```js
<div onclick="alert('The handler!')">
   <em>Click on <code>ME</code>, or click on the main <code>DIV</code> runs.</em>
</div>
```

Un eveniment în faza de bubbling urcă spre obiectul "**document**", iar unele evenimente ating chiar "**window**", apelând toți handlerii de pe traseu. 

Putem opri faza de **bubbling** folosind o metodă numită `event.stopPropagation()`.

În acest exemplu, `body.onclick` nu va funcționa dacă dăm click pe `<button>`.

```js
<body onclick="alert(`the bubbling doesn't reach here`)">
   <button onclick="event.stopPropagation()">Click me</button>
</body>
```

[/slide]

[slide hideTitle]

# Tipuri de Evenimente în DOM API

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-13-event-types-in-dom-api-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Iată câteva tipuri de evenimente folosite în DOM.

| **Mouse events** | **Touch events** | **DOM/UI events** | **Keyboard events** | **Focus events** | **Form events** |
| :---: | :---: | :---: | :---: | :---: | :---: |
| click | touchstart | load | keydown | focus (got focus) | input |
| mouseover | touchend | unload | keypress | blur (lost focus) | change |
| mouseout | touchmove | resize | keyup |  | submit |
| mousedown | touchcancel | dragstart / drop |  |  | reset |
| mouseup |  |  |  |  |  |

[/slide]

[slide hideTitle]

# Proprietățile și Metodele Obiectelor de tip Eveniment

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-14-15-event-object-properties-and-methods-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Să examinăm Obiectul de tip Eveniment. 

Funcția **de gestionare a evenintului (handler)** poate fi o **funcție anonimă** sau o **declarare de funcție**.

Argumentul nostru `e`, care este transmis funcției, este **referința noastră pentru obiectul de tip eveniment**.

Obiectul de tip eveniment are mai multe **proprietăți** și **metode**. 

## Proprietăți

Câteva proprietăți sunt: 

- **target**

- **timeStamp** 

- **isTrusted**

- **ClientX / ClientY**

```js
addBtn.addEventListener('click', function(e){
    console.log(e.target);
})
```

Proprietatea **target** a evenimentului returnează elementul care a declanșat evenimentul.

Proprietatea **timeStamp** a evenimentului este read-only. Aceasta returnează **timpul în milisecunde** de la începutul vieții documentului curent până la momentul când a fost creat evenimentul. 

Proprietatea **isTrusted** returnează o valoare booleană care indică dacă evenimentul este **trusted** sau nu. 

Proprietatea **clientX** returnează o coordonată orizontală (în acord cu domeniul clientului) a pointer-ului mouse-ului, atunci când un eveniment de tip este declanșat. 

Proprietatea **clientY** returnează coordonata verticală. 

## Metode

Câteva metode sunt: 

- `preventDefault()`

- `stopPropagation()`

- `stopImmediatePropagation()`

Metoda `preventDefault()` îi spune utilizatorului că dacă evenimentul nu este gestionat explicit, acțiunea sa implicită nu trebuie să aibă loc așa cum s-ar fi întâmplat în mod normal. 

Metoda `stopPropagation()` previne propagarea mai departe a unui eveniment curent în fazele de capturare și bubbling. 

Metoda `stopImmediatePropagation()` previne apelarea altor ascultători ai aceluiași eveniment. 

[/slide]

[slide hideTitle]
# Problemă cu Soluție: List Of Items

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-16-17-solution-list-of-items-html-NEW-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="List Of Items" taskId="Js-Advanced-Dom-Manipulations-lab-List-Of-Items" executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]

```
function addItem(){
  // Scrieți codul dvs. aici
}
```
[/code-editor]
[task-description]
# Descriere

**Aici este un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/JS-Advanced-DOM-Manipulations-Lab-01.List-Of-Items.zip) **pentru această sarcină.**

Creați o funcție care **citește** un text din interiorul unui câmp de intrare și **adaugă** textul specificat unei liste din interiorul unei pagini HTML.

## Exemplu
[image assetsSrc="Dom-Manipulation(3).png" /]

[/task-description]
[code-io /]
[tests]
[test open]
[input]
document.body.innerHTML = \`
\<h1\>List of Items\</h1\>
    \<main\>
        \<ul id="items"\>
            \<li\>First\</li\>
            \<li\>Second\</li\>
        \</ul\>
        \<input type="text" id="newItemText" /\>
        \<input type="button" value="Add""\>
    \</main\>
\`;

document.getElementById('newItemText').value = 'new mode';

result();

let liElements = document.getElementsByTagName('li');

assert.equal(liElements.length, 3, 'List items count is invalid');
assert.equal(liElements\[2\].textContent, 'new mode', 'The new list item contains something different');
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = \`
\<h1\>List of Items\</h1\>
    \<main\>
        \<ul id="items"\>
            \<li\>First\</li\>
            \<li\>Second\</li\>
        \</ul\>
        \<input type="text" id="newItemText" /\>
        \<input type="button" value="Add" onclick="addItem()"\>
    \</main\>
\`;

\\$('\#newItemText').val('new mode');
result();

\\$('\#newItemText').val('Fourth Grade');
result();

let liElements = document.getElementsByTagName('li');

assert.equal(liElements.length, 4, 'List items count is invalid');
assert.equal(liElements\[2\].textContent, 'new mode', 'The new list item contains something different');
assert.equal(liElements\[3\].textContent, 'Fourth Grade', 'The new list item contains something different');
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]

[/slide]
