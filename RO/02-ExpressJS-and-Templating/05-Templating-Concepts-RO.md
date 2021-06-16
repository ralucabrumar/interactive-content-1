# Concepte de Șablonare 

[slide hideTitle]

# Ce este Șablonarea?

**Șablonarea** este procesul de separare a **structurii unui document HTML** de conținutul **actual**.

**Șabloanele** permit **reproducerea conținutului similar** într-o pagină web, cum ar fi o listă de produse dintr-un magazin online, generând automat marcajul necesar.

Această **distincție** clară între **logică și date** face codul nostru mult **mai ușor de citit și de prelucrat**.

Aceasta introduce o modalitate mai **eficientă** de a construi interfețe utilizator și are ca rezultat **mai puțin cod inutil**.


[image assetsSrc="JS-Back-End-ExpressJs-and-Templating-1.png" /]




[/slide]

[slide hideTitle]

# Concepte de Șablonare

Părțile **statice** ale paginii noastre web sunt stocate sub formă de **șabloane**, în timp ce conținutul **dinamic**, cum ar fi datele entității, este stocat **separat**, cel mai adesea într-o bază de date.

Un **motor de șablonare** este utilizat pentru a le **combina pe cele două**.

Vom discuta despre motoarele de șablonare mai târziu în această lecție.

Acestea sunt principalele **concepte de șablonare**:

- Șabloanele sunt utilizate pentru a **defini structura** site-ului nostru web
    - izolarea **componentelor HTML** de conținutul **actual**

- Fiecare **sistem de șablonare** are **propria sa sintaxă**
    - în general foarte **ușor de învățat**
    - **diferențe minore de sintaxă** între **motoarele de șablonare**

- Fiecare șablon trebuie păstrat cât mai **simplu** posibil
    - **împărțiți în unități mai mici** ori de câte ori este posibil

[/slide]


[slide hideTitle]
# Exemple de Șablonare

Exemple de situații reale în care șablonarea va fi utilă sunt

- Afișarea articolelor într-un blog

- Afișarea unei galerii de fotografii

- Vizualizarea profilurilor utilizatorilor

- Afișarea articolelor dintr-un catalog

[image assetsSrc="JS-Back-End-ExpressJs-and-Templating-2.png" /]

[/slide]

[slide hideTitle]

# Motoare de Vizualizare Server

**Motoarele de vizualizare server** transformă datele în HTML **direct pe server**.

Acest lucru are ca rezultat **o securitate mai mare**, deoarece nu vă bazați pe client pentru a ignora datele pe care nu trebuie să le vadă.

Cu toate acestea, **Single Page Applications nu utilizează randarea de pe server** în majoritatea cazurilor.

Aceasta înseamnă că aplicațiile cu randare pe partea de server **nu sunt SPA-uri (Single Page Applications) reale**.

Multe motoare de șablonare acceptă Express:

- **express-handlebars**: Adaptare a motorului Handlebars, modificat pentru a funcționa mai bine cu Express.
  
- **Pug**: Haml\-motor șablon cu inspirație (anterior denumit Jade).
  
- **Express-views-dom**: un motor de vizualizare DOM pentru Express.

- **Rivets-server**: randează șabloanele [Rivets.js](http://rivetsjs.com) de pe server.

[/slide]