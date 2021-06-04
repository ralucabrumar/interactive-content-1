[slide hideTitle]

# Summary

[video src="https://videos.softuni.org/hls/Java/Java-OOP-Advanced/01-Encapsulation/EN/01.Java-OOP-Advanced-Encapsulation-34-summary-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

## In this lesson you learned:

- **Encapsulation**
    - is used to hide the implementation
    - it reduces complexity
    - it ensures that structural changes remain local

```java
  public String getName() {…}
  protected String getName () {…}
  private String name;
```

- **Mutable** and **Immutable** objects
    - mutable objects can be modified
    - immutable objects cannot be modified

```java
String firstName = "John";
String lastName = "Davis";
// Strings are immutable

String fullName = firstName.concat(" ").concat(lastName);
// Concatenating two strings returns a new one
```

- Keyword `final`
    - it prevents entities from being extended and overridden

```java
public final class Mammal extends Animal {}
```


## In the next lesson you will learn:

- What is inheritance 

- Class hierarchies

- How to access members of the base class

- Types of class reuse
    - extension
    - composition
    - delegation

[/slide]