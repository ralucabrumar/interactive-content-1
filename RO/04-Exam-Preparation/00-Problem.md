# Problema 1: Password Reset

[slide hideTitle]
# Password Reset

[video src="https://videos.softuni.org/hls/Java/Java-Fundamentals-Object-And-Classes/05.Java-Fundamentals-Exam-Preparation/RO/01-password-reset-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="Password Reset" taskId="java-fundamentals-part-2-exam-preparation-password-reset" executionType="tests-execution" executionStrategy="java-code" requiresInput]
[code-editor language=java]
```
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Scrieți codul dvs. aici
    }
}
```
[/code-editor]
[task-description]
## Descriere

Scrieți un program de resetare a parolei care efectuează o serie de comenzi pe un șir predefinit.

În primul rând, veți primi un șir.

Până la comanda "**Done**", veți primi șiruri cu comenzi împărțite de un singur spațiu.

Comenzile vor fi următoarele:

- **TakeOdd**
  * preia doar caracterele de la **indici impari** și **le concatenează** împreună pentru a obține **noua parolă brută** și apoi **o imprimă**
- "**Cut** \{**index**\} \{**length**\}"
  * obține șirul cu **lungimea dată** începând din **indexul dat** din parolă și elimină prima apariție a acesteia, apoi imprimă parola pe consolă
  * indicele și lungimea date vor fi **întotdeauna valabile**
- "**Substitute** \{**substring**\} \{**substitute**\}"
  * dacă parola brută conține șirul dat, înlocuiește toate aparițiile sale cu textul înlocuit dat și imprimă rezultatul
  * dacă nu, imprimă "**Nothing to replace!**"


## Intrare

  - Veți primi șiruri până când este dată comanda "**Done**"

## Ieșire

- După ce se primește comanda "**Done**", tipăriți:
  * **"Your password is:** \{**password**\}"

## Constrângeri

- Indexurile din comanda "**Cut** \{**index**\} \{**length**\}" vor fi întotdeauna valabile


## Exemplu

| **Intrare** | **Ieșire** |
| --- | --- |
| Siiceercaroetavm\!\:\?\:ahsott\.\:i\:nstupmomceqr | icecream\:\:hot\:\:summer |
| TakeOdd | icecream\:\:hot\:\:mer |
| Cut 15 3 | icecream\-hot\-mer |
| Substitute \:\: \- | Nothing to replace! |
| Substitute \| \^ | Your password is\: icecream\-hot\-mer |

## Comentarii

TakeOdd

- " Siiceercaroetavm\!\:\?\:ahsott\.\:i\:nstupmomceqr" \-\> "icecream\:\:hot\:\:summer"


- Luăm caracterele numai la indici impari 1, 3, 5 etc.

"Cut 15  3" \-\> "icecream\:\:hot\:\:summer" \-\> sum

- icecream\:\:hot\:\:mer

Decupăm un șir care începe de la indexul 15 cu o lungime de 3, îl scoatem din parola brută și îl imprimăm.

Apoi, pe o nouă linie imprimăm noua parolă brută rezultată.

"Substitute \:\: \-" \-\> "icecream\:\:hot\:\:summer" \-\> "icream\-hot\-summer"

- Înlocuim "\:\:" with "\-"

"Substitute \| \^" \-\> "Nothing to replace!" 

- "|" nu este găsit nicăieri în parola brută

- În cele din urmă, după ce primim comanda "**Done**", imprimăm parola rezultată în formatul corespunzător

| **Intrare** | **Ieșire** |
| --- | --- |
| up8rgoyg3r1atmlmpiunagt\!\-irs7\!1fgulnnnqy | programming\!is\!funny |
| TakeOdd | programming\!is\!fun |
| Cut 18 2 | programming\*\*\*is\*\*\*fun |
| Substitute \! \*\*\* | Nothing to replace! |
| Substitute \? \.\!\.| Your password is\: programming\*\*\*is\*\*\*fun |
| Done | | 


[/task-description]
[code-io /]
[tests]
[test open]
[input]
Siiceercaroetavm!:?:ahsott.:i:nstupmomceqr
TakeOdd
Cut 15 3
Substitute :: -
Substitute \| ^
Done
[/input]
[output]
icecream\:\:hot\:\:summer
icecream\:\:hot\:\:mer
icecream-hot-mer
Nothing to replace!
Your password is\: icecream-hot-mer
[/output]
[/test]
[test open]
[input]
up8rgoyg3r1atmlmpiunagt!-irs7!1fgulnnnqy
TakeOdd
Cut 18 2
Substitute ! \*\*\*
Substitute ? .!.
Done
[/input]
[output]
programming!is!funny
programming!is!fun
programming\*\*\*is\*\*\*fun
Nothing to replace!
Your password is: programming\*\*\*is\*\*\*fun
[/output]
[/test]
[test]
[input]
abcd
TakeOdd
Done
[/input]
[output]
bd
Your password is: bd
[/output]
[/test]
[test]
[input]
abcdefg
TakeOdd
Done
[/input]
[output]
bdf
Your password is: bdf
[/output]
[/test]
[test]
[input]
abcdefg
TakeOdd
Cut 0 2
Done
[/input]
[output]
bdf
f
Your password is: f
[/output]
[/test]
[test]
[input]
abcdefg
TakeOdd
Substitute b y
Done
[/input]
[output]
bdf
ydf
Your password is: ydf
[/output]
[/test]
[test]
[input]
abcdefg
TakeOdd
Substitute z y
Done
[/input]
[output]
bdf
Nothing to replace!
Your password is: bdf
[/output]
[/test]
[test]
[input]
abcdefg
Cut 0 3
Done
[/input]
[output]
defg
Your password is: defg
[/output]
[/test]
[test]
[input]
abcdefg
Cut 0 6
Done
[/input]
[output]
g
Your password is: g
[/output]
[/test]
[test]
[input]
abcdefg
Cut 3 1
Done
[/input]
[output]
abcefg
Your password is: abcefg
[/output]
[/test]
[test]
[input]
abcdefg
Cut 4 2
Done
[/input]
[output]
abcdg
Your password is: abcdg
[/output]
[/test]
[test]
[input]
AABBCCDDEEFFGG
TakeOdd
Cut 2 3
Substitute B A
Done
[/input]
[output]
ABCDEFG
ABFG
AAFG
Your password is: AAFG
[/output]
[/test]
[test]
[input]
AAABBBCCCDDDEEEFFFGGG
Cut 0 1
Cut 0 1
Cut 0 1
Cut 1 1
Cut 3 2
Substitute G Y
TakeOdd
Done
[/input]
[output]
AABBBCCCDDDEEEFFFGGG
ABBBCCCDDDEEEFFFGGG
BBBCCCDDDEEEFFFGGG
BBCCCDDDEEEFFFGGG
BBCDDDEEEFFFGGG
BBCDDDEEEFFFYYY
BDDEFFY
Your password is: BDDEFFY
[/output]
[/test]
[test]
[input]
AAABBBCCCDDD
Cut 2 3
Substitute C J
Substitute Z M
TakeOdd
Done
[/input]
[output]
AABCCCDDD
AABJJJDDD
Nothing to replace!
AJJD
Your password is: AJJD
[/output]
[/test]
[/tests]
[/code-task]
[/slide]