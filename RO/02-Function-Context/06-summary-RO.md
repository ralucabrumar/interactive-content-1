[slide hideTitle]

# Rezumat

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/03.JS-Advanced-Function-Context/RO/js-advanced-function-context-35-summary-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

## În această lecție ați învățat:

- **Context funcțional** - obiectul din care a provenit codul este contextul său implicit

- Ținta lui **this** depinde de **locația** și **modul** în care **este apelată** **funcția** executată

- Funcțiile **bind**, **apply** și **call** pot fi folosite pentru a seta în mod explicit valoarea lui **this**

- `call()` - schimbă contextul funcției la obiectul dat

```js
functionName.call(objectToBind, additionalArguments);
```

- `apply()`- similară lui **call()**, dar aceasta acceptă o listă de argumente, în timp ce **apply()** acceptă o matrice

```js
console.log(praise.apply(dog,
    ['A good boy', 'My best friend']
));
```

- `bind()` - creează o **funcție nouă** 

    - permite obiectelor să împrumute metode de la alte obiecte fără ca noi să facem manual copii ale acelei metode

- Proprietățile **interne** ale obiectelor care vă permit să modificați modul în care se vor comporta proprietățile obiectului:

   - **enumerable** 
   - **configurable**
   -  **writable**

- **Seal** și **freeze** tratează **imuabilitatea** obiectului


## În lecția următoare veți învăța:

- **Funcții avansate** - ce sunt funcțiile de primă clasă și cele de ordin superior

- Currying și aplicație parțială

- Expresii de funcții invocate imediat

- Closure

- Tratarea erorilor

[/slide]
