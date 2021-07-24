[slide hideTitle]

# Rezumat

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-36-summary-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

## În această lecție ați învățat: 

- Bucla de eveniment
- Tipuri de evenimente: `document.addEventListener('click', getEventType);`
- Proprietățile și metodele obiectukui de tip eveniment 
    - preventDefault: `event.preventDefault();`
    - stopPropagation: `event.stopPropagation();`
- Gestionarea evenimentelor
    - atașarea unui ascultător de evenimente
    ```js
    button.addEventListener('click', () => {
    console.log('Button clicked.');
    });
    ```
    - eliminarea unui ascultător de evenimente
     ```js
    button.removeEventListener('click', () => {
    console.log('Button event listener removed.');
    });
    ```
    
## În următoarea lecție veți învăța despre:

- Ce este `this` 

- Moduri de utilizare a cuvântului cheie `this` 

- Utilizarea lui `this` în funcții

- Legarea explicită 

- Proprietăți interne ale obiectelor
[/slide]
