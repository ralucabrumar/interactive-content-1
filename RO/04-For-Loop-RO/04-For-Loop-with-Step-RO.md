[slide hideTitle]
# Bucla For cu Pas

[video src="https://videos.softuni.org/hls/Java/Java-Programming-Basics/04-for-loops/RO/interactive-programming-basics-with-java-for-loops-19-20-for-loop-with-step-and-demo-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

În această secțiune vom acorda atenție unei părți particulare și foarte importante a buclei `for`, și anume **pasul**.

**Pasul** este acea **parte** a construcției buclei `for` care indică **cu cât** trebuie **să crească** sau **să scadă** valoarea **variabilei sale** principale .

Este declarat ultima în **structura** buclei for.

Cel mai adesea, avem **o dimensiune de** `1` și, în acest caz, în loc să scriem `i += 1` sau `i -= 1`, putem folosi pentru o sintaxă mai scurtă `i++`sau operatorii `i--`.

```java live
for (int i = 0; i < 10; i++) {
  System.out.println(i);
}
```

Dacă dorim ca pasul nostru să fie **diferit de 1**, atunci când **creștem**, vom folosi operatorul `i + =` + step size.

  Cu pasul 2, bucla ar arăta astfel:
```java live
for (int i = 0; i < 10; i += 2) {
  System.out.println(i);
}
```

S-ar putea să dorim să avem un **pas descrescător** - `i-=` + dimensiunea pasului.

În acest caz, ar trebui să fim atenți la condiția finală pentru a evita o **buclă infinită**.

```java live
for (int i = 10; i >= 1; i--) {
  System.out.println(i);
}
```
[/slide]

[slide hideTitle]
# Problemă cu Soluție: Numbers Ending with 7 

[video src="https://videos.softuni.org/hls/Java/Java-Programming-Basics/04-for-loops/RO/interactive-programming-basics-with-java-for-loops-21-problem-and-solution-numbers-ending-with-seven-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="Numbers Ending with 7" taskId="java-basics-for-loop-numbers-ending-with-7" executionType="tests-execution" executionStrategy="java-code" requiresInput]
[code-editor language=java]
```java
import java.util.Scanner;

public class Program {
   public static void main(String[] args) {
      // Scrieți codul dvs. aici
    }
}
```
[/code-editor]
[task-description]
## Descriere
Scrieți un program care:

* Citește un număr **n**
* Imprimă toate numerele de la **7 până la n**, **care se termină cu 7**

## Exemplu
|**Intrare**|**Ieșire** |
| --- | --- |
| 30 | 7 |
|  | 17 |
|  | 27 |

[/task-description]
[tests]
[test open]
[input]
30
[/input]
[output]
7
17
27
[/output]
[/test]
[test]
[input]
40
[/input]
[output]
7
17
27
37
[/output]
[/test]
[/tests]
[code-io/]
[/code-task]

[/slide]


[slide hideTitle]
# Problemă cu Soluție: Exam Countdown

[video src="https://videos.softuni.org/hls/Java/Java-Programming-Basics/04-for-loops/RO/interactive-programming-basics-with-java-for-loops-23-problem-and-solution-exam-countdown-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="Exam Countdown" taskId="java-basics-for-loop-exam-countdown" executionType="tests-execution" executionStrategy="java-code" requiresInput]
[code-editor language=java]
```java
import java.util.Scanner;

public class Program {
   public static void main(String[] args) {
      // Scrieți codul dvs. aici
    }
}
```
[/code-editor]
[task-description]
# Descriere
Scrieți un program care:

* Citește un număr întreg - numărul de **zile înainte de un examen**
* Pentru **fiecare zi** imprimă: "\{**currentDay**\} **days before the exam**"
* La final imprimă: **"The exam has come"**

## Exemplu
|**Intrare**| **Ieșire** |
| --- | --- |
| 3 | 3 days before the exam |
|  | 2 days before the exam |
|  | 1 days before the exam |
|  | The exam has come |
[/task-description]
[tests]
[test open]
[input]
3
[/input]
[output]
3 days before the exam
2 days before the exam
1 days before the exam
The exam has come
[/output]
[/test]
[test]
[input]
4
[/input]
[output]
4 days before the exam
3 days before the exam
2 days before the exam
1 days before the exam
The exam has come
[/output]
[/test]
[/tests]
[code-io/]
[/code-task]

[/slide]
