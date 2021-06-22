# Mongoose Middleware

[slide hideTitle]

# Pre Middleware

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Back-End/RO/04-Mongoose-MongoDB/31-32-Mongoose-Middleware-and-Pre-Middleware-NEW-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

**Middleware** este o funcție care rulează în timpul executării funcțiilor asincrone.

Acestea sunt executate înainte sau după o anumită funcție pe care o specificăm.

**Pre Middleware** rulează înainte ca metoda conectată să fie executată.

Mai multe funcții middleware vor fi executate una după alta.

Le folosim atunci când:

- Trebuie să efectuăm o **validare complexă**

- Trebuie să **eliminăm** documentele dependente

- Când avem sarcini **asincrone** pe care o anumită acțiune **le declanșează**

Iată cum se adaugă o funcție Pre Middleware:

``` js
const schema = new Schema(..);
schema.pre('save', function() {
    return hashPassword()
        .then(() => validateData());
});
```
[/slide]


[slide hideTitle]

# Post Middleware

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Back-End/RO/04-Mongoose-MongoDB/33-Post-Middleware-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

**Post middleware** este executat odată ce toate  **pre hooks** și **metoda originală** au fost executate.

Funcțiile middleware rulează în următoarea ordine:

`pre-conectate -> metoda -> post-conectate`

Iată un exemplu de adăugare a funcțiilor Post middleware:

``` js
const schema = new Schema(..);

schema.post('save', function(doc) { 
  console.log('It has been saved', doc._id); 
}); 

schema.post('remove', function(doc) { 
  console.log('It has been removed', doc._id); 
});
```
[/slide]