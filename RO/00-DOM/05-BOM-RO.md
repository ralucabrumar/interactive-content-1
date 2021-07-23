# Browser Object Model

[slide hideTitle]

# BOM

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/01.JS-Advanced-DOM/RO/JS-Advanced-DOM-40-41-browser-object-model-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

**Browser Object Model** acționează ca o conexiune la fel ca și **Document Object Model**.

El conecteazâ JavaScript la **browser** la fel cum DOM îl conectează la **documentul HTML**.

**BOM** permite accesarea şi manipularea elementelor din browser prin **reprezentarea lor ca obiecte**.

[image assetsSrc="Js-advanced-DOM-1.png" /]

Următoarele comenzi arată câteva dintre obiectele din browser:

```js
console.dir(window);
console.dir(navigator);
console.dir(screen);
console.dir(location);
console.dir(history);
console.dir(document);
```

**Fereastra** este obiectul global din browser.

Toate variabilele globale sunt **proprietățile** sale și toate funcțiile globale sunt **metodele** sale.

```js
var name = 'Steven';
//name este acum stocat ca proprietate a obiectului de tip fereastră

function printYear() {
  console.log(2020);
}
//PrintYear este acum o metodă a obiectului de tip fereastră

name === window.name;
//returns true

window.printYear();
//invocă funcția prin obiectul de tip fereastră
```

[/slide]

[slide hideTitle]

# Exerciții cu BOM

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/01.JS-Advanced-DOM/RO/JS-Advanced-DOM-42-playing-with-bom-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Iatâ câteva proprietăți interesante și educative ale lui BOM:

```js
console.log(navigator.deviceMemory); //afișează memroia RAM a mașinii curente

document.location = 'https://softuni.org'; //redirecționează la o locație dată

history.back(); //merge înapoi o dată

console.log(location.host); //afișează host-ul curent

location.reload(); //reîncarcă pagina
```

[/slide]
