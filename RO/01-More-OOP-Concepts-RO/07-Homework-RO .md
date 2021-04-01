# Teme Pentru Acasă

[slide hideTitle]
# Problem: Card Suit
[code-task title="Card Suit" taskId="oop-basics-java-more-oop-concepts-Card-Suit" executionType="tests-execution" executionStrategy="java-zip-file-code" requiresInput]

[task-description]
## Descriere

Creați un **tip de enumerare** care să aibă ca constante **cele patru costume** ale unui pachet de cărți de joc (CLUBURI, DIAMANTE, INIMI, SPADE).

Repetați valorile tipului de enumerare și imprimați toate **valorile ordinale** și **numele**.

## Trimitere

Submit `.zip`

## Exemplu
| **Intrare**|**Ieșire**|
| --- | --- |
| Card Suits | Card Suits: |
|  | Ordinal value: 0; Name value: CLUBS |
|  | Ordinal value: 1; Name value: DIAMONDS |
|  | Ordinal value: 2; Name value: HEARTS |
|  | Ordinal value: 3; Name value: SPADES |

[/task-description]
[code-upload allowedMemory="30" /]
[tests]
[test open]
[input]
Card Suits
[/input]
[output]
Card Suits:
Ordinal value: 0; Name value: CLUBS
Ordinal value: 1; Name value: DIAMONDS
Ordinal value: 2; Name value: HEARTS
Ordinal value: 3; Name value: SPADES
[/output]
[/test]
[test]
[input]
Card Suits
[/input]
[output]
Card Suits:
Ordinal value: 0; Name value: CLUBS
Ordinal value: 1; Name value: DIAMONDS
Ordinal value: 2; Name value: HEARTS
Ordinal value: 3; Name value: SPADES
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]
# Problem: Card Rank
[code-task title="Card Rank" taskId="oop-basics-java-more-oop-concepts-Card-Rank" executionType="tests-execution" executionStrategy="java-zip-file-code" requiresInput]

[task-description]
## Descriere

Creați un **tip de enumerare** care să aibă ca constante **cele paisprezece rânduri** ale unui pachet de cărți de joc  (ACE, TWO, THREE, FOUR, FIVE, SIX, SEVEN, EIGHT, NINE, TEN, JACK, QUEEN, KING).

Repetați valorile tipului de enumerare și imprimați toate valorile ordinale și numele.

## Trimitere
Submit `.zip`

## Exemplu
| **Intrare**|**Ieșire**|
| --- | --- |
| Card Ranks | Card Ranks: |
|  | Ordinal value: 0; Name value: ACE |
|  | Ordinal value: 1; Name value: TWO |
|  | Ordinal value: 2; Name value: THREE |
|  | Ordinal value: 3; Name value: FOUR |
|  | Ordinal value: 4; Name value: FIVE |
|  | Ordinal value: 5; Name value: SIX |
|  | Ordinal value: 6; Name value: SEVEN |
|  | Ordinal value: 7; Name value: EIGHT |
|  | Ordinal value: 8; Name value: NINE |
|  | Ordinal value: 9; Name value: TEN |
|  | Ordinal value: 10; Name value: JACK |
|  | Ordinal value: 11; Name value: QUEEN |
|  | Ordinal value: 12; Name value: KING |

[/task-description]
[code-upload allowedMemory="30" /]
[tests]
[test]
[input]
Card Ranks
[/input]
[output]
Card Ranks:
Ordinal value: 0; Name value: ACE
Ordinal value: 1; Name value: TWO
Ordinal value: 2; Name value: THREE
Ordinal value: 3; Name value: FOUR
Ordinal value: 4; Name value: FIVE
Ordinal value: 5; Name value: SIX
Ordinal value: 6; Name value: SEVEN
Ordinal value: 7; Name value: EIGHT
Ordinal value: 8; Name value: NINE
Ordinal value: 9; Name value: TEN
Ordinal value: 10; Name value: JACK
Ordinal value: 11; Name value: QUEEN
Ordinal value: 12; Name value: KING
[/output]
[/test]
[test]
[input]
Card Ranks
[/input]
[output]
Card Ranks:
Ordinal value: 0; Name value: ACE
Ordinal value: 1; Name value: TWO
Ordinal value: 2; Name value: THREE
Ordinal value: 3; Name value: FOUR
Ordinal value: 4; Name value: FIVE
Ordinal value: 5; Name value: SIX
Ordinal value: 6; Name value: SEVEN
Ordinal value: 7; Name value: EIGHT
Ordinal value: 8; Name value: NINE
Ordinal value: 9; Name value: TEN
Ordinal value: 10; Name value: JACK
Ordinal value: 11; Name value: QUEEN
Ordinal value: 12; Name value: KING
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]
# Problem: Cards with Power

[code-task title="Cards with Power" taskId="oop-basics-java-more-oop-concepts-Cards-with-Power" executionType="tests-execution" executionStrategy="java-zip-file-code" requiresInput]

[task-description]
## Descriere

Creați un program care generează un **pachet de cărți** **(class Card)** care au putere. Puterea unei cărți este calculată prin **adăugarea** puterii rangului său la puterea costumului său.

**Puterile de rang** sunt după cum urmează: (ACE - 14, TWO - 2, THREE - 3, FOUR - 4, FIVE - 5, SIX - 6, SEVEN - 7, EIGHT - 8, NINE - 9, TEN - 10, JACK - 11, QUEEN - 12, KING - 13).

**Puterile costumului** sunt după cum urmează: (CLUBS - 0, DIAMONDS - 13, HEARTS - 26, SPADES - 39).

## Intrare
Veți primi o comandă formată din **două** linii. 

Pe **prima** linie veți primi Rangul cărții și pe **a doua** linie veți obține costumul cărții.

## Ieșire
Imprimați rezultatul în format: **"Card name: ACE of SPADES; Card power: 53".**

## Notă

Încercați să utilizați tipurile de enumerare pe care le-ați creat în problemele anterioare, dar extindeți-le cu constructori și metode. Încercați să utilizați `Enum.valueOf()`.

## Trimitere
Submit `.zip`


## Exemplu
| **Intrare**|**Ieșire**|
| --- | --- |
| TWO | Card name: TWO of CLUBS; Card power: 2 |
| CLUBS |  |


| **Intrare**|**Ieșire**|
| --- | --- |
| ACE | Card name: ACE of SPADES; Card power: 53 |
| SPADES |  |

[/task-description]
[code-upload allowedMemory="30" /]
[tests]
[test open]
[input]
TWO
CLUBS
[/input]
[output]
Card name: TWO of CLUBS; Card power: 2
[/output]
[/test]
[test open]
[input]
ACE
SPADES
[/input]
[output]
Card name: ACE of SPADES; Card power: 53
[/output]
[/test]
[test]
[input]
ACE
CLUBS
[/input]
[output]
Card name: ACE of CLUBS; Card power: 14
[/output]
[/test]
[test]
[input]
KING
CLUBS
[/input]
[output]
Card name: KING of CLUBS; Card power: 13
[/output]
[/test]
[test]
[input]
TEN
HEARTS
[/input]
[output]
Card name: TEN of HEARTS; Card power: 36
[/output]
[/test]
[test]
[input]
TWO
DIAMONDS
[/input]
[output]
Card name: TWO of DIAMONDS; Card power: 15
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]
# Problem: Traffic Lights
[code-task title="Traffic Lights" taskId="oop-basics-java-more-oop-concepts-Traffic-Lights" executionType="tests-execution" executionStrategy="java-zip-file-code" requiresInput]

[task-description]
## Descriere

Implementați o mașină de stare simplă sub forma unui semafor.

Fiecare semafor are **trei** semnale posibile - **roșu**, **verde** și **galben**.

Fiecare semafor poate fi **actualizat**, ceea ce schimbă culoarea semnalului său (de exemplu, dacă este roșu în prezent, se schimbă în verde, dacă este verde se schimbă în galben).

Ordinea semnalelor este: **red -> green -> yellow -> red** și așa mai departe.

## Intrare

Pe prima linie vi se vor da mai multe semnale de semafoare **în formatul "RED GREEN YELLOW"**. 

Acestea pot fi de 3, **mai mult** sau **mai puțin** decât 3.

Trebuie să faceți cât mai multe semafoare pe cât sunt semnale în intrare.

Pe a doua linie, veți primi **n** - de câte ori trebuie să modificați semnalul fiecărui semafor.

## Ieșire

Rezultatul dvs. trebuie să fie format din **n** - numărul de linii, care includ **fiecare** semnal actualizat al semaforului.

Pentru a înțelege mai bine problema, vedeți exemplul de mai jos.

## Trimitere
Sumbit `.zip`

## Exemplu
| **Intrare** | **Ieșire** |
| --- | --- |
| GREEN RED YELLOW | YELLOW GREEN RED |
| 4 | RED YELLOW GREEN |
|  | GREEN RED YELLOW |
|  | YELLOW GREEN RED |

[/task-description]
[code-upload allowedMemory="30" /]
[tests]
[test open]
[input]
GREEN RED YELLOW
4
[/input]
[output]
YELLOW GREEN RED
RED YELLOW GREEN
GREEN RED YELLOW
YELLOW GREEN RED
[/output]
[/test]
[test open]
[input]
RED RED RED RED
10
[/input]
[output]
GREEN GREEN GREEN GREEN
YELLOW YELLOW YELLOW YELLOW
RED RED RED RED
GREEN GREEN GREEN GREEN
YELLOW YELLOW YELLOW YELLOW
RED RED RED RED
GREEN GREEN GREEN GREEN
YELLOW YELLOW YELLOW YELLOW
RED RED RED RED
GREEN GREEN GREEN GREEN
[/output]
[/test]
[test]
[input]
GREEN RED
3
[/input]
[output]
YELLOW GREEN
RED YELLOW
GREEN RED
[/output]
[/test]
[test]
[input]
RED RED RED GREEN GREEN GREEN
6
[/input]
[output]
GREEN GREEN GREEN YELLOW YELLOW YELLOW
YELLOW YELLOW YELLOW RED RED RED
RED RED RED GREEN GREEN GREEN
GREEN GREEN GREEN YELLOW YELLOW YELLOW
YELLOW YELLOW YELLOW RED RED RED
RED RED RED GREEN GREEN GREEN
[/output]
[/test]
[test]
[input]
GREEN
99
[/input]
[output]
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
YELLOW
RED
GREEN
[/output]
[/test]
[test]
[input]
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
199
[/input]
[output]
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN
RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW
GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED GREEN YELLOW RED
[/output]
[/test]
[/tests]
[/code-task]
[/slide]