# Bucla de Eveniment

[slide hideTitle]
# Apeluri Inverse

**JavaScript** este executat de cele mai multe ori **în browser.**

**Bucla de eveniment** este un concept fundamental în **programarea asincronă** JavaScript.

**JavaScript** execută toate operațiile într-o singură secvență, dar folosește câteva structuri de date inteligente, creând iluzia de secvențe multiple.

JavaScript este un limbaj **bazat pe evenimente**. 

Acest lucru înseamnă că în loc să așteptăm un răspuns înainte de a merge mai departe, **JavaScript** va continua să execute în timp ce ascultă alte evenimente și de aceea avem nevoie de apeluri inverse (**callbacks**).

O funcție **de apel invers** este o funcție transmisă într-o altă funcție ca argument, care este invocată apoi în interiorul funcției externe pentru a completa un tip de **rutină** sau **acțiune**. 


[/slide]

[slide hideTitle]

# Execuția Stivei

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-5-10-stack-execution-of-the-event-loop-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

În acest exemplu, putem vedea cele două tipuri de memorie: **Stack (stivă)** și **Heap**.

**Heap** este locul în care obiectele sunt stocate atunci când definim variabile. 

**Stiva** reține doar apelurile funcției.

De fiecare dată când apelăm o nouă funcție, aceasta este adăugată în vârful stivei. 

În **stivă**, totul este **organizat în domenii**, deci fiecare funcție din stivă **are propriul domeniu.**

**Stiva de apeluri** este un mecanism JavaScript folosit pentru a ține socoteala funcțiilor. 

Atunci când apelăm o funcție, JavaScript va **adăuga** această funcție în **stiva de apeluri**. 
 
Dacă această funcție apelează o altă funcție, JavaScript va adăuga și această funcție la **stiva de apeluri**, deasupra primei funcții.

Acest proces se va repeta pentru fiecare funcție care va fi apelată de funcția anterioară. 

Când o funcție s-a terminat, JavaScript va **elimina** acea funcție din **stiva de apeluri**.

[/slide]

[slide hideTitle]
# Bucla de Eveniment

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Advanced/02.JS-Advanced-DOM-Manipulations/RO/JS-Advanced-DOM-Manipulations-3-4-event-loop-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

În acest exemplu, **avem o funcție** care invocă o altă funcție, dar de această dată funcția creează un **eveniment în coada de evenimente**.

Continuăm cu operațiile **sincrone** standard până când stiva se golește. 

La un moment dat, **evenimentul creează o funcție nouă** care este **o funcție de apel invers**. Aceasta merge în stivă, unde este executată. 

Aceasta este un **prezentare scurtă** a execuției asincronă a codului. 

[image assetsSrc="Dom-Manipulation(1).gif" /]

[/slide]
