# Provlem 1: SoftUni Reception 

[slide hideTitle]

# SoftUni Reception 

[video src="https://videos.softuni.org/hls/Java/Java-Fundamentals-Methods-And-Arrays/05.Java-Fundamentals-Exam-Preparation/EN/Java-Fund-Exam-Prep-1-Softuni-Receptionist-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="SoftUni Reception" taskId="java-fund-18-Exam-Preparation-problem-1" executionType="tests-execution" executionStrategy="java-code" requiresInput]
[code-editor language=java]

```
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        // Write your code here
    }
}
```
[/code-editor]
[task-description]
# Description

There are **3 employees working** on the reception ат SoftUni full time.

Each of them can process a **different number of customer help requests and questions per hour**.

Your task is to **calculate how much time it will take them to answer a certain amount of questions** .

First, you will receive **3 lines with integers**, representing the **number of people that each of the employees can help per hour**. 

On the next line, you will receive **the total amount of people** as a single integer, each of them is cosidered as a separate request to be processed. 

**Every fourth hour, the employees will take a one-hour break** before they start working again. 

**Calculate the time needed to answer the questions** and **print the result in the following format**:

"**Time needed:** \{**time**\}**h.**"

## Input / Constraints

- On the first 3 lines -  each employee's **efficiency** - **integers**

- On the 4th line - the amount of people - an **integer**

## Output

- Print a **single line**: 

"**Time needed:** \{**time**\}**h.**"

## Example One
| **Input** | **Output** |
| --- | --- |
| 5 | Time needed: 2h. |
| 6 | |
| 4 | |
| 20 | |

## Comment

- All of the employees can answer the questions of 15 people per hour
- After the first hour, the questions of 5 people remain unanswered
- Everyone's questions will be answered within the second hour

## Example Two
| **Input** | **Output** |
| --- | --- |
| 1 | Time needed: 10h. |
| 2 | |
| 3 | |
|45 | |

## Comment

- All front desk workers combined can answer the questions of 6 people per hour
- In the first 3 hours, they have answered the questions of 18 people (6 \* 3)
- Then they take an hour break
- In the next 3 hours, they have serviced 36 people (18 + 6 \* 3)
- After their one-hour break, only 9 unanswered questions remain
- Everyone's questions will be answered on the 10th hour

## Example Three
| **Input** | **Output** |
| --- | --- |
| 3 | Time needed: 5h. |
| 2 | |
| 5 | |
| 40 | |

[/task-description]
[code-io /]
[tests]
[test open]
[input]
5
6
4
20
[/input]
[output]
Time needed\: 2h\.
[/output]
[/test]
[test open]
[input]
1
2
3
45
[/input]
[output]
Time needed\: 10h\.
[/output]
[/test]
[test open]
[input]
3
2
5
40
[/input]
[output]
Time needed\: 5h\.
[/output]
[/test]
[test]
[input]
1
2
3
45
[/input]
[output]
Time needed\: 10h\.
[/output]
[/test]
[test]
[input]
1
2
3
100
[/input]
[output]
Time needed\: 22h\.
[/output]
[/test]
[test]
[input]
20
40
40
900
[/input]
[output]
Time needed\: 11h\.
[/output]
[/test]
[test]
[input]
3
2
5
40
[/input]
[output]
Time needed\: 5h\.
[/output]
[/test]
[test]
[input]
1
1
1
4519
[/input]
[output]
Time needed\: 2009h\.
[/output]
[/test]
[test]
[input]
1
1
1
30
[/input]
[output]
Time needed\: 13h\.
[/output]
[/test]
[test]
[input]
2
4
4
70
[/input]
[output]
Time needed\: 9h\.
[/output]
[/test]
[test]
[input]
2
4
4
500
[/input]
[output]
Time needed\: 66h\.
[/output]
[/test]
[test]
[input]
3
3
3
27
[/input]
[output]
Time needed\: 3h\.
[/output]
[/test]
[test]
[input]
3
3
3
0
[/input]
[output]
Time needed\: 0h\.
[/output]
[/test]
[/tests]
[/code-task]
[/slide]