# "this" în Funcții
[slide hideTitle]

# "this" cu Funcții Interne

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-13-14-this-with-inner-functions-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

**Funcțiile interne** sunt funcții care sunt imbricate în interiorul altor funcții.

Încercarea de a apela `this` dintr-o funcție imbricată nu funcționează așa cum era de așteptat:

```js live
let socialMediaUser = {
    name: 'John Doe',
    pageLikes: ['Cute Cats Page', 'Web Programming Gurus', 'SoftUni International'],
    displayLikes: function() {
        this.pageLikes.forEach(function(page) {
            console.log(`User: ${this.name} likes: ${page}`);
        });
    }
}
socialMediaUser.displayLikes();
```

Apelarea `this.name` din interiorul funcției imbricate returnează **undefined**. 

Acest lucru se datorează faptului că `this` face referire la obiectul global în contextul funcțiilor imbricate.

Dacă doriți să utilizați `this` în situații similare, puteți face acest lucru cu **funcții săgeată**, despre care vom vorbi în continuare.

[/slide]

[slide hideTitle]
# "this" cu Funcții Săgeată

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-15-this-with-arrow-functions-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Cu **funcțiile săgeată** (`=>`), `this` păstrează valoarea **contextului lexical care îl înconjoară**

Cu alte cuvinte, ele moștenesc referința lui `this` de la obiectul părinte sau domeniul de aplicare în care sunt utilizate

```js live
let socialMediaUser = {
    name: 'John Doe',
    pageLikes: ['Cute Cats Page', 'Web Programming Gurus', 'SoftUni International'],
    displayLikes: function() {
        this.pageLikes.forEach((page) => {
            console.log(`User: ${this.name} likes: ${page}`);
        });
    }
}
socialMediaUser.displayLikes();
```

De această dată rezultatul este corect și numele utilizatorului nu mai este **undefined**. 

Diferența dintre exemplul anterior și cel curent este că acum am folosit o **funcție săgeată**.

Această funcție a moștenit contextul din obiectul atașat **socialMediaUser**, deci avem: 

[/slide]
