# Teme Pentru Acasă


[slide hideTitle]
# Problemă: Subtraction

[code-task title="Subtraction" taskId="js-advanced-DOM-Subtraction" executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]

```
function subtraction(){
  // Scrieți codul dvs. aici
}
```
[/code-editor]
[task-description]

# Descriere

**Aveți un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/01-Subtraction.zip) **pentru această sarcină**.

O pagină HTML conține **două câmpuri de text** cu **id-urile** "**firstNumber**" și "**secondNumber**". 

Scrieți o funcție pentru a **extrage** valorile din aceste câmpuri de text și afișați rezultatul într-un `<div>` numit "**result**".

## Cod HTML și JavaScript

Implementați descrierea de mai sus pentru a furniza următoarele funcționalități:

- Funcția voastră trebuie să ia valorile "**firstNumber**" și "**secondNumber**", **să le transforme** în numere, **să scadă** al doilea număr din primul și apoi să adauge rezultatul la `<div>` cu `id="result"`

- Funcția voastră trebuie să poată funcționa cu **orice 2 numere** din intrări, nu doar cu cele date în exemplu

## Exemplu

[image assetsSrc="JS-Advanced-DOM-Homework-1.png" /]

[hints]
[hint]
Vedem că **căsuțele pentru text** și `div` au atribute `id`:

```js
<div id="wrapper">
   <input type="text" id="firstNumber" 
      value="13.33" disabled>
   <input type="text" id="secondNumber" 
      value="22.18" disabled>
   <div id="result"></div>
</div>
```

Putem lua numerele direct din câmpul de intrare utilizând funcția `getElementById()`.
[/hint] 
[hint]
Dupa ce am luat elementele din DOM, este timpul să efectuăm munca propriu-zisă.

Obținem valorile celor două **căsuțe de text**. 

```js
let firstNumber = document
  .getElementById('firstNumber').value;

let secondNumber = document
  .getElementById('secondNumber').value;
```

Valoarea uneia, așa cum ne-am așteptat, este **text**.

Pentru a obține un **număr**, trebuie să folosim o funcție pentru a le **transforma**.
[/hint] 
[hint]
Tot ce a mai rămas acum de făcut este să adăugăm rezultatul la `div`.

Folosim aceeași funcție pentru a obține elementul **result** după `id` și pentru a-i schimba **conținutul de text** la rezultatul **scpderii**.

```js
function subtract() {
  let firstNumber = Number(document
    .getElementById('firstNumber').value);
  let secondNumber = Number(document
    .getElementById('secondNumber').value);

  document.getElementById('result')
    .textcontent = firstNumber - secondNumber;
}
```
[/hint] 
[/hints] 


## Trimitere

Trimiteți numai funcția `subtract()`.


[/task-description]
[code-io /]
[tests]
[test open]
[input]
document.body.innerHTML = '\<div id="wrapper"\>\<input type="text" id="firstNumber" value="13.33" disabled\>\<input type="text" id="secondNumber" value="22.18" disabled\>\<div id="result"\>\</div\>\</div\>';

result();

var \\$div = \\$('\#result');

expect(\\$div\[0\].textContent).to.equal("-8.85");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = '\<div id="wrapper"\>\<input type="text" id="firstNumber" value="0" disabled\>\<input type="text" id="secondNumber" value="0" disabled\>\<div id="result"\>\</div\>\</div\>';

result();

var \\$div = \\$('\#result');

expect(\\$div\[0\].textContent).to.equal("0");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = '\<div id="wrapper"\>\<input type="text" id="firstNumber" value="15" disabled\>\<input type="text" id="secondNumber" value="2" disabled\>\<div id="result"\>\</div\>\</div\>';

result();

var \\$div = \\$('\#result');

expect(\\$div\[0\].textContent).to.equal("13");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = '\<div id="wrapper"\>\<input type="text" id="firstNumber" value="0" disabled\>\<input type="text" id="secondNumber" value="-13.40" disabled\>\<div id="result"\>\</div\>\</div\>';

result();

var \\$div = \\$('\#result');

expect(\\$div\[0\].textContent).to.equal("13.4");
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]

# Problemă: Fill Dropdown

[code-task title="Fill Dropdown" taskId="js-advanced-DOM-Fill-Dropdown"  executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]

```
function fillDropdown(){
  // Scrieți codul dvs. aici
}
```

[/code-editor]
[task-description]

# Descriere

**Aveți un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/02-Fill-Dropdown.zip) **pentru această sarcină**.

Sarcina voastră este să luați valorile din câmpurile **de intrare**, cu **id-urile** "**newItemText**" și "**newItemValue**.

Apoi trebuie să **creați** și să **adăugați** un `<option>` la `<select>`, cu **id-ul** "**menu**".

## Exemple

[image assetsSrc="JS-Advanced-DOM-Homework-5.gif" /]

[hints]
[hint]
**Funcția** voastră trebuie să ia **valorile** `newItemText` și `newItemValue`.
[/hint] 
[hint]
După aceea, trebuie să **creați** un nou element `option` și să setați `textContent` și **valoarea** sa la cele nou recuperate.
[/hint] 
[hint]
După ce ați făcut toate acestea, trebuie **să adaugați** elementul `<option>` nou drept **copil** pentru elementul `<select>` cu id-ul "**menu**".
[/hint] 
[hint]
În cele din urmă, trebuie să **ștergeți** valoarea celor două câmpuri **de intrare** - `input`.
[/hint] 
[/hints] 

[/task-description]
[code-io /]
[tests]
[test]
[input]
document.body.innerHTML = \`
    \<h1\>Dropdown Menu\</h1\>
    \<article\>
        \<div\>
            \<select id="menu"\>\</select\>
        \</div\>
        \<label for="newItemText"\>
            Text:
        \</label\>
        \<input type="text" id="newItemText" /\>
        \<label for="newItemValue"\>
            Value:
        \</label\>
        \<input type="text" id="newItemValue" /\>
        \<input type="button" value="Add" onclick="addItem()"\>
    \</article\>
\`;

\$('\#newItemText').val('new node');
\$('\#newItemValue').val('val1');

result();

let item = \$('\#menu').find('option');
expect(item.text()).to.contains('new node', "Item text wasn't added");
expect(item.val()).to.contains('val1', "Item value wasn't added");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = \`
    \<h1\>Dropdown Menu\</h1\>
    \<article\>
        \<div\>
            \<select id="menu"\>\</select\>
        \</div\>
        \<label for="newItemText"\>
            Text:
        \</label\>
        \<input type="text" id="newItemText" /\>
        \<label for="newItemValue"\>
            Value:
        \</label\>
        \<input type="text" id="newItemValue" /\>
        \<input type="button" value="Add" onclick="addItem()"\>
    \</article\>
\`;

\$('\#newItemText').val('Some Text');
\$('\#newItemValue').val('myValue');

result();

let item = \$('\#menu').find('option');
expect(item.text()).to.contains('Some Text', "Item text wasn't added");
expect(item.val()).to.contains('myValue', "Item value wasn't added");
expect(\$('\#newItemText').val()).to.equal('', "Text input was not cleared");
expect(\$('\#newItemValue').val()).to.equal('', "Value input was not cleared");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = \`
    \<h1\>Dropdown Menu\</h1\>
    \<article\>
        \<div\>
            \<select id="menu"\>\</select\>
        \</div\>
        \<label for="newItemText"\>
            Text:
        \</label\>
        \<input type="text" id="newItemText" /\>
        \<label for="newItemValue"\>
            Value:
        \</label\>
        \<input type="text" id="newItemValue" /\>
        \<input type="button" value="Add" onclick="addItem()"\>
    \</article\>
\`;

\$('\#newItemText').val('Option 1');
\$('\#newItemValue').val('value1');
result();
\$('\#newItemText').val('Option 2');
\$('\#newItemValue').val('value2');
result();

let item = \$('\#menu').find('option');
expect(item\[0\].textContent).to.contains('Option 1', "Item wasn't added");
expect(item\[0\].value).to.contains('value1', "Item wasn't added");
expect(item\[1\].textContent).to.contains('Option 2', "Item wasn't added");
expect(item\[1\].value).to.contains('value2', "Item wasn't added");
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]

# Problemă: Accordion

[code-task title="Accordion" taskId="js-advanced-DOM-Accordion" executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]

```
function accordion(){
  // Scrieți codul dvs. aici
}
```

[/code-editor]
[task-description]

# Descriere

**Aveți un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/03-Accordion.zip) **pentru această sarcină.**

Veți primi un fișier **HTML**.

Sarcina voastră este de a afișa **mai multe/mai puține** informații apăsând butonul `[ADD]` (nu este un buton real, ci un **span** care are atașat evenimentul `onclick`).

Când este apăsat butonul `[More]`, acesta **dezvăluie** conținutul unui `div` **ascuns**, iar textul butonului este **schimbat** în `[Less]`.

Când același link este apasat **din nou** (acum fiind **Less**), **ascundeți** `div-ul` și **schimbați** textul linkului în **More**.

Acțiunea linkului ar trebui să fie **toggleable** (ar trebui să puteți apăsa butonul de un număr **infinit** de ori).

## Exemplu

[image assetsSrc="JS-Advanced-DOM-Homework-6.gif" /]

[hints]
[hint]
Pentru a **schimba** conținutul textului unui buton, puteți utiliza `getElementsByClassName`.

Însă, aceasta returnează o **colecție** și avem nevoie doar de **un** element din aceasta, așa este mai corect este să folosiți `getElementsByClassName('button')[0]`.

Aceasta va **returna** elementul `span` necesar.
[/hint] 
[hint]
După aceea, trebuie să schimbăm **stilul de afișare** al `div-ului` cu `id-ul` "**extra**".

Dacă stilul de afișare este "**none**", ar trebui să-l **schimbăm** în "**block**" și **opusul**.
[/hint] 
[hint]
Împreună cu toate acestea, trebuie **să schimbăm** conținutul textului **butonului** la `[Less]`/`[More]`.
[/hint] 
[/hints]

[/task-description]
[code-io /]
[tests]
[test]
[input]
document.body.innerHTML = `
<div id="accordion">
        <div class="head">DOM Manipulations Exercise <span class="button">More</span></div>
        <div id="extra" style="display: none">
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
                dolore
                magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
                commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu
                fugiat
                nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt
                mollit
                anim id est laborum.</p>
        </div>
    </div>
`;

result(); // Show

let extra = document.getElementById("extra");
let button = document.getElementsByClassName("button")[0];

button.click();

expect(extra.style.display).to.equal('block', "Text was not made visible.");
expect(button.textContent).to.contains('Less', "Button text wasn't changed.");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = \`
\<div id="accordion"\>
        \<div class="head"\>DOM Manipulations Exercise \<span class="button"\>More\</span\>\</div\>
        \<div id="extra" style="display: none"\>
            \<p\>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
                dolore
                magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
                commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu
                fugiat
                nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt
                mollit
                anim id est laborum.\</p\>
        \</div\>
    \</div\>
\`;

let extra = document.getElementById("extra");
let button = document.getElementsByClassName("button")\[0\];

result(); // Show
expect(extra.style.display).to.equal('block', "Text was not made visible.");
expect(button.textContent).to.contains('Less', "Button text wasn't changed.");

result(); // Hide
expect(extra.style.display).to.equal('none', "Text was not hidden.");
expect(button.textContent).to.contains('More', "Button text wasn't changed.");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = \`
\<div id="accordion"\>
        \<div class="head"\>DOM Manipulations Exercise \<span class="button"\>More\</span\>\</div\>
        \<div id="extra" style="display: none"\>
            \<p\>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
                dolore
                magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
                commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu
                fugiat
                nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt
                mollit
                anim id est laborum.\</p\>
        \</div\>
    \</div\>
\`;

let extra = document.getElementById("extra");
let button = document.getElementsByClassName("button")\[0\];

result(); // Show
expect(extra.style.display).to.equal('block', "Text was not made visible.");
expect(button.textContent).to.contains('Less', "Button text wasn't changed.");

result(); // Hide
expect(extra.style.display).to.equal('none', "Text was not hidden.");
expect(button.textContent).to.contains('More', "Button text wasn't changed.");

result(); // Show
expect(extra.style.display).to.equal('block', "Text was not made visible.");
expect(button.textContent).to.contains('Less', "Button text wasn't changed.");

result(); // Hide
expect(extra.style.display).to.equal('none', "Text was not hidden.");
expect(button.textContent).to.contains('More', "Button text wasn't changed.");
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]


[slide hideTitle]

# Problemă: Order the Names

[code-task title="Order the names" taskId="js-advanced-DOM-Order-The-Names" executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]

```
function orderTheNames(){
  // Scrieți codul dvs. aici
}
```

[/code-editor]
[task-description]

# Descriere

**Aveți un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/04-Order-the-Names.zip) **pentru această sarcină.**

Scrieți o funcție **care ordonează numele în ordine alfabetică**.

[image assetsSrc="JS-Advanced-DOM-Homework-7.jpg" /]

Veți primi un **nume al unui student ca date de intrare**.

Când butonul **"Register"** este **apăsat**, trebuie să adăugați numele studentului dat în baza de date SoftUni, păstrând **ordinea alfabetică**.

De exemplu, dacă îl înregistrăm pe **David**, numele său ar trebui să apară în coloana **D**.

[image assetsSrc="JS-Advanced-DOM-Homework-8.jpg" /]

[image assetsSrc="JS-Advanced-DOM-Homework-9.jpg" /]

Dacă **primiți mai multe nume cu aceeași literă de pornire**, trebuie să **alăturați toate numele** printr-o virgulă și un spațiu **(", ")**.

[image assetsSrc="JS-Advanced-DOM-Homework-10.jpg" /]

[hints]
[hint]
Atașați un ascultător pentru evenimentul `click` la butonul `ADD`:

```js
const addButton = document
  .getElementsByTagName('button')[0];

addButton
  .addEventListener('click', addName);
```
[/hint] 
[hint]
Creați un handler pentru evenimentul `addName` și obțineți **valoarea** câmpului de intrare **name**:

```js
function addName() { 
    const nameInput = document
      .getElementsByTagName('input')[0];

    let name = nameInput.value;
}
```
[/hint] 
[hint]
Asigurați-vă că prima literă va fi o **majusculă**, iar celelalte caractere litere mici:

```js
let firstLetter = name[0].toUpperCase();
let fixedName = firstLetter 
  + name.substring(1).toLowerCase();

let charIndex = 
  Number(firstLetter.charCodeAt('0') - 65);
```

Apoi, folosiți metoda `charCodeAt` pentru a obține valoarea **ASCII** a primului caracter.
[/hint] 
[hint]
Obțineți toate elementele **list item** folosind `getElementsByTagName`.

În funcție de `innerHTML` al list item-ului corespunzător, puteți:

- **Să adăugați** noul nume, precedat de **o virgulă și un spațiu** (**", "**)
- Dacă se întâmplă să fie primul pentru litera dată, **adăugați**-l pur și simplu

```js
const liElements = 
  document.getElementsByTagName('li');

if (liElements[charIndex].innerHTML !== '') {

  liElements[charIndex]
    .innerHTML += ', ' + fixedName;
}
else {
  liElements[charIndex]
    .innerHTML = fixedName;
}

nameInput.value = '';
```

Nu uitați să ștergeți **valoarea casetei de intrare** după aceea.

[/hint] 
[/hints]

[/task-description]
[code-io /]
[tests]
[test open]
[input]
document.body.innerHTML = `
\<div id="container"\>

        \<main id="main"\>
            \<div id="exercise"\>
                \<article\>
                    \<input type="text" /\>
                    \<button type="button"\>ADD\</button\>
                \</article\>

                \<div\>
                    \<h1\>SoftUni Database\</h1\>
                    \<ol type="A"\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>Nixon\</li\>
                        \<li\>\</li\>
                        \<li\>Peterson\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                    \</ol\>
                \</div\>
            \</div\>
        \</main\>

    \</div\>
`;

result();

\\$("\#exercise input").val("Pepe");

\\$("button").trigger("click");

let test = \\$("ol")\[0\].children\[15\].textContent;
expect(test).to.equal("Peterson, Pepe");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
\<div id="container"\>

        \<main id="main"\>
            \<div id="exercise"\>
                \<article\>
                    \<input type="text" /\>
                    \<button type="button"\>ADD\</button\>
                \</article\>

                \<div\>
                    \<h1\>SoftUni Database\</h1\>
                    \<ol type="A"\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>Nixon\</li\>
                        \<li\>\</li\>
                        \<li\>Peterson\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                    \</ol\>
                \</div\>
            \</div\>
        \</main\>

    \</div\>
`;

result();

\\$("\#exercise input").val("Nickson");

\\$("button").trigger("click");

let test = \\$("ol")\[0\].children\[13\].textContent;
expect(test).to.equal("Nixon, Nickson");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
\<div id="container"\>

        \<main id="main"\>
            \<div id="exercise"\>
                \<article\>
                    \<input type="text" /\>
                    \<button type="button"\>ADD\</button\>
                \</article\>

                \<div\>
                    \<h1\>SoftUni Database\</h1\>
                    \<ol type="A"\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>Nixon\</li\>
                        \<li\>\</li\>
                        \<li\>Peterson\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                    \</ol\>
                \</div\>
            \</div\>
        \</main\>

    \</div\>
`;

result();

\\$("\#exercise input").val("AARON");

\\$("button").trigger("click");

let test = \\$("ol")\[0\].children\[0\].textContent;
expect(test).to.equal("Aaron");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
\<div id="container"\>

        \<main id="main"\>
            \<div id="exercise"\>
                \<article\>
                    \<input type="text" /\>
                    \<button type="button"\>ADD\</button\>
                \</article\>

                \<div\>
                    \<h1\>SoftUni Database\</h1\>
                    \<ol type="A"\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>Nixon\</li\>
                        \<li\>\</li\>
                        \<li\>Peterson\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                    \</ol\>
                \</div\>
            \</div\>
        \</main\>

    \</div\>
`;

result();

\\$("\#exercise input").val("AARON");
\\$("button").trigger("click");

\\$("\#exercise input").val("angus");
\\$("button").trigger("click");

let test = \\$("ol")\[0\].children\[0\].textContent;
expect(test).to.equal("Aaron, Angus");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
\<div id="container"\>

        \<main id="main"\>
            \<div id="exercise"\>
                \<article\>
                    \<input type="text" /\>
                    \<button type="button"\>ADD\</button\>
                \</article\>

                \<div\>
                    \<h1\>SoftUni Database\</h1\>
                    \<ol type="A"\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>Nixon\</li\>
                        \<li\>\</li\>
                        \<li\>Peterson\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                    \</ol\>
                \</div\>
            \</div\>
        \</main\>

    \</div\>
`;

result();

\\$("\#exercise input").val("Ziliph");
\\$("button").trigger("click");

\\$("\#exercise input").val("Yamamoto");
\\$("button").trigger("click");

\\$("\#exercise input").val("YANA");
\\$("button").trigger("click");

\\$("\#exercise input").val("Zoro");
\\$("button").trigger("click");

let test = \\$("ol")\[0\].children\[25\].textContent;
expect(test).to.equal("Ziliph, Zoro");

let test2 = \\$("ol")\[0\].children\[24\].textContent;
expect(test2).to.equal("Yamamoto, Yana");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
\<div id="container"\>

        \<main id="main"\>
            \<div id="exercise"\>
                \<article\>
                    \<input type="text" /\>
                    \<button type="button"\>ADD\</button\>
                \</article\>

                \<div\>
                    \<h1\>SoftUni Database\</h1\>
                    \<ol type="A"\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>Nixon\</li\>
                        \<li\>\</li\>
                        \<li\>Peterson\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                        \<li\>\</li\>
                    \</ol\>
                \</div\>
            \</div\>
        \</main\>

    \</div\>
`;

result();

\\$("\#exercise input").val("FRANK");
\\$("button").trigger("click");

\\$("\#exercise input").val("Furious");
\\$("button").trigger("click");

\\$("\#exercise input").val("fury");
\\$("button").trigger("click");

\\$("\#exercise input").val("Farmerson");
\\$("button").trigger("click");

let test = \\$("ol")\[0\].children\[5\].textContent;
expect(test).to.equal("Frank, Furious, Fury, Farmerson");
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]

# Problemă: Chat Room

[code-task title="Chat Room" taskId="js-advanced-DOM-Chat-Room" executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]

```
function chatRoom(){
  // Scrieți codul dvs. aici
}
```

[/code-editor]
[task-description]

# Descriere

**Aveți un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/05-Chat-Room.zip) **pentru această sarcină**.

Scrieți o **funcție** pentru a crea funcționalitatea de **chat room**.

[image assetsSrc="JS-Advanced-DOM-Homework-11.jpg" /]

**Notă:** Nu uitați să **adăugați un ascultător de evenimente** la **butonul de trimitere!**

**Noul** `div` element cu clasa **"message my-message"** trebuie să conțină **mesajul curent** care urmează să fie trimis.

`div-ul` **curent** trebuie să fie adăugat la `div-ul` cu `id="chat_messages"`.

**Intrarea trebuie să fie ștearsă la fiecare clic al butonului de trimitere**.

[image assetsSrc="JS-Advanced-DOM-Homework-12.jpg" /]

[image assetsSrc="JS-Advanced-DOM-Homework-13.jpg" /]

[hints]
[hint]
Folosiți metoda `classlist.add()` pentru a adăuga **clasele** necesare la noul **div**:

```js
let myMessage = document.createElement("div");
myMessage.classList.add("message", "my-message");
```
[/hint] 
[hint]
Setați `textContent` al noului **div** la valoarea elementului `#chat_input`:

```js
myMessage.textContent = chatInput.value;
```
[/hint] 
[hint]
Adăugați **div-ul vostru** la div-ul `#chat_messages` folosind `appendChild()`:

```js
chatMessages.appendChild(myMessage);
```
[/hint] 
[/hints]

[/task-description]
[code-io /]
[tests]
[test open]
[input]
document.body.innerHTML = `
\<div class="flexbox"\>
        \<div class="chat-box"\>
            \<div class="chat-box-header"\>
                \<h3\>Chat Room\<br /\>\<small\>Last active: 2 min ago\</small\>\</h3\>
            \</div\>
            \<div id="chat_box_body" class="chat-box-body"\>
                \<div id="chat_messages"\>
                    \<div class="profile other-profile"\>
                        \<img src="https://images.unsplash.com/photo-1537396123722-b93d0acd8848?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=efc6e85c24d3cfdd15cd36cb8a2471ed"
                            width="30" height="30" /\>
                        \<span\>Other profile\</span\>
                    \</div\>
                    \<div class="message other-message"\>
                        Sorry, I am busy right now, Can I write you back later?
                    \</div\>
                    \<div class="profile my-profile"\>
                        \<span\>My profile\</span\>
                        \<img src="https://images.unsplash.com/photo-1534135954997-e58fbd6dbbfc?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=02d536c38d9cfeb4f35f17fdfaa36619"
                            width="30" height="30" /\>
                    \</div\>

                    \<div class="message my-message"\>
                        Hi!
                    \</div\>
                \</div\>
            \</div\>
            \<div id="typing"\>
                \<div\>\<span\>\</span\> \<span\>\</span\> \<span\>\</span\> \<span class="n"\>Someone\</span\> is typing...\</div\>
            \</div\>
            \<div class="chat-box-footer"\>
                \<textarea id="chat_input" placeholder="Enter your message here..."\>\</textarea\>
                \<button id="send"\>
                    \<svg style="width:24px;height:24px" viewBox="0 0 24 24"\>
                        \<path fill="\#006ae3" d="M2,21L23,12L2,3V10L17,12L2,14V21Z" /\>
                    \</svg\>
                \</button\>
            \</div\>
        \</div\>
    \</div\>
`;

result();

document.getElementById('chat_input').value = "Are you there?";
document.getElementById('send').click();

let messages = document.getElementById('chat_messages').children;

assert.equal(messages.length, 5, 'The messages count is invalid');
assert.equal(messages\[4\].textContent, 'Are you there?', 'The expected message is different.');
assert.equal(messages\[4\].tagName, 'DIV', 'The expected message element should be DIV');
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// Children length, textContent, tagName
document.body.innerHTML = `
\<div class="flexbox"\>
        \<div class="chat-box"\>
            \<div class="chat-box-header"\>
                \<h3\>Chat Room\<br /\>\<small\>Last active: 2 min ago\</small\>\</h3\>
            \</div\>
            \<div id="chat_box_body" class="chat-box-body"\>
                \<div id="chat_messages"\>
                    \<div class="profile other-profile"\>
                        \<img src="https://images.unsplash.com/photo-1537396123722-b93d0acd8848?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=efc6e85c24d3cfdd15cd36cb8a2471ed"
                            width="30" height="30" /\>
                        \<span\>Other profile\</span\>
                    \</div\>
                    \<div class="message other-message"\>
                        Sorry, I am busy right now, Can I write you back later?
                    \</div\>
                    \<div class="profile my-profile"\>
                        \<span\>My profile\</span\>
                        \<img src="https://images.unsplash.com/photo-1534135954997-e58fbd6dbbfc?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=02d536c38d9cfeb4f35f17fdfaa36619"
                            width="30" height="30" /\>
                    \</div\>

                    \<div class="message my-message"\>
                        Hi!
                    \</div\>
                \</div\>
            \</div\>
            \<div id="typing"\>
                \<div\>\<span\>\</span\> \<span\>\</span\> \<span\>\</span\> \<span class="n"\>Someone\</span\> is typing...\</div\>
            \</div\>
            \<div class="chat-box-footer"\>
                \<textarea id="chat_input" placeholder="Enter your message here..."\>\</textarea\>
                \<button id="send"\>
                    \<svg style="width:24px;height:24px" viewBox="0 0 24 24"\>
                        \<path fill="\#006ae3" d="M2,21L23,12L2,3V10L17,12L2,14V21Z" /\>
                    \</svg\>
                \</button\>
            \</div\>
        \</div\>
    \</div\>
`;

result();

document.getElementById('chat_input').value = "Helloooooooooooooooo, its me... :D";
document.getElementById('send').click();

let messages = document.getElementById('chat_messages').children;

assert.equal(messages.length, 5, 'The messages count is invalid');
assert.equal(messages\[4\].textContent, 'Helloooooooooooooooo, its me... :D', 'The expected message is different.');
assert.equal(messages\[4\].tagName, 'DIV', 'The expected message element should be DIV');
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// Class name check
document.body.innerHTML = `
\<div class="flexbox"\>
        \<div class="chat-box"\>
            \<div class="chat-box-header"\>
                \<h3\>Chat Room\<br /\>\<small\>Last active: 2 min ago\</small\>\</h3\>
            \</div\>
            \<div id="chat_box_body" class="chat-box-body"\>
                \<div id="chat_messages"\>
                    \<div class="profile other-profile"\>
                        \<img src="https://images.unsplash.com/photo-1537396123722-b93d0acd8848?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=efc6e85c24d3cfdd15cd36cb8a2471ed"
                            width="30" height="30" /\>
                        \<span\>Other profile\</span\>
                    \</div\>
                    \<div class="message other-message"\>
                        Sorry, I am busy right now, Can I write you back later?
                    \</div\>
                    \<div class="profile my-profile"\>
                        \<span\>My profile\</span\>
                        \<img src="https://images.unsplash.com/photo-1534135954997-e58fbd6dbbfc?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=02d536c38d9cfeb4f35f17fdfaa36619"
                            width="30" height="30" /\>
                    \</div\>

                    \<div class="message my-message"\>
                        Hi!
                    \</div\>
                \</div\>
            \</div\>
            \<div id="typing"\>
                \<div\>\<span\>\</span\> \<span\>\</span\> \<span\>\</span\> \<span class="n"\>Someone\</span\> is typing...\</div\>
            \</div\>
            \<div class="chat-box-footer"\>
                \<textarea id="chat_input" placeholder="Enter your message here..."\>\</textarea\>
                \<button id="send"\>
                    \<svg style="width:24px;height:24px" viewBox="0 0 24 24"\>
                        \<path fill="\#006ae3" d="M2,21L23,12L2,3V10L17,12L2,14V21Z" /\>
                    \</svg\>
                \</button\>
            \</div\>
        \</div\>
    \</div\>
`;

result();

document.getElementById('chat_input').value = "Helloooooooooooooooo, its me... :D";
document.getElementById('send').click();

let messages = document.getElementById('chat_messages').children;

assert.equal(messages\[4\].className, 'message my-message', 'The expected className is different.');
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// Clearing input field
document.body.innerHTML = `
\<div class="flexbox"\>
        \<div class="chat-box"\>
            \<div class="chat-box-header"\>
                \<h3\>Chat Room\<br /\>\<small\>Last active: 2 min ago\</small\>\</h3\>
            \</div\>
            \<div id="chat_box_body" class="chat-box-body"\>
                \<div id="chat_messages"\>
                    \<div class="profile other-profile"\>
                        \<img src="https://images.unsplash.com/photo-1537396123722-b93d0acd8848?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=efc6e85c24d3cfdd15cd36cb8a2471ed"
                            width="30" height="30" /\>
                        \<span\>Other profile\</span\>
                    \</div\>
                    \<div class="message other-message"\>
                        Sorry, I am busy right now, Can I write you back later?
                    \</div\>
                    \<div class="profile my-profile"\>
                        \<span\>My profile\</span\>
                        \<img src="https://images.unsplash.com/photo-1534135954997-e58fbd6dbbfc?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=02d536c38d9cfeb4f35f17fdfaa36619"
                            width="30" height="30" /\>
                    \</div\>

                    \<div class="message my-message"\>
                        Hi!
                    \</div\>
                \</div\>
            \</div\>
            \<div id="typing"\>
                \<div\>\<span\>\</span\> \<span\>\</span\> \<span\>\</span\> \<span class="n"\>Someone\</span\> is typing...\</div\>
            \</div\>
            \<div class="chat-box-footer"\>
                \<textarea id="chat_input" placeholder="Enter your message here..."\>\</textarea\>
                \<button id="send"\>
                    \<svg style="width:24px;height:24px" viewBox="0 0 24 24"\>
                        \<path fill="\#006ae3" d="M2,21L23,12L2,3V10L17,12L2,14V21Z" /\>
                    \</svg\>
                \</button\>
            \</div\>
        \</div\>
    \</div\>
`;

result();

let input = document.getElementById('chat_input');
input.value = "Just TESTING";
document.getElementById('send').click();

assert.equal(input.value, '', 'The input field, should be cleared!');
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// Multiple messages
document.body.innerHTML = `
\<div class="flexbox"\>
        \<div class="chat-box"\>
            \<div class="chat-box-header"\>
                \<h3\>Chat Room\<br /\>\<small\>Last active: 2 min ago\</small\>\</h3\>
            \</div\>
            \<div id="chat_box_body" class="chat-box-body"\>
                \<div id="chat_messages"\>
                    \<div class="profile other-profile"\>
                        \<img src="https://images.unsplash.com/photo-1537396123722-b93d0acd8848?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=efc6e85c24d3cfdd15cd36cb8a2471ed"
                            width="30" height="30" /\>
                        \<span\>Other profile\</span\>
                    \</div\>
                    \<div class="message other-message"\>
                        Sorry, I am busy right now, Can I write you back later?
                    \</div\>
                    \<div class="profile my-profile"\>
                        \<span\>My profile\</span\>
                        \<img src="https://images.unsplash.com/photo-1534135954997-e58fbd6dbbfc?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=02d536c38d9cfeb4f35f17fdfaa36619"
                            width="30" height="30" /\>
                    \</div\>

                    \<div class="message my-message"\>
                        Hi!
                    \</div\>
                \</div\>
            \</div\>
            \<div id="typing"\>
                \<div\>\<span\>\</span\> \<span\>\</span\> \<span\>\</span\> \<span class="n"\>Someone\</span\> is typing...\</div\>
            \</div\>
            \<div class="chat-box-footer"\>
                \<textarea id="chat_input" placeholder="Enter your message here..."\>\</textarea\>
                \<button id="send"\>
                    \<svg style="width:24px;height:24px" viewBox="0 0 24 24"\>
                        \<path fill="\#006ae3" d="M2,21L23,12L2,3V10L17,12L2,14V21Z" /\>
                    \</svg\>
                \</button\>
            \</div\>
        \</div\>
    \</div\>
`;

result();

let input = document.getElementById('chat_input');
let button = document.getElementById('send');

input.value = "Are you there?";
button.click();

input.value = "Hello???";
button.click();

input.value = "Cmon man, don't waste my time... :@";
button.click();

let messages = document.getElementById('chat_messages').children;

assert.equal(messages.length, 7, 'The messages count is invalid');
assert.equal(messages\[4\].textContent, 'Are you there?', 'The expected message is different.');
assert.equal(messages\[5\].textContent, 'Hello???', 'The expected message is different.');
assert.equal(messages\[6\].textContent, "Cmon man, don't waste my time... :@", 'The expected message is different.');
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// Children length, textContent, tagName
document.body.innerHTML = `
\<div class="flexbox"\>
        \<div class="chat-box"\>
            \<div class="chat-box-header"\>
                \<h3\>Chat Room\<br /\>\<small\>Last active: 2 min ago\</small\>\</h3\>
            \</div\>
            \<div id="chat_box_body" class="chat-box-body"\>
                \<div id="chat_messages"\>
                    \<div class="profile other-profile"\>
                        \<img src="https://images.unsplash.com/photo-1537396123722-b93d0acd8848?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=efc6e85c24d3cfdd15cd36cb8a2471ed"
                            width="30" height="30" /\>
                        \<span\>Other profile\</span\>
                    \</div\>
                    \<div class="message other-message"\>
                        Sorry, I am busy right now, Can I write you back later?
                    \</div\>
                    \<div class="profile my-profile"\>
                        \<span\>My profile\</span\>
                        \<img src="https://images.unsplash.com/photo-1534135954997-e58fbd6dbbfc?ixlib=rb-0.3.5&q=80&fm=jpg&crop=entropy&cs=tinysrgb&w=400&fit=max&ixid=eyJhcHBfaWQiOjE0NTg5fQ&s=02d536c38d9cfeb4f35f17fdfaa36619"
                            width="30" height="30" /\>
                    \</div\>

                    \<div class="message my-message"\>
                        Hi!
                    \</div\>
                \</div\>
            \</div\>
            \<div id="typing"\>
                \<div\>\<span\>\</span\> \<span\>\</span\> \<span\>\</span\> \<span class="n"\>Someone\</span\> is typing...\</div\>
            \</div\>
            \<div class="chat-box-footer"\>
                \<textarea id="chat_input" placeholder="Enter your message here..."\>\</textarea\>
                \<button id="send"\>
                    \<svg style="width:24px;height:24px" viewBox="0 0 24 24"\>
                        \<path fill="\#006ae3" d="M2,21L23,12L2,3V10L17,12L2,14V21Z" /\>
                    \</svg\>
                \</button\>
            \</div\>
        \</div\>
    \</div\>
`;

result();

document.getElementById('chat_input').value = "Hello";
document.getElementById('send').click();

document.getElementById('chat_input').value = "It's me again";
document.getElementById('send').click();

let messages = document.getElementById('chat_messages').children;

assert.equal(messages.length, 6, 'The messages count is invalid');
assert.equal(messages\[4\].textContent, 'Hello', 'The expected message is different.');
assert.equal(messages\[4\].tagName, 'DIV', 'The expected message element should be DIV');

assert.equal(messages\[5\].textContent, "It's me again", 'The expected message is different.');
assert.equal(messages\[5\].tagName, 'DIV', 'The expected message element should be DIV');
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]

# Problemă: Numpad Calculator

[code-task title="Numpad Calculator" taskId="js-advanced-DOM-Numpad-Calculator" executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]

```
function numpadCalculator(){
  // Scrieți codul dvs. aici
}
```

[/code-editor]
[task-description]

# Descriere

**Aveți un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/06-Numpad-Calculator.zip) **pentru această sarcină**.

Scrieți o **funcție** care implementează un **calculator** cu următoarele funcționalități.

[image assetsSrc="JS-Advanced-DOM-Homework-14.png" /]

Când unul dintre **butoane este apăsat**, valoarea acestuia trebuie afișată în câmpul "**Expression**" (`#expressionOutput`).

De exemplu, dacă facem clic pe butonul cu valoarea **9**, **rezultatul** așteptat ar trebui să fie:

[image assetsSrc="JS-Advanced-DOM-Homework-15.png" /]

Dacă câmpul **Expression** curent (`#expresisonOutput`) conține întreaga expresie matematică (**operandul din stânga**, **operatorul** și **operand din dreapta**: "**9 + 2**", de exemplu), **rezultatul** așteptat ar trebui să fie:

[image assetsSrc="JS-Advanced-DOM-Homework-16.png" /]

Când se apasă **semnul egal** `=`, rezultatul acelei expresii **trebuie să apară în câmpul Result** (`#resultOutput`).

[image assetsSrc="JS-Advanced-DOM-Homework-17.png" /]

În caz contrar, dacă creăm o **expresie nevalidă**, cum ar fi `"99 +" (fără operandul stâng/drept)`, și facem clic pe semnul egal `=`, rezultatul așteptat ar trebui să fie:

[image assetsSrc="JS-Advanced-DOM-Homework-18.png" /]

Butonul "**Clear**" trebuie să șteargă atât câmpul Expression, cât și Result (`#expressionOutput` și `#resultOutput`)

De exemplu, dacă avem următoarea expresie:

[image assetsSrc="JS-Advanced-DOM-Homework-19.png" /]

Și apăsăm "**Clear**", rezultatul așteptat ar trebui să fie:

[image assetsSrc="JS-Advanced-DOM-Homework-20.png" /]

[hints]
[hint]
Creați un obiect **"operations"** cu metode pentru **fiecare** operație aritmetică:

```js
const operations = {
  '+': (num1, num2) => Number(num1) + Number(num2),
  '-': (num1, num2) => Number(num1) - Number(num2),
  '*': (num1, num2) => Number(num1) * Number(num2),
  '/': (num1, num2) => Number(num1) / Number(num2)
};
```

Obțineți **valoarea** țintei click curente.
[/hint] 
[hint]
Obțineți **tastatura** folosind numele de clasă `keys` și atașați la ea un ascultător de evenimente:

```js
const pad = document
  .getElementsByClassName('keys')[0];

pad.addEventListener('click', (e) => {
  let value = e.target.value;

  // ... 
})
```

Obțineți **valoarea** țintei click curente. 
[/hint] 
[hint]
Dacă utilizatorul apasă pe semnul **egal**, trebuie să afișați rezultatul în div-ul `resultOutput`:

```js
if (value === '=') {
  const params = expressionOutput
    .innerHTML
    .split(' ')
    .filter(x => x !== '');

  const numOne = params[0];
  const operation = params[1];
  const numTwo = params[2];

   return resultOutput.innerHTML = 
     operations[operation](numOne, numTwo);
}
```
[/hint] 
[hint]
Dacă apasă pe oricare dintre **operatorii aritmetici**, actualizați `innerHTML` al `expressionOutput` cu sintaxa **" {sign} "**: 

```js
if (operators.includes(value)) {
  return expressionOutput.innerHTML 
    += ` ${value} `;
}
```
[/hint] 
[/hints]


[/task-description]
[code-io /]
[tests]
[test open]
[input]
document.body.innerHTML = `
	\<div id="calculator"\>
		\<!-- Screen and clear key --\>
		\<div class="top"\>
			\<button class="clear" type="button" value="Clear"\>C\</button\>
			\<p id="expressionOutput"\>\</p\>
			\<p id="resultOutput"\>\</p\>
			\<div id="result"\>\</div\>
		\</div\>

		\<div class="keys"\>
			\<!-- operators and other keys --\>
			\<button type="button" value="7"\>7\</button\>
			\<button type="button" value="8"\>8\</button\>
			\<button type="button" value="9"\>9\</button\>
			\<button type="button" value="/"\>/\</button\>
			\<button type="button" value="4"\>4\</button\>
			\<button type="button" value="5"\>5\</button\>
			\<button type="button" value="6"\>6\</button\>
			\<button type="button" value="\*"\>x\</button\>
			\<button type="button" value="1"\>1\</button\>
			\<button type="button" value="2"\>2\</button\>
			\<button type="button" value="3"\>3\</button\>
			\<button type="button" value="-"\>-\</button\>
			\<button type="button" value="0"\>0\</button\>
			\<button type="button" value="."\>.\</button\>
			\<button type="button" value="="\>=\</button\>
			\<button type="button" value="+"\>+\</button\>
		\</div\>
	\</div\>
`;

result();

\\$("button\[value='1'\]")\[0\].click();
\\$("button\[value='2'\]")\[0\].click();

\\$("button\[value='+'\]")\[0\].click();

\\$("button\[value='3'\]")\[0\].click();
\\$("button\[value='='\]")\[0\].click();

let test1 = \\$("\#expressionOutput")\[0\].innerHTML;
let test2 = \\$("\#resultOutput")\[0\].innerHTML;

\\$("button\[value='Clear'\]")\[0\].click();

let test3 = \\$("\#expressionOutput")\[0\].innerHTML;
let test4 = \\$("\#resultOutput")\[0\].innerHTML;

expect(test1).to.equal("12 + 3");
expect(test2).to.equal("15");
expect(test3).to.equal("");
expect(test4).to.equal("");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
	\<div id="calculator"\>
		\<!-- Screen and clear key --\>
		\<div class="top"\>
			\<button class="clear" type="button" value="Clear"\>C\</button\>
			\<p id="expressionOutput"\>\</p\>
			\<p id="resultOutput"\>\</p\>
			\<div id="result"\>\</div\>
		\</div\>

		\<div class="keys"\>
			\<!-- operators and other keys --\>
			\<button type="button" value="7"\>7\</button\>
			\<button type="button" value="8"\>8\</button\>
			\<button type="button" value="9"\>9\</button\>
			\<button type="button" value="/"\>/\</button\>
			\<button type="button" value="4"\>4\</button\>
			\<button type="button" value="5"\>5\</button\>
			\<button type="button" value="6"\>6\</button\>
			\<button type="button" value="\*"\>x\</button\>
			\<button type="button" value="1"\>1\</button\>
			\<button type="button" value="2"\>2\</button\>
			\<button type="button" value="3"\>3\</button\>
			\<button type="button" value="-"\>-\</button\>
			\<button type="button" value="0"\>0\</button\>
			\<button type="button" value="."\>.\</button\>
			\<button type="button" value="="\>=\</button\>
			\<button type="button" value="+"\>+\</button\>
		\</div\>
	\</div\>
`;

result();

\\$("button\[value='3'\]")\[0\].click();
\\$("button\[value='4'\]")\[0\].click();
\\$("button\[value='5'\]")\[0\].click();

\\$("button\[value='-'\]")\[0\].click();

\\$("button\[value='7'\]")\[0\].click();
\\$("button\[value='8'\]")\[0\].click();

\\$("button\[value='='\]")\[0\].click();

let test1 = \\$("\#expressionOutput")\[0\].innerHTML;

expect(test1).to.equal("345 - 78");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
	\<div id="calculator"\>
		\<!-- Screen and clear key --\>
		\<div class="top"\>
			\<button class="clear" type="button" value="Clear"\>C\</button\>
			\<p id="expressionOutput"\>\</p\>
			\<p id="resultOutput"\>\</p\>
			\<div id="result"\>\</div\>
		\</div\>

		\<div class="keys"\>
			\<!-- operators and other keys --\>
			\<button type="button" value="7"\>7\</button\>
			\<button type="button" value="8"\>8\</button\>
			\<button type="button" value="9"\>9\</button\>
			\<button type="button" value="/"\>/\</button\>
			\<button type="button" value="4"\>4\</button\>
			\<button type="button" value="5"\>5\</button\>
			\<button type="button" value="6"\>6\</button\>
			\<button type="button" value="\*"\>x\</button\>
			\<button type="button" value="1"\>1\</button\>
			\<button type="button" value="2"\>2\</button\>
			\<button type="button" value="3"\>3\</button\>
			\<button type="button" value="-"\>-\</button\>
			\<button type="button" value="0"\>0\</button\>
			\<button type="button" value="."\>.\</button\>
			\<button type="button" value="="\>=\</button\>
			\<button type="button" value="+"\>+\</button\>
		\</div\>
	\</div\>
`;

result();

\\$("button\[value='9'\]")\[0\].click();

\\$("button\[value='\*'\]")\[0\].click();

\\$("button\[value='8'\]")\[0\].click();
\\$("button\[value='0'\]")\[0\].click();

\\$("button\[value='='\]")\[0\].click();

let test2 = \\$("\#resultOutput")\[0\].innerHTML;

expect(test2).to.equal("720");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
	\<div id="calculator"\>
		\<!-- Screen and clear key --\>
		\<div class="top"\>
			\<button class="clear" type="button" value="Clear"\>C\</button\>
			\<p id="expressionOutput"\>\</p\>
			\<p id="resultOutput"\>\</p\>
			\<div id="result"\>\</div\>
		\</div\>

		\<div class="keys"\>
			\<!-- operators and other keys --\>
			\<button type="button" value="7"\>7\</button\>
			\<button type="button" value="8"\>8\</button\>
			\<button type="button" value="9"\>9\</button\>
			\<button type="button" value="/"\>/\</button\>
			\<button type="button" value="4"\>4\</button\>
			\<button type="button" value="5"\>5\</button\>
			\<button type="button" value="6"\>6\</button\>
			\<button type="button" value="\*"\>x\</button\>
			\<button type="button" value="1"\>1\</button\>
			\<button type="button" value="2"\>2\</button\>
			\<button type="button" value="3"\>3\</button\>
			\<button type="button" value="-"\>-\</button\>
			\<button type="button" value="0"\>0\</button\>
			\<button type="button" value="."\>.\</button\>
			\<button type="button" value="="\>=\</button\>
			\<button type="button" value="+"\>+\</button\>
		\</div\>
	\</div\>
`;

result();

\\$("button\[value='7'\]")\[0\].click();
\\$("button\[value='2'\]")\[0\].click();
\\$("button\[value='0'\]")\[0\].click();

\\$("button\[value='/'\]")\[0\].click();

\\$("button\[value='9'\]")\[0\].click();

\\$("button\[value='='\]")\[0\].click();

let test2 = \\$("\#resultOutput")\[0\].innerHTML;

expect(test2).to.equal("80");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
	\<div id="calculator"\>
		\<!-- Screen and clear key --\>
		\<div class="top"\>
			\<button class="clear" type="button" value="Clear"\>C\</button\>
			\<p id="expressionOutput"\>\</p\>
			\<p id="resultOutput"\>\</p\>
			\<div id="result"\>\</div\>
		\</div\>

		\<div class="keys"\>
			\<!-- operators and other keys --\>
			\<button type="button" value="7"\>7\</button\>
			\<button type="button" value="8"\>8\</button\>
			\<button type="button" value="9"\>9\</button\>
			\<button type="button" value="/"\>/\</button\>
			\<button type="button" value="4"\>4\</button\>
			\<button type="button" value="5"\>5\</button\>
			\<button type="button" value="6"\>6\</button\>
			\<button type="button" value="\*"\>x\</button\>
			\<button type="button" value="1"\>1\</button\>
			\<button type="button" value="2"\>2\</button\>
			\<button type="button" value="3"\>3\</button\>
			\<button type="button" value="-"\>-\</button\>
			\<button type="button" value="0"\>0\</button\>
			\<button type="button" value="."\>.\</button\>
			\<button type="button" value="="\>=\</button\>
			\<button type="button" value="+"\>+\</button\>
		\</div\>
	\</div\>
`;

result();

\\$("button\[value='1'\]")\[0\].click();
\\$("button\[value='+'\]")\[0\].click();
\\$("button\[value='5'\]")\[0\].click();
\\$("button\[value='='\]")\[0\].click();

\\$("button\[value='Clear'\]")\[0\].click();

let test4 = \\$("\#resultOutput")\[0\].innerHTML;

expect(test4).to.equal("");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
	\<div id="calculator"\>
		\<!-- Screen and clear key --\>
		\<div class="top"\>
			\<button class="clear" type="button" value="Clear"\>C\</button\>
			\<p id="expressionOutput"\>\</p\>
			\<p id="resultOutput"\>\</p\>
			\<div id="result"\>\</div\>
		\</div\>

		\<div class="keys"\>
			\<!-- operators and other keys --\>
			\<button type="button" value="7"\>7\</button\>
			\<button type="button" value="8"\>8\</button\>
			\<button type="button" value="9"\>9\</button\>
			\<button type="button" value="/"\>/\</button\>
			\<button type="button" value="4"\>4\</button\>
			\<button type="button" value="5"\>5\</button\>
			\<button type="button" value="6"\>6\</button\>
			\<button type="button" value="\*"\>x\</button\>
			\<button type="button" value="1"\>1\</button\>
			\<button type="button" value="2"\>2\</button\>
			\<button type="button" value="3"\>3\</button\>
			\<button type="button" value="-"\>-\</button\>
			\<button type="button" value="0"\>0\</button\>
			\<button type="button" value="."\>.\</button\>
			\<button type="button" value="="\>=\</button\>
			\<button type="button" value="+"\>+\</button\>
		\</div\>
	\</div\>
`;

result();

\\$("button\[value='1'\]")\[0\].click();
\\$("button\[value='3'\]")\[0\].click();

\\$("button\[value='\*'\]")\[0\].click();

\\$("button\[value='4'\]")\[0\].click();
\\$("button\[value='='\]")\[0\].click();

\\$("button\[value='Clear'\]")\[0\].click();

let test3 = \\$("\#expressionOutput")\[0\].innerHTML;
let test4 = \\$("\#resultOutput")\[0\].innerHTML;

expect(test3).to.equal("");
expect(test4).to.equal("");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
	\<div id="calculator"\>
		\<!-- Screen and clear key --\>
		\<div class="top"\>
			\<button class="clear" type="button" value="Clear"\>C\</button\>
			\<p id="expressionOutput"\>\</p\>
			\<p id="resultOutput"\>\</p\>
			\<div id="result"\>\</div\>
		\</div\>

		\<div class="keys"\>
			\<!-- operators and other keys --\>
			\<button type="button" value="7"\>7\</button\>
			\<button type="button" value="8"\>8\</button\>
			\<button type="button" value="9"\>9\</button\>
			\<button type="button" value="/"\>/\</button\>
			\<button type="button" value="4"\>4\</button\>
			\<button type="button" value="5"\>5\</button\>
			\<button type="button" value="6"\>6\</button\>
			\<button type="button" value="\*"\>x\</button\>
			\<button type="button" value="1"\>1\</button\>
			\<button type="button" value="2"\>2\</button\>
			\<button type="button" value="3"\>3\</button\>
			\<button type="button" value="-"\>-\</button\>
			\<button type="button" value="0"\>0\</button\>
			\<button type="button" value="."\>.\</button\>
			\<button type="button" value="="\>=\</button\>
			\<button type="button" value="+"\>+\</button\>
		\</div\>
	\</div\>
`;

result();

\\$("button\[value='1'\]")\[0\].click();
\\$("button\[value='5'\]")\[0\].click();
\\$("button\[value='.'\]")\[0\].click();
\\$("button\[value='5'\]")\[0\].click();

\\$("button\[value='+'\]")\[0\].click();

\\$("button\[value='3'\]")\[0\].click();
\\$("button\[value='6'\]")\[0\].click();
\\$("button\[value='.'\]")\[0\].click();
\\$("button\[value='8'\]")\[0\].click();

\\$("button\[value='='\]")\[0\].click();

let test1 = \\$("\#expressionOutput")\[0\].innerHTML;
let test2 = \\$("\#resultOutput")\[0\].innerHTML;

\\$("button\[value='Clear'\]")\[0\].click();

let test3 = \\$("\#expressionOutput")\[0\].innerHTML;
let test4 = \\$("\#resultOutput")\[0\].innerHTML;

expect(test1).to.equal("15.5 + 36.8");
expect(test2).to.equal("52.3");
expect(test3).to.equal("");
expect(test4).to.equal("");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
document.body.innerHTML = `
	\<div id="calculator"\>
		\<!-- Screen and clear key --\>
		\<div class="top"\>
			\<button class="clear" type="button" value="Clear"\>C\</button\>
			\<p id="expressionOutput"\>\</p\>
			\<p id="resultOutput"\>\</p\>
			\<div id="result"\>\</div\>
		\</div\>

		\<div class="keys"\>
			\<!-- operators and other keys --\>
			\<button type="button" value="7"\>7\</button\>
			\<button type="button" value="8"\>8\</button\>
			\<button type="button" value="9"\>9\</button\>
			\<button type="button" value="/"\>/\</button\>
			\<button type="button" value="4"\>4\</button\>
			\<button type="button" value="5"\>5\</button\>
			\<button type="button" value="6"\>6\</button\>
			\<button type="button" value="\*"\>x\</button\>
			\<button type="button" value="1"\>1\</button\>
			\<button type="button" value="2"\>2\</button\>
			\<button type="button" value="3"\>3\</button\>
			\<button type="button" value="-"\>-\</button\>
			\<button type="button" value="0"\>0\</button\>
			\<button type="button" value="."\>.\</button\>
			\<button type="button" value="="\>=\</button\>
			\<button type="button" value="+"\>+\</button\>
		\</div\>
	\</div\>
`;

result();

\\$("button\[value='1'\]")\[0\].click();
\\$("button\[value='5'\]")\[0\].click();
\\$("button\[value='.'\]")\[0\].click();
\\$("button\[value='5'\]")\[0\].click();

\\$("button\[value='+'\]")\[0\].click();

\\$("button\[value='='\]")\[0\].click();

let test1 = \\$("\#expressionOutput")\[0\].innerHTML;
let test2 = \\$("\#resultOutput")\[0\].innerHTML;

\\$("button\[value='Clear'\]")\[0\].click();

expect(test1).to.equal("15.5 + ");
expect(test2).to.equal("NaN");
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]

# Problemă: Number Convertor

[code-task title="Number Convertor" taskId="js-advanced-DOM-Number-Convertor" executionType="tests-execution" executionStrategy="javascript-js-dom-unit-tests" requiresInput] [code-editor language=javascript]

```
function numberConvertor(){
  // Scrieți codul dvs. aici
}
```

[/code-editor]
[task-description]

# Descriere

**Aveți un link către** [resursele](https://videos.softuni.org/resources/javascript/javascript-advanced/07-Number-Convertor.zip) **pentru această sarcină**.

Scrieți o funcție care **convertește** un **număr zecimal** în reprezentarea sa **binară** și **hexazecimală**.

[image assetsSrc="JS-Advanced-DOM-Homework-21.jpg" /]

Numărul dat va fi întotdeauna în **format zecimal**.

Meniul de selecție "**From**" va avea doar o opțiune **Decimal**, dar meniul de selecție "**To**" va avea **două opțiuni:** **binary** și **hexadeicmal**.

Aceasta înseamnă că programul nostru ar trebui să aibă funcționalitatea de a **converti un număr zecimal** în reprezentarea sa **binară** și **hexazecimală**.

Rețineți că meniul de selecție "**To**" este gol în mod implicit.

Trebuie să introduceți cele două opțiuni (**binary** și **hexadecimal**) înăuntru înainte de a continua.

De asemenea, acestea ar trebui să aibă **valori** (binare și hexazecimale).

- Când **se apasă** butonul `[Convert it]` rezultatul așteptat trebuie să apară în câmpul de intrare `[Result]`

[image assetsSrc="JS-Advanced-DOM-Homework-22.jpg" /]

[image assetsSrc="JS-Advanced-DOM-Homework-23.jpg" /]

[/task-description]
[code-io /]
[tests]
[test open]
[input]
// 20 to binary
document.body.innerHTML = \`
\<div id="container"\>
    \<label for="input"\>Number\</label\>
    \<input type="number" id="input"/\>\<br\>
    \<label for="selectMenuFrom"\>From\</label\>
    \<select id="selectMenuFrom"\>
        \<option selected value="decimal"\>Decimal\</option\>
    \</select\>
    \<label for="selectMenuTo"\>To\</label\>
    \<select id="selectMenuTo"\>
        \<option selected value=""\>\</option\>
    \</select\>
    \<button\>Convert it\</button\>
\</div\>
\<footer\>
    \<label for="result"\>Result\</label\>
    \<input type="text" name="output" id="result" disabled readonly/\>
\</footer\>
\`;

result();

\\$("\#input").val("20");
\\$("\#selectMenuTo").val("binary");
\\$("button").trigger("click");

let res = \\$("\#result").val();
expect(res).to.equal("10100");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// 100 to binary
document.body.innerHTML = \`
\<div id="container"\>
    \<label for="input"\>Number\</label\>
    \<input type="number" id="input"/\>\<br\>
    \<label for="selectMenuFrom"\>From\</label\>
    \<select id="selectMenuFrom"\>
        \<option selected value="decimal"\>Decimal\</option\>
    \</select\>
    \<label for="selectMenuTo"\>To\</label\>
    \<select id="selectMenuTo"\>
        \<option selected value=""\>\</option\>
    \</select\>
    \<button\>Convert it\</button\>
\</div\>
\<footer\>
    \<label for="result"\>Result\</label\>
    \<input type="text" name="output" id="result" disabled readonly/\>
\</footer\>
\`;

result();

\\$("\#input").val("100");
\\$("\#selectMenuTo").val("binary");
\\$("button").trigger("click");

let res = \\$("\#result").val();
expect(res).to.equal("1100100");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// 110 to hexadecimal
document.body.innerHTML = \`
\<div id="container"\>
    \<label for="input"\>Number\</label\>
    \<input type="number" id="input"/\>\<br\>
    \<label for="selectMenuFrom"\>From\</label\>
    \<select id="selectMenuFrom"\>
        \<option selected value="decimal"\>Decimal\</option\>
    \</select\>
    \<label for="selectMenuTo"\>To\</label\>
    \<select id="selectMenuTo"\>
        \<option selected value=""\>\</option\>
    \</select\>
    \<button\>Convert it\</button\>
\</div\>
\<footer\>
    \<label for="result"\>Result\</label\>
    \<input type="text" name="output" id="result" disabled readonly/\>
\</footer\>
\`;

result();

\\$("\#input").val("110");
\\$("\#selectMenuTo").val("hexadecimal");
\\$("button").trigger("click");

let res = \\$("\#result").val();
expect(res).to.equal("6E");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// 1515 to hexadecimal
document.body.innerHTML = \`
\<div id="container"\>
    \<label for="input"\>Number\</label\>
    \<input type="number" id="input"/\>\<br\>
    \<label for="selectMenuFrom"\>From\</label\>
    \<select id="selectMenuFrom"\>
        \<option selected value="decimal"\>Decimal\</option\>
    \</select\>
    \<label for="selectMenuTo"\>To\</label\>
    \<select id="selectMenuTo"\>
        \<option selected value=""\>\</option\>
    \</select\>
    \<button\>Convert it\</button\>
\</div\>
\<footer\>
    \<label for="result"\>Result\</label\>
    \<input type="text" name="output" id="result" disabled readonly/\>
\</footer\>
\`;

result();

\\$("\#input").val("1515");
\\$("\#selectMenuTo").val("hexadecimal");
\\$("button").trigger("click");

let res = \\$("\#result").val();
expect(res).to.equal("5EB");
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
// 903 to binary
document.body.innerHTML = \`
\<div id="container"\>
    \<label for="input"\>Number\</label\>
    \<input type="number" id="input"/\>\<br\>
    \<label for="selectMenuFrom"\>From\</label\>
    \<select id="selectMenuFrom"\>
        \<option selected value="decimal"\>Decimal\</option\>
    \</select\>
    \<label for="selectMenuTo"\>To\</label\>
    \<select id="selectMenuTo"\>
        \<option selected value=""\>\</option\>
    \</select\>
    \<button\>Convert it\</button\>
\</div\>
\<footer\>
    \<label for="result"\>Result\</label\>
    \<input type="text" name="output" id="result" disabled readonly/\>
\</footer\>
\`;

result();

\\$("\#input").val("903");
\\$("\#selectMenuTo").val("binary");
\\$("button").trigger("click");

let res = \\$("\#result").val();
expect(res).to.equal("1110000111");
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]
