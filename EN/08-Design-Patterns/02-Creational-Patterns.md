# Creational Patterns

[slide hideTitle]

# Purposes

[video src="https://videos.softuni.org/hls/Java/Java-OOP-Advanced/09-Design-Pattern/EN/Java-OOP-Advanced-Design-Patterns-12-13-creational-patterns-purposes-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Creational patterns are **object creational design patterns**.

We use these patterns when we need to decide in what way to create an object of a class.

They comprise of **two main concepts**:

- **Encapsulating** knowledge about which classes the system uses

- **Hiding** how instances of these classes are created

[/slide]

[slide hideTitle]

# The Singleton Pattern

[video src="https://videos.softuni.org/hls/Java/Java-OOP-Advanced/09-Design-Pattern/EN/Java-OOP-Advanced-Design-Patterns-14-15-singleton-pattern-example-and-demo-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

The singleton pattern is one of the most used creational design patterns.

Its main concept is the singleton class - a class that has only one object at a time.

The difference between a normal class and a singleton class is that we use a constructor to initialize the normal class, whereas, for a singleton class, we use the `getInstance()` method.

## Example

Let us create a singleton class:

``` java
public class Singleton {

    // First, we create an object of Singleton
    private static Singleton instance = new Singleton();

    // Then, we make the constructor private
    // This way the class cannot be instantiated
    private Singleton(){}

    // With the getInstance() method we get the only object available
    public static Singleton getInstance() {
        return instance;
    }

    public void printMessage() {
        System.out.println("Hello, I am a singleton class!");
    }
}
```

The `Main` class of this program:

``` java
public class Main {
    public static void main(String[] args) {

    	// Trying to create a singleton object via the constructor results in an error:
	// Compile Time Error: The constructor SingleObject() is not visible
	// Singleton object = new Singleton();

        // Get the only object available
        Singleton object = Singleton.getInstance();

        // Print the message
        object.printMessage();
    }
}
```

The **output** will be:

```
Hello, I am a singleton class!
```

This way, our Singleton class provides a method to get its **static** instance to the **outside world**.


[/slide]

[slide hideTitle]

# The Prototype Pattern

[video src="https://videos.softuni.org/hls/Java/Java-OOP-Advanced/09-Design-Pattern/EN/Java-OOP-Advanced-Design-Patterns-16-17-18-prototype-pattern-demo-new-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

The **prototype pattern** allows us to copy the class instance and create a new object from it.

This method of creating objects allows us to hide the complexity of making new instances from the client.

The copied object acts as a **prototype** and contains all the information of the **actual object**.

Instead of using the `new` keyword, we can use the `clone()` method.

We can add or remove objects at runtime using the prototype pattern.

[image assetsSrc="Design-Patterns.png" /]

**Example**:

``` java
public abstract class Prototype {
    private String id;
    
    // This is our Prototype Class
    public Prototype(String id) {
        this.id = id; 
    }

    public String getId() { 
        return this.id; 
    }
    public abstract Prototype clone();
}
```


``` java
class ConcretePrototype extends Prototype {
    public ConcretePrototype(String id) {
        super(id);
    }
    
    @Override
    public Prototype clone() {
        return (Prototype)this.clone(); 
    }
}
```

We can use the **prototype design pattern** when:

- We need to instantiate classes at runtime

- It is complicated or resource-heavy to create new classes

- Our clients do not need to know of the object's creation and representation procedures

[/slide]

[slide hideTitle]

# The Builder Pattern

[video src="https://videos.softuni.org/hls/Java/Java-OOP-Advanced/09-Design-Pattern/EN/Java-OOP-Advanced-Design-Patterns-19-builder-pattern-demo-new-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

The **builder design pattern** is used to assemble a complex structure step by step.

In the end, it will return an entire object. 

We can create an object with many possible configuration options.

**Usage** of the builder pattern:

- When our construction process must allow different representations for the constructed object (highly customizable)

- When we want our object creating algorithm to be independent of the parts that make up our object and the process of their construction

Example:

We want to create a character in our MMORPG game. 

We can make the constructor **instantiate a character** for us.

Code representation:

``` java
// This is our Hero class
public final class Hero {
    private final Race race;
    private final String name;
    private Integer startingHP;
    private final HairColor hairColor;
    private final Armor armor;
    private final Weapon weapon;

 Hero(
     Race race, 
     String name, 
     Integer startingHP, 
     HairColor hairColor, 
     Armor armor, 
     Weapon weapon
     ) {
    this.race = race;
    this.name = name;
    this.startingHP = startingHP;
    this.hairColor = hairColor;
    this.armor = armor;
    this.weapon = weapon;
    }

    // getters...
}
```

And that is how a **Builder** class should function:

``` java
public class Builder {
    private final Race race;
    private final String name;
    private Integer startingHP;
    private HairColor hairColor;
    private Armor armor;
    private Weapon weapon;

    public Builder(Race race, String name) {
        if (race == null || name == null) {
            throw new IllegalArgumentException("Race and name can not be null");
        }
	
        this.race = race;
        this.name = name;
    }

    public Builder startingHP (Integer startingHP) {
        this.startingHP = startingHP;
        return this;
    }


    public Builder withHairColor(HairColor hairColor) {
        this.hairColor = hairColor;
        return this;
    }

    public Builder withArmor(Armor armor) {
        this.armor = armor;
        return this;
    }

    public Builder withWeapon(Weapon weapon) {
        this.weapon = weapon;
        return this;
    }

    public Hero build() {
        return new Hero(
            this.race,
            this.name,
            this.startingHp,
            this.hairColor,
            this.armor,
            this.weapon
            );
    }
}
```

With the builder pattern, we have control over the steps of the **construction process**.

We can create a **different** representation with the **same** construction process.

[/slide]

[slide hideTitle]

# Example: Computer Class

[video src="https://videos.softuni.org/hls/Java/Java-OOP-Advanced/09-Design-Pattern/EN/Java-OOP-Advanced-Design-Patterns-20-21-example-computer-class-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[/slide]