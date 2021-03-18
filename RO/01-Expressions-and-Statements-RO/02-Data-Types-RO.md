[slide hideTitle]
# Tipuri de date

[video src="https://videos.softuni.org/hls/Java/Java-Programming-Basics/01-expressions-and-statements/RO/interactive-programming-basics-with-java-expressions-and-statements-8-10-data-types-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

În Java putem folosi tipurile de date pentru a defini variabilele după cum urmează:

  * **Int** - un număr întreg: 1, 2, 3 
  * **Double** – numere zecimale: -0.5, 3.14
  * **Boolean** – valoare booleană : true, false
  * **Char** – simbol: 'a', 'b', '#'
  * **String** - text: "Hello", "World"

Odată ce o variabilă este definită, poate schimba valoarea sa de mai multe ori, dar nu poate schimba tipul de date mai târziu. 

Variabilele pot conține numai date de tipul lor. 

Mai jos putem declara variabile de diferite tipuri:
```java
int a = 5;
String text = "Some text";
char letter = 'A';
float f = 4.2;
```

Tipurile de date stabilesc intervale de valori cu caracteristici similare.

Sunt caracterizate prin:

  * **Nume** - E.g. boolean, int, String, DateTime
  * **Dimensiune** (mutilizarea memoriei) - Exemplu: 4 bytes
  * **Valoare implicită** - Exemplu: 0
[/slide]

[slide hideTitle]
# Convențiile de Denumire

În programarea, o convenție de denumire este un set de **reguli** pentru alegerea numelui care trebuie utilizat pentru variabile.

In Java pentru convențiile de denumire a variabilelor sunt utilizate **"camelCase"**. 

Există alte convenții de denumire care sunt folosite în diferite limbi, cum ar fi cazul pascal, cazul de șarpe.

**Camel case** combină cuvintele prin:
* Scrierea cu majuscule a tuturor cuvintelor care urmează primului cuvânt
* Eliminarea spațiului
```java
int userLoginCount;
```

**Pascal case** combină cuvintele prin:
* Scrierea cu majuscule a fiecărui cuvânt împreună cu primul
* Eliminarea spațiului:
```java
int UserLoginCount;
```

**Snake-case** este o altă convenție de denumire, care separă cuvintele cu:
* Un caracter de subliniere (_)
* Fara spații
* Litera inițială a fiecărui element de obicei cu litere mici în compus
* Prima literă mai mare sau mică
```java
int users_count;
String first_name;
```
[/slide]