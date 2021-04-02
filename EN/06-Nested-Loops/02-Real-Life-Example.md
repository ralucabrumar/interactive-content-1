// sectionId: "Javascript::Programming-Basics::Nested-Loops::Real-Life-Example"

[slide hideTitle]
# Real-Life Example: Clock

[video src="https://videos.softuni.org/hls/javascript-basics/06.Nested-Loops/EN/JS-basics-nested-loops-11-12-real-life-example-clock-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[image assetsSrc="06-nested-loops-clock-1159.png" /]

Imagine the current time is **11:00 AM.** 

The minutes on the clock will gradually increase by **1 until they reach 59.** 

Once they get to 60, the hours will be incremented by 1 and the minutes will reset back to 00. 

[image assetsSrc="06-nested-loops-clock-1200.png" /]

We can represent this process using **for-loops**.

More importantly, this is a good example of why we would even need more than one **for-loop** to complete any task. 

As you can see in the pseudocode example there are two loops: an inner and an outer one. 

The outer one represents the hours, while the inner one - the minutes. 

## Pseudocode

```
for h which is in the range from 0 to 23
    for m which is in the range from 0 to 59
        print h and m in a format similar to the clock
```
[/slide]