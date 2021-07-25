# Proprietăți Interne ale Obiectelor

[slide hideTitle]

# Proprietăți Interne

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-27-28-internal-object-properties-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[image assetsSrc="function-context-06.png" /]

Toate proprietățile unui obiect au propriile lor proprietăți, și anume **Enumerable, Configurable, Writable** și **Value**.

Pentru **a lista proprietățile interne** ale oricărei proprietăți a unui obiect, utilizați `Object.getOwnPropertyDescriptor(yourObject, 'propertyName');`

```js
let person = {
    name: 'Billy',
    age: 50
}

const descriptor = Object.getOwnPropertyDescriptor(person, 'name');

console.log(descriptor);
```

**Ieșire**:
```js
{
  value: 'Billy',
  writable: true,
  enumerable: true,
  configurable: true
}
```

- **Enumerable**: Putem enumera proprietățile care sunt setate la **enumerable:true** cu bucla `for..in` sau le putem lista folosind metoda `Object.keys()`

- **Configurable**: folosit pentru a modifica comportamentul proprietății

   - Setarea **configurable: false** face ca proprietatea să nu poată fi ștearsă 

   - Numai proprietățile care sunt **configurable** pot fi șterse

- **Writable** - proprietățile marcate ca **writable:true** pot fi modificate și valorile lor pot fi actualizate prin simpla atribuire a unei noi valori pentru acestea

- **Value** - ne permite să modificăm valoarea proprietății chiar și atunci când aceasta este setată la **writable:false**, utlizând `Object.defineProperty()`

[/slide]

[slide hideTitle]
# Proprietăți Non-Enumerable

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-29-objects-non-enumerable-properties-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Rulați codul de mai jos:

```js live
let person = {
    name: 'Billy',
    age: 50
}

for (const property in person) {
    const item = `${property}: ${person[property]}`;
    console.log(item);
}
```

Rezultatul așteptat aici este:

```js
name: 'Billy'
age: 50
```

Notă: În locul utilizării unei **bucle for**, puteți afișa rezultatul cu `Object.keys(person)`, iar proprietățile vor fi returnate sub forma unei matrice.

```js
console.log(Object.keys(person));
//output -> [ 'name', 'age' ]
```

Putem modifica valoarea proprietăților interne cu ajutorul metodei `Object.defineProperty()`. 

Puteți modifica una sau chiar toate proprietățile interne simultan.

În acest exemplu, vom schimba valoarea proprietății **age** și vom seta **enumerable** la **false**.

```js
Object.defineProperty(object1, 'property1', {
    enumerable: false,
    writable: true
    //and so on
});
```

```js live
let person = {
    name: 'Billy',
    age: 50
}

Object.defineProperty(person, 'age',
    {
        enumerable: false
    });

for (const property in person) {
    const item = `${property}: ${person[property]}`;
    console.log(item);
}
```

Acum rezultatul așteptat este:

```js
name: Billy
```

Observați că vârsta nu mai este afișată pe consolă. Aceasta se află încă în interiorul obiectului, dar nu mai poate fi enumerată.

De asemenea, puteți încerca să enumerați proprietățile cu `Object.keys(person)`, dar singura proprietate vizibilă va fi **name**.

Nici imprimarea obiectului propriu-zis cu `console.log(person)` nu va avea ca rezultat imprimarea proprietații **age**.

**Proprietățile care nu sunt enumerabile** nu sunt serializate atunci când se utilizează `JSON.stringify()`.

[/slide]

[slide hideTitle]
# Proprietăți Non-Writable 

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-30-objects-non-writable-properties-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Valorile proprietăților **non-writable** nu pot fi modificate prin atribuire.

Folosind `Object.defineProperty` prin specificarea unei proprietăți care nu există în obiectul nostru, putem să adăugăm o proprietate complet nouă obiectului respectiv, să îi setăm valoarea și o putem face nemodificabilă (non-writable):

```js live
let object = {
    property: 2
};
Object.defineProperty(object, 'anotherProperty', {
    value: 2,
    writable: false
});

console.log('Original value:', object.anotherProperty);

object.anotherProperty = 1000;

console.log('New value:', object.anotherProperty);
```

Rezultatul așteptat:

```js
Original value: 2
New value: 2
```

Dacă modificați codul de mai sus și setați writable la **true**, așa cum este în mod implicit, atunci veți putea atribui valoarea **1000** pentru **anotherProperty**. 

Rezultatul ar fi:

```js
Original value: 2
New value: 1000
```

Dacă proprietatea **non-writable** conține un obiect, atunci referința obiectului nu va putea fi modificată, dar obiectul în sine poate fi modificat prin atribuirea unei noi valori.
[/slide]

[slide hideTitle]

# Proprietăți Non-Configurable

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-31-object-non-configurable-properties-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Dacă setați **configurable:false** pentru orice proprietate, veți putea modifica doar proprietatea **writable**, care este true, la false și nimic altceva.

Orice încercare de modificare a oricărei alte proprietăți interne **va eșua** și va genera un **TypeError**.

```js
let ob = {};
Object.defineProperty(ob, 'a', {
    configurable: false,
    writable: true
});
Object.defineProperty(ob, 'a', {
    enumerable: true
}); // generează TypeError
Object.defineProperty(ob, 'a', {
    value: 12
}); // generează TypeError
Object.defineProperty(ob, 'a', {
    writable: false
}); // acest lucru este permis
Object.defineProperty(ob, 'a', {
    writable: true
}); // generează TypeError
```
[/slide]

[slide hideTitle]

# Object Freeze și Seal

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-32-object-freeze-and-seal-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Sintaxă: `Object.freeze(obj)` și `Object.seal(obj)`

## Object Freeze

`Object.freeze()`- nu permite adăugarea de proprietăți noi obiectului și toate proprietățile vor fi **non-writable**.

Să vedem un exemplu:

```js live
const obj = {
    property1: 'something',
    property2: 654,
    property3: {
        innerProperty: 'can-change'
    }
};

const frozenObj = Object.freeze(obj);
frozenObj.property1 = 'trying to change it'; 
// TypeError
```

Toate proprietățile sunt schimbate în **non-writable**, deci nu puteți atribui o nouă valoare pentru **property1** și veți primi o **TypeError** dacă încercați.

Puteți modifica valoarea lui **innerProperty**, deoarece conține o referință la un obiect. 

Referința nu se modifică, dar i se poate atribui valoarea lui **innerProperty**.

```js
frozenObj.property3.innerProperty = 'something else';
```

Pentru a preveni acest lucru, puteți folosi **freeze** pentru proprietatea obiectului:

```js
Object.freeze(frozenObj.property3);

frozenObj.prop3.innerProperty = 'this will not work'; 
//Type Error
```

Puteți utiliza `Object.isFrozen(someObject)`. 

Dacă **someObject** este frozen, va returna **true**.

## Object Seal

`Object.seal()`- nu permite adăugarea de proprietăți noi obiectului și toate proprietățile acestuia devin **non-configurable**. 

Valorile proprietăților pot fi modificate.

```js live
const obj = {
    property1: 'something',
    property2: 654
};

Object.seal(obj);
obj.property1 = 'something else' // OK
delete obj.property1 // Nu face nimic. În plus: Eroare în modul strict;
console.log(obj);
```

`delete obj.property1` trebuia să elimine această proprietate din obiect, dar din moment ce este **sealed** nu va funcționa.

Puteți verifica dacă un obiect este sealed cu `Object.isFrozen(someObject)`.

## Concluzie

Atât **freeze**, cât și **seal** se ocupă de imuabilitatea obiectului.

Când folosiți `Object.freeze()`, noile valori nu pot fi atribuite proprietăților.

`Object.seal()` face astfel încât noile proprietăți să nu poată fi adăugate și proprietățile existente să nu poată fi eliminate, dar le puteți atribui noi valori.

În orice caz, dacă aveți o proprietate care conține un obiect, numai referința sa nu poate fi modificată, dar valoarea poate fi, chiar dacă este **non-writable**. 

Pentru a preveni acest lucru, putem, de asemenea să folosim **freeze** pentru proprietatea obiectului, iar atunci valoarea din interiorul acestuia nu va fi **writable**.

[/slide]

[slide hideTitle]

# Problemă cu Soluție: Person

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-34-solution-person-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="Person" taskId="js-advanced-function-context-Person" executionType="tests-execution" executionStrategy="javascript-unit-tests-with-mocha" requiresInput] [code-editor language=javascript]
```
class Person{
    // Scrieți codul dvs. aici
}

```
[/code-editor]
[task-description]
# Descriere
Scrieți o clasă care accepte **prenumele** și **numele** ca **parameteri** și returnează un obiect cu **firstName**, **lastName** și **fullName**: "\{**firstName**\} \{**lastName**\}". 

Toate proprietățile trebuie să fie **accesibile**. Am descoperit că "accesibil" înseamnă și "modificabil". 

Acest lucru înseamnă că:

- Dacă **firstName** sau **lastName** s-au schimbat, atunci **fullName** ar trebui de asemenea modificat

- Dacă **fullName** este modificat, atunci **firstName** și **lastName** ar trebui de asemenea schimbate

- Dacă **fullName** este **nevalid**, nu trebuie să modificați celelalte proprietăți

Un **nume complet** **valid** respectă formatul: "\{**firstName**\} \{**lastName**\}".

Notă: Consultați exemplele de mai jos pentru mai multe informații.

## Exemple

**Model de Intrare**

```js
let person = new Person('Peter', 'Smith');
console.log(person.fullName); // Peter Smith

person.firstName = 'George';
console.log(person.fullName); // George Smith

person.lastName = 'Peterson';
console.log(person.fullName); // George Peterson

person.fullName = 'Nikola Tesla';
console.log(person.firstName) // Nikola
console.log(person.lastName)  // Tesla

let person = new Person('Albert", "Simpson');
console.log(person.fullName); // Albert Simpson

person.firstName = 'Simon';
console.log(person.fullName); // Simon Simpson

person.fullName = 'Peter';
console.log(person.firstName) // Simon
console.log(person.lastName)
```

[/task-description]
[code-io /]
[tests]
[test]
[input]
let Person = result;
let a = new Person("Albert", "Simpson");
let actual = a.fullName;
let expected = "Albert Simpson";
assert.equal(actual,expected);
a.firstName = "Simon";
let actualFullName = a.fullName;
let expectedFullName = "Simon Simpson";
assert.equal(actualFullName,expectedFullName);
a.fullName = "Peter";
let b = a.firstName;
let expectedB = "Simon"
assert.equal(b,expectedB);
let v = a.lastName;
let expectedV = "Simpson";
assert.equal(v,expectedV);
[/input]
[output]
yes
[/output]
[/test]
[test]
[input]
let Person = result;
let person = new Person("Peter", "Ivanov");

let act1 = person.fullName;
let exp1 = "Peter Ivanov";
assert.equal(act1,exp1);

person.firstName = "George";
let act2 = person.fullName;
let exp2 = "George Ivanov";
assert.equal(act2,exp2);

person.lastName = "Peterson";
let act3 = person.fullName;
let exp3 = "George Peterson";
assert.equal(act3,exp3);

person.fullName = "Nikola Tesla";
let act4 = person.firstName;
let exp4 = "Nikola";
assert.equal(act4,exp4);

let act5 = person.lastName;
let exp5 = "Tesla";
assert.equal(act5,exp5);
[/input]
[output]
yes
[/output]
[/test]
[/tests]
[/code-task]
[/slide]
