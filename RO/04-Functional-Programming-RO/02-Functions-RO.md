# Funcții

[slide hideTitle]

# Programare Funcțională

Să continuăm cu o altă **paradigmă importantă** în programarea modernă: **programare funcțională**

**Programarea funcțională** (FP) este programarea bazată pe compunerea **funcțiilor pure**, evitând în același timp starea partajată, datele modificabile și efectele secundare.

Programele funcționale sunt **secvențe de transformări** ale datelor prin funcții.

Aceasta se numește abordare de programare **declarativă** (nu **imperativă**),
ceea ce înseamnă că în loc să fie descris un algoritm dezvoltatorii funcționali descriu rezultatul prin **funcții și compoziții de funcții**.

## Funcții Pure

Ce este o **funcție pură**?

- Este o funcție, care returnează o valoare **determinată numai de intrarea sa**, fără **efecte secundare**.

- Imprimarea codului la consola sau stocarea datelor într-o bază de date sunt exemple de efecte secundare

- Prin urmare, utilizarea **programării funcționale pure** este adesea **nepractică**.

- Limbile moderne folosesc **elemente de programare de stil funcțional** și nu sunt pur funcționale.

Exemple de **funcții pure** sunt:

## `f(x) = √x` 
- Funcția rădăcină pătrată: **"sqrt of x"**, care ia un număr la intrare și returnează un alt număr la ieșire.

- Funcția **"sortare listă"**, care ia o listă la intrare și returnează o listă nouă la ieșire.

Ambele funcții nu au **efecte secundare**:
- Nu schimbă nimic
- Nu citesc și nu scriu date externe
- Nu folosesc nicio stare

[/slide]

[slide hideTitle]

# Limbaje Funcționale de Programare

Există multe limbaje **de programare funcțională** și limbaje care integrează **paradigme funcționale** în dezvoltarea software-ului modern.

**Limbajele pur funcționale** sunt **nepracticabile** și rar folosite, deoarece programarea este mai complicată atunci când nu se menține o stare.

Dezvoltatorii pur funcționali trebuie să **își schimbe stilul de gândire** de la **gândirea algoritmică** tradițională la **gândirea funcțională**. 

- Programul în limbajele pur funcționale este o **funcție pură** (care solicită alte funcții pure), fără efecte secundare

**Limbajele funcționale impure** sunt utilizate mai des deoarece permit excepții de la conceptul de "funcții pure" și simplifică activitatea dezvoltatorilor.

- -Aceste limbaje subliniază **stilul funcțional**, dar uneori **permit efecte secundare**

-  Un exemplu de limbaj funcțional impur este **Clojure**

- Nu este foarte popular în dezvoltarea practică de software

**Limbajele multi-paradigme** combină punctele forte atât ale lumii **funcționale**, cât și ale celei **algoritmice** (sau **imperative**).

- Majoritatea limbajelor de programare de sens general utilizate astăzi sunt **multi-paradigme**

- Combină mai multe paradigme de programare:

- **Funcțională**,  **declarativă**,  **imperativă**, **pe bază de componente**, **pe baza de obiecte**, **determinată de un eveniment**, **programare asincronă**, și multe altele.



**Exemple** de limbaje populare de programare multi-paradigme de uz general sunt:

- JavaScript, C#, Python, Java, PHP, C++, Go, Swift și TypeScript.

Toate aceste limbaje combină mai multe concepte și paradigme pentru structurarea programului pentru a simplifica munca dezvoltatorilor și a le îmbunătăți **eficiența** și **performanța**.



[/slide]

[slide hideTitle]

# Funcții Java

În Java, putem crea funcții analogice cu funcțiile matematice.

## `ƒ(x) = x²`

``` java
Function<Integer, Integer> func = x -> x * x;
``` 

In this example, we have all needed **components** for a Java Function:
- Function **type**
- **Parameters**
- **Name** of the function 
- **Return expression**

[/slide]

[slide hideTitle]

# Function Interface

În Java `Function<T,R>` este o **interfață** care reprezintă o operație menită să accepte un argument și să returneze un rezultat adecvat.

``` java
int increment (int number) {
    return number + 1;
}
```

Putem folosi funcția cu `.apply()`


``` java
Function <Integer, Integer> increment = number -> number + 1;

int a = increment.apply(5);
int b = increment.apply(a);

```


[/slide]

[slide hideTitle]
# Problemă cu Soluție: Sum Numbers

[code-task title="Sum Numbers" taskId="oop-basics-java-functional-programming-lab-Sum-Numbers" executionType="tests-execution" executionStrategy="java-code" requiresInput]
[code-editor language=java]
```
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Arrays;
import java.util.function.ToIntFunction;

public class Main {
    public static void main(String[] args) {
        // Scrieți codul dvs. aici
    }
}
```
[/code-editor]
[task-description]
## Descriere
Scrieți un program care citește un rând de **Numere întregi** separate prin **", "**. 

Imprimați **cantintatea** numerelor și **suma** lor.

- Utilizați `Function<String, Integer>` pentru **analizarea** numerelor întregi după ce le împărțit într-o matrice **String**

# Exemple

## Example 1
| **Intrare**|**Ieșire**|
| --- | --- |
| 4, 2, 1, 3, 5, 7, 1, 4, 2, 12 | Count = 10
|  | Sum = 41 |

## Example 2
| **Intrare**|**Ieșire**|
| --- | --- |
| 2, 4, 6 | Count = 3 |
|  | Sum = 12 |


[/task-description]
[code-io /]
[tests]
[test open]
[input]
4, 2, 1, 3, 5, 7, 1, 4, 2, 12
[/input]
[output]
Count = 10
Sum = 41
[/output]
[/test]
[test open]
[input]
2, 4, 6
[/input]
[output]
Count = 3
Sum = 12
[/output]
[/test]
[test]
[input]
84, 31, 31, 54, 38, 50, 6, 34, 63, 50, 3, 61, 51, 61, 5, 79, 60, 79, 51, 34
[/input]
[output]
Count = 20
Sum = 925
[/output]
[/test]
[test]
[input]
87
[/input]
[output]
Count = 1
Sum = 87
[/output]
[/test]
[test]
[input]
85, 47, 91, 32, 83, 75, 81, 25, 31, 72
[/input]
[output]
Count = 10
Sum = 622
[/output]
[/test]
[test]
[input]
93, 26, 52, 9, 69, 31, 72, 13, 58, 10
[/input]
[output]
Count = 10
Sum = 433
[/output]
[/test]
[test]
[input]
77, 32, 36, 3, 33, 19, 90, 14, 5, 4, 44, 71, 5, 69, 67, 15, 2, 52, 59, 3, 12, 88, 66, 50, 91, 31, 84, 11, 43, 73, 95, 98, 17, 23, 93, 47, 68, 10, 84, 94, 63, 97, 74, 52, 69, 81, 61, 68, 15, 6, 68, 22, 52, 45, 29, 96, 70, 16, 27, 20, 85, 25, 27, 37, 32, 70, 16, 25, 73, 17, 11, 87, 81, 18, 42, 76, 28, 69, 13, 46, 42, 87, 23, 5, 25, 43, 6, 99, 3, 22, 89, 85, 49, 12, 14, 80, 63, 58, 85, 40, 74, 41, 57, 20, 31, 19, 44, 19, 71, 7, 91, 73, 53, 25, 33, 7, 97, 63, 29, 11, 51, 54, 61, 56, 44, 67, 14, 8, 9, 83, 25, 30, 2, 36, 50, 24, 74, 10, 47, 29, 76, 48, 6, 91, 98, 53, 16, 56, 44, 54, 97, 66, 63, 3, 70, 40, 27, 7, 11, 82, 8, 72, 87, 36, 65, 19, 76, 32, 85, 17, 78, 48, 6, 85, 31, 46, 78, 74, 7, 62, 5, 85, 22, 3, 50, 59, 52, 17, 39, 64, 84, 98, 32, 54, 59, 94, 64, 86, 68, 81, 82, 43, 48, 47, 38, 79, 65, 39, 37, 52, 54, 41, 48, 7, 47, 65, 88, 28, 50, 69, 73, 11, 45, 67, 98, 79, 95, 36, 95, 99, 17, 51, 4, 54, 34, 52, 43, 68, 68, 48, 60, 6, 59, 71, 55, 28, 53, 44, 73, 3, 45, 57, 95, 63, 12, 60, 42, 63, 31, 91, 51, 14, 99, 37, 80, 21, 50, 7, 54, 10, 35, 87, 9, 75, 78, 54, 41, 36, 76, 40, 96, 88, 22, 80, 30, 55, 36, 15, 30, 85, 5, 28, 51, 52, 7, 94, 40, 99, 62, 80, 31, 49, 7, 87, 38, 23, 18, 62, 95, 10, 30, 77, 99, 66, 20, 78, 8, 46, 72, 79, 6, 33, 93, 95, 67, 34, 9, 96, 97, 91, 58, 37, 27, 73, 56, 37, 56, 57, 79, 9, 6, 63, 52, 96, 59, 25, 10, 11, 18, 54, 88, 39, 71, 36, 22, 49, 66, 32, 50, 21, 20, 33, 32, 26, 76, 47, 44, 98, 25, 52, 86, 44, 72, 35, 74, 15, 49, 21, 45, 99, 42, 19, 15, 15, 82, 82, 90, 17, 41, 85, 62, 81, 9, 62, 61, 53, 21, 64, 88, 8, 60, 54, 72, 85, 40, 10, 73, 40, 73, 71, 97, 58, 7, 48, 33, 18, 39, 24, 77, 32, 26, 32, 10, 5, 85, 55, 41, 19, 36, 38, 47, 29, 70, 27, 90, 17, 82, 78, 17, 27, 86, 80, 85, 11, 48, 93, 97, 68, 27, 44, 76, 3, 80, 89, 91, 4, 9, 39, 83, 76, 91, 62, 42, 72, 88, 53, 2, 20, 2, 83, 76, 43, 82, 22, 22, 94, 35, 2, 99, 38, 55, 6, 91, 36, 95, 91, 83, 89, 97, 4, 76, 13, 23, 97, 69, 38, 95, 50, 95, 11, 88, 24, 20, 26, 51, 64, 33, 7, 39, 26, 25, 54, 30, 85, 12, 26, 12, 32, 74, 14, 17, 76, 35, 93, 42, 88, 5, 75, 51, 42, 4, 46, 52, 98, 58, 29, 30, 63, 45, 97, 63, 14, 74, 21, 44, 19, 6, 62, 8, 48, 72, 19, 61, 89, 39, 56, 71, 65, 87, 41, 44, 13, 68, 20, 5, 19, 40, 32, 90, 68, 72, 63, 23, 3, 95, 33, 20, 32, 28, 32, 97, 25, 11, 93, 90, 49, 26, 28, 36, 19, 29, 68, 53, 99, 19, 20, 15, 28, 31, 15, 20, 59, 41, 66, 90, 89, 23, 72, 42, 39, 56, 85, 27, 22, 80, 25, 24, 73, 37, 71, 22, 68, 84, 70, 72, 53, 29, 87, 4, 26, 73, 20, 48, 48, 25, 64, 9, 93, 6, 99, 22, 80, 48, 68, 27, 8, 53, 63, 61, 50, 89, 55, 22, 60, 92, 85, 52, 96, 17, 75, 58, 78, 18, 40, 95, 89, 43, 75, 67, 17, 29, 23, 49, 30, 44, 31, 95, 49, 21, 67, 32, 50, 12, 64, 52, 25, 33, 48, 16, 61, 98, 46, 47, 6, 62, 36, 84, 62, 51, 14, 79, 51, 45, 97, 61, 80, 37, 70, 98, 88, 21, 15, 29, 79, 14, 63, 16, 44, 13, 96, 42, 22, 83, 16, 73, 43, 29, 75, 33, 3, 13, 77, 74, 20, 7, 49, 95, 2, 56, 94, 44, 20, 31, 50, 54, 10, 36, 52, 9, 92, 14, 93, 49, 26, 26, 32, 77, 84, 2, 27, 50, 62, 83, 33, 8, 44, 33, 26, 35, 10, 86, 57, 49, 10, 82, 65, 71, 98, 35, 63, 92, 32, 16, 83, 5, 47, 5, 5, 23, 6, 6, 27, 83, 28, 59, 39, 7, 74, 29, 76, 28, 4, 94, 99, 32, 3, 33, 89, 72, 65, 32, 9, 20, 32, 62, 43, 82, 36, 99, 24, 24, 42, 34, 81, 63, 57, 15, 86, 25, 30, 34, 32, 64, 78, 71, 19, 55, 50, 30, 65, 55, 16, 29, 16, 29, 46, 17, 28, 14, 37, 63, 99, 63, 81, 49, 50, 98, 79, 76, 61, 88, 49, 49, 33, 81, 90, 74, 41, 4, 76, 69, 62, 39, 82, 18, 15, 2, 2, 7, 72, 92, 55, 66, 96, 8, 9, 57, 79, 84, 24, 69, 88, 91, 27, 48, 5, 68, 95, 39, 72, 57, 52, 31, 79, 90, 97, 52, 32, 4, 31, 27, 30, 52, 5, 63, 14, 53, 38, 98, 8, 3, 29, 43, 38, 4, 46, 85, 92, 16, 23, 46, 38, 84, 16, 38, 36, 7, 96, 39, 31, 7, 30, 94, 92, 67, 78, 20, 53, 84, 17, 81, 6, 57, 51, 7, 57, 83, 87, 56, 24, 50, 43, 52, 12, 94, 5, 8, 64, 69, 49, 77, 54, 11, 27, 71, 28, 73, 29, 43, 74, 64, 32, 60, 18, 69, 21, 19, 23, 35, 58, 81, 64, 39, 86, 44, 29, 75, 6, 57, 66
[/input]
[output]
Count = 1000
Sum = 48660
[/output]
[/test]
[test]
[input]
3, 5, 2
[/input]
[output]
Count = 3
Sum = 10
[/output]
[/test]
[/tests]
[/code-task]
[/slide]