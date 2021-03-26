# Streams

[slide hideTitle]

# Streams Basics

[video src="https://videos.softuni.org/hls/Java/Java-Advanced/07-Streams-Files-and-Directories/EN/interactive-java-advanced-streams-files-and-directories-6-Stream-Basics-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

All of us have watched online videos on YouTube or another website.

When you hit the play button on a video, a small portion of the file gets loaded into your device's memory before the video can play. 

There is no need to download the complete video before you start playing it, and this is called **streaming**.

A stream can be defined as a **sequence of data**. 

In Java, a stream is **composed of bytes**. 

It's called a stream because it is like a stream of water that continues to flow.

[/slide]

[slide hideTitle]

# Types of Streams

There are **two fundamental types** of Streams:

- **InputStreams** − used to read data from a **source**

[image assetsSrc="streams-files-directories-example(1).png" /]

- **OutputStreams** − used for writing data to a **destination**

[image assetsSrc="streams-files-directories-example(2).png" /]


[/slide]

[slide hideTitle]
# Opening a File Stream

[video src="https://videos.softuni.org/hls/Java/Java-Advanced/07-Streams-Files-and-Directories/EN/interactive-java-advanced-streams-files-and-directories-7-Opening-A-File-Stream-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Let us look at the following example that illustrates how to open a file stream.

```java
String path = "C:\\input.txt";
FileInputStream fileStream = new FileInputStream(path);
int oneByte = fileStream.read();

while (oneByte >= 0) {
  System.out.println(oneByte);
  
  oneByte = fileStream.read();
}
```

First, we declare a **path** variable that holds the path to the resource that we will work with.


Instantiating an input stream by using the **FileInputStream** class:

```java
FileInputStream fileStream = new FileInputStream(path);
```

As you can see the file path is added as a parameter in the FileInputStream's constructor.

Next, we are starting the stream reading process by storing the first byte of the file into a variable of type **int**:

```java
int oneByte = fileStream.read();
```

After this, we use a while loop to read the file until the ``read()`` method returns **-1**. 

If the **oneByte** variable returns -1 at any point, this would mean there is nothing more to read.

Printing oneByte to the console is not necessary, but in this example, it helps to show the moment when the read() method returns -1.


[/slide]

[slide hideTitle]
# Closing a File Stream

[video src="https://videos.softuni.org/hls/Java/Java-Advanced/07-Streams-Files-and-Directories/EN/interactive-java-advanced-streams-files-and-directories-8-9-Closing-A-File-Stream-1-2-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

To avoid memory leaks and application crashes, we should close any streams that we open when they are no longer needed.

One way to close File Streams is by using `try-catch-finally` to handle possible exceptions:

```java

String path = "C:\\input.txt";

// declaring the inputStream variable
InputStream inputStream = null;

try {
    // opening a stream might cause an exception if the file is missing or corrupted
    // or some other circumstances might trip us in our efforts of reading it
    inputStream = new FileInputStream(path);
    int oneByte = inputStream.read();
    while (oneByte >= 0) {
        System.out.print(oneByte);
        oneByte = inputStream.read();
    }
} // specifying the exact type of exception
  catch (IOException ex) {
    // handling the exception
    System.out.println("File not found!");

}
  finally {
    if (inputStream != null) {
      // closing the stream
        inputStream.close();
    }
}

```

The exception that can occur once we try to open a FileInputStream can typically be of type **IOException** (Input/Output Exception).

It has to be handled by the developer and in this example, we are going to print "File not found!".

The closing of the Input Stream is in a `finally` block which means it will always be executed even if an exception is thrown.

The way this works is that the code in the `try` block will run and if there is an IOException the "File not found!" error will be printed.

After all of this is done the Input Stream will close and the resources used by it will be freed up.


There is a **shorter way** of implementing the same behavior from the previous example - `try-with-resources`.

We can create a Stream inside the try block.

The **main benefit** is that the Stream will be **automatically closed** after we finish our job in the try block.

```java
// source 
String path = "C:\\input.txt";

// opening a stream inside of the braces of the try block
try (InputStream in = new FileInputStream(path)) {
    int oneByte = in.read();
    while (oneByte >= 0) {
        System.out.print(oneByte);
        oneByte = in.read();
      }
  } catch (IOException e) {
        System.out.println("File not found!");
}

```

[/slide]

[slide hideTitle]
# Problem with Solution: Read File

[video src="https://videos.softuni.org/hls/Java/Java-Advanced/07-Streams-Files-and-Directories/EN/interactive-java-advanced-streams-files-and-directories-10-read-file-problem-and-solution-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="Read File" taskId="java-advanced-streams-files-lab-read-file" executionType="tests-execution" executionStrategy="java-code" requiresInput]
[code-editor language=java]
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Write your code here
    }
}
```
[/code-editor]
[task-description]
## Description

**Download the resources** [here](https://videos.softuni.org/resources/java/java-advanced/04-Java-Advanced-Files-and-Streams-Lab-Resources.zip ). The zip file contains the resources for all the tasks in this lesson.

You are given a file named "**input.txt**" (from the Resources - Folder).

**Read** and **print** all of its contents as a sequence of bytes (the binary representation of the ASCII code for each character) separated by a single comma.

## Guidelines

There is a zipped folder with resources for all exercises, that you need to use. 

For each exercise submit only the **output** of your program, **not the code**.


## Examples
| **Input** | **Output** |
| --- | --- |
| On January 1 , 1533 , Michael Angelo, then fifty-seven years old, writes… | 11101111 10111011 10111111 1001111 1101110 100000 1001010 1100001 1101110 1110101… |

| **Input** | **Output** |
| --- | --- |
| Two households, both alike in dignity, | 1010100 1110111 1101111 100000 1101000 1101111 1110101 1110011 1100101 1101000… |


## Hints
- Create a string variable holding the path to the file. For example, if the file is located in "D:\\"

```java
String path = "D:\\input.txt";
```
- Use try-with-resources to open the file and to ensure that it will be closed after you are done with it

```java
try(FileInputStream fileStream = new FileInputStream(path)) {
      
} catch (IOException ex){
      ex.printStackTrace();
}
```

- Use the ``read()`` method to read each byte of the file until it returns -1

```java
try (FileInputStream fileStream = new FileInputStream(path)) {
    int oneByte = fileStream.read();
    while (oneByte >= 0) {
        System.out.printf("%s ", Integer.toBinaryString(oneByte));
        oneByte = fileStream.read();
    }
} catch (IOException ex) {
    ex.printStackTrace();
}
```
- Select the output of the program and copy it [Ctrl + C]
- Submit the output

[/task-description]
[code-io /]
[tests]
[test]
[input]
1001111 1101110 100000 1001010 1100001 1101110 1110101 1100001 1110010 1111001 100000 110001 100000 101100 100000 110001 110101 110011 110011 100000 101100 100000 1001101 1101001 1100011 1101000 1100001 1100101 1101100 100000 1000001 1101110 1100111 1100101 1101100 1101111 101100 100000 1110100 1101000 1100101 1101110 100000 1100110 1101001 1100110 1110100 1111001 101101 1110011 1100101 1110110 1100101 1101110 100000 1111001 1100101 1100001 1110010 1110011 100000 1101111 1101100 1100100 101100 100000 1110111 1110010 1101001 1110100 1100101 1110011 1101 1010 1100110 1110010 1101111 1101101 100000 1000110 1101100 1101111 1110010 1100101 1101110 1100011 1100101 100000 1110100 1101111 100000 1010100 1101111 1101101 1101101 1100001 1110011 1101111 100000 1100100 1100101 100111 100000 1000011 1100001 1110110 1100001 1101100 1101001 1100101 1110010 1101001 101100 100000 1100001 100000 1111001 1101111 1110101 1110100 1101000 100000 1101111 1100110 100000 1101110 1101111 1100010 1101100 1100101 100000 1010010 1101111 1101101 1100001 1101110 100000 1100110 1100001 1101101 1101001 1101100 1111001 101100 1101 1010 1110111 1101000 1101111 100000 1100001 1100110 1110100 1100101 1110010 1110111 1100001 1110010 1100100 1110011 100000 1100010 1100101 1100011 1100001 1101101 1100101 100000 1101000 1101001 1110011 100000 1100110 1100001 1110110 1101111 1110101 1110010 1101001 1110100 1100101 100000 1110000 1110101 1110000 1101001 1101100 111010 100000 100010 1001001 1100110 100000 1001001 100000 1100100 1101111 100000 1101110 1101111 1110100 100000 1110000 1101111 1110011 1110011 1100101 1110011 1110011 100000 1110100 1101000 1100101 1101 1010 1100001 1110010 1110100 100000 1101111 1100110 100000 1101110 1100001 1110110 1101001 1100111 1100001 1110100 1101001 1101110 1100111 100000 1110100 1101000 1100101 100000 1110011 1100101 1100001 100000 1101111 1100110 100000 1111001 1101111 1110101 1110010 100000 1110000 1101111 1110100 1100101 1101110 1110100 100000 1100111 1100101 1101110 1101001 1110101 1110011 101100 100000 1110100 1101000 1100001 1110100 100000 1100111 1100101 1101110 1101001 1110101 1110011 100000 1110111 1101001 1101100 1101100 1101 1010 1101110 1100101 1110110 1100101 1110010 1110100 1101000 1100101 1101100 1100101 1110011 1110011 100000 1100101 1111000 1100011 1110101 1110011 1100101 100000 1101101 1100101 101100 100000 1100001 1101110 1100100 100000 1101110 1100101 1101001 1110100 1101000 1100101 1110010 100000 1100100 1100101 1110011 1110000 1101001 1110011 1100101 100000 1101101 1111001 100000 1101001 1101110 1100101 1110001 1110101 1100001 1101100 1101001 1110100 1111001 101100 100000 1101110 1101111 1110010 100000 1100100 1100101 1101101 1100001 1101110 1100100 1101 1010 1101111 1100110 100000 1101101 1100101 100000 1110100 1101000 1100001 1110100 100000 1110111 1101000 1101001 1100011 1101000 100000 1001001 100000 1101000 1100001 1110110 1100101 100000 1101001 1110100 100000 1101110 1101111 1110100 100000 1101001 1101110 100000 1101101 1100101 100000 1110100 1101111 100000 1100111 1101001 1110110 1100101 111011 100000 1110011 1101001 1101110 1100011 1100101 100000 1110100 1101000 1100001 1110100 100000 1110111 1101000 1101001 1100011 1101000 100000 1110011 1110100 1100001 1101110 1100100 1110011 1101 1010 1100001 1101100 1101111 1101110 1100101 100000 1101001 1101110 100000 1100101 1110110 1100101 1110010 1111001 1110100 1101000 1101001 1101110 1100111 100000 1100011 1100001 1101110 100000 1101001 1101110 100000 1101110 1101111 1110100 1101000 1101001 1101110 1100111 100000 1100110 1101001 1101110 1100100 100000 1101001 1110100 1110011 100000 1100011 1101111 1110101 1101110 1110100 1100101 1110010 1110000 1100001 1110010 1110100 101110 100000 1010111 1101000 1100101 1110010 1100101 1100110 1101111 1110010 1100101 100000 1111001 1101111 1110101 1110010 1101 1010 1101100 1101111 1110010 1100100 1110011 1101000 1101001 1110000 101100 100000 1011111 1110100 1101000 1100101 100000 1101111 1101110 1101100 1111001 100000 1101100 1101001 1100111 1101000 1110100 100000 1101001 1101110 100000 1101111 1110101 1110010 100000 1100001 1100111 1100101 100000 1110110 1101111 1110101 1100011 1101000 1110011 1100001 1100110 1100101 1100100 100000 1110100 1101111 100000 1110100 1101000 1101001 1110011 100000 1110111 1101111 1110010 1101100 1100100 1110011 1011111 100000 1101000 1100001 1110110 1101001 1101110 1100111 1101 1010 1101110 1101111 100000 1100101 1110001 1110101 1100001 1101100 100000 1101111 1110010 100000 1110000 1100101 1100101 1110010 101100 100000 1100011 1100001 1101110 1101110 1101111 1110100 100000 1100110 1101001 1101110 1100100 100000 1110011 1100001 1110100 1101001 1110011 1100110 1100001 1100011 1110100 1101001 1101111 1101110 100000 1101001 1101110 100000 1110100 1101000 1100101 100000 1110111 1101111 1110010 1101011 100000 1101111 1100110 100000 1100001 1101110 1111001 100000 1101111 1110100 1101000 1100101 1110010 1101 1010 1101000 1100001 1101110 1100100 101110 100000 1001001 1100110 101100 100000 1110100 1101000 1100101 1110010 1100101 1100110 1101111 1110010 1100101 101100 100000 1110100 1101000 1101001 1110011 100000 1101111 1110010 100000 1110100 1101000 1100001 1110100 100000 1101001 1101110 100000 1110100 1101000 1100101 100000 1110111 1101111 1110010 1101011 1110011 100000 1110111 1101000 1101001 1100011 1101000 100000 1001001 100000 1101000 1101111 1110000 1100101 100000 1100001 1101110 1100100 100000 1110000 1110010 1101111 1101101 1101001 1110011 1100101 1101 1010 1110100 1101111 100000 1100101 1111000 1100101 1100011 1110101 1110100 1100101 100000 1110011 1101000 1101111 1110101 1101100 1100100 100000 1101000 1100001 1110000 1110000 1100101 1101110 100000 1110100 1101111 100000 1110000 1101100 1100101 1100001 1110011 1100101 100000 1111001 1101111 1110101 101100 100000 1001001 100000 1110011 1101000 1101111 1110101 1101100 1100100 100000 1100011 1100001 1101100 1101100 100000 1110100 1101000 1100001 1110100 100000 1110111 1101111 1110010 1101011 101100 100000 1101110 1101111 1110100 1101 1010 1100111 1101111 1101111 1100100 101100 100000 1100010 1110101 1110100 100000 1100110 1101111 1110010 1110100 1110101 1101110 1100001 1110100 1100101 101110 100000 1000001 1101110 1100100 100000 1101001 1100110 100000 1001001 100000 1110011 1101000 1101111 1110101 1101100 1100100 100000 1100101 1110110 1100101 1110010 100000 1100110 1100101 1100101 1101100 100000 1100001 1110011 1110011 1110101 1110010 1100101 1100100 100000 1110100 1101000 1100001 1110100 101101 101101 1100001 1110011 100000 1101000 1100001 1110011 1101 1010 1100010 1100101 1100101 1101110 100000 1110010 1100101 1110000 1101111 1110010 1110100 1100101 1100100 100000 1110100 1101111 100000 1101101 1100101 101101 101101 1001001 100000 1101000 1100001 1110110 1100101 100000 1100111 1101001 1110110 1100101 1101110 100000 1111001 1101111 1110101 1110010 100000 1101100 1101111 1110010 1100100 1110011 1101000 1101001 1110000 100000 1110011 1100001 1110100 1101001 1110011 1100110 1100001 1100011 1110100 1101001 1101111 1101110 100000 1101001 1101110 100000 1101111 1101110 1100101 1101 1010 1110100 1101000 1101001 1101110 1100111 100000 1101111 1110010 100000 1100001 1101110 1101111 1110100 1101000 1100101 1110010 101100 100000 1001001 100000 1110111 1101001 1101100 1101100 100000 1101101 1100001 1101011 1100101 100000 1100001 100000 1100111 1101001 1100110 1110100 100000 1110100 1101111 100000 1111001 1101111 1110101 100000 1101111 1100110 100000 1101101 1111001 100000 1110000 1110010 1100101 1110011 1100101 1101110 1110100 100000 1100001 1101110 1100100 100000 1101111 1100110 100000 1100001 1101100 1101100 1101 1010 1110100 1101000 1100001 1110100 100000 1110100 1101000 1100101 100000 1100110 1110101 1110100 1110101 1110010 1100101 100000 1101101 1100001 1111001 100000 1100010 1110010 1101001 1101110 1100111 100000 1101101 1100101 111011 100000 1100001 1101110 1100100 100000 1101001 1110100 100000 1110111 1101001 1101100 1101100 100000 1100010 1100101 100000 1100001 100000 1100111 1110010 1100101 1100001 1110100 100000 1110000 1100001 1101001 1101110 100000 1110100 1101111 100000 1101101 1100101 100000 1110100 1101111 100000 1100010 1100101 1101 1010 1110101 1101110 1100001 1100010 1101100 1100101 100000 1110100 1101111 100000 1110010 1100101 1100011 1100001 1101100 1101100 100000 1110100 1101000 1100101 100000 1110000 1100001 1110011 1110100 101100 100000 1101001 1101110 100000 1101111 1110010 1100100 1100101 1110010 100000 1110100 1101111 100000 1110011 1100101 1110010 1110110 1100101 100000 1111001 1101111 1110101 100000 1110011 1101111 100000 1101101 1110101 1100011 1101000 100000 1110100 1101000 1100101 100000 1101100 1101111 1101110 1100111 1100101 1110010 101100 1101 1010 1101001 1101110 1110011 1110100 1100101 1100001 1100100 100000 1101111 1100110 100000 1101000 1100001 1110110 1101001 1101110 1100111 100000 1101111 1101110 1101100 1111001 100000 1110100 1101000 1100101 100000 1100110 1110101 1110100 1110101 1110010 1100101 101100 100000 1110111 1101000 1101001 1100011 1101000 100000 1100011 1100001 1101110 1101110 1101111 1110100 100000 1100010 1100101 100000 1101100 1101111 1101110 1100111 101100 100000 1110011 1101001 1101110 1100011 1100101 100000 1001001 100000 1100001 1101101 100000 1100001 1101100 1101100 1101 1010 1110100 1101111 1101111 100000 1101111 1101100 1100100 101110 100000 1010100 1101000 1100101 1110010 1100101 100000 1101001 1110011 100000 1101110 1101111 1110100 1101000 1101001 1101110 1100111 100000 1101101 1101111 1110010 1100101 100000 1101100 1100101 1100110 1110100 100000 1100110 1101111 1110010 100000 1101101 1100101 100000 1110100 1101111 100000 1110011 1100001 1111001 101110 100000 1010010 1100101 1100001 1100100 100000 1101101 1111001 100000 1101000 1100101 1100001 1110010 1110100 100000 1100001 1101110 1100100 1101 1010 1101110 1101111 1110100 100000 1101101 1111001 100000 1101100 1100101 1110100 1110100 1100101 1110010 101100 100000 1100110 1101111 1110010 100000 1101101 1111001 100000 1110000 1100101 1101110 100000 1100011 1100001 1101110 1101110 1101111 1110100 100000 1100001 1110000 1110000 1110010 1101111 1100001 1100011 1101000 100000 1110100 1101000 1100101 100000 1100101 1111000 1110000 1110010 1100101 1110011 1110011 1101001 1101111 1101110 100000 1101111 1100110 100000 1101101 1111001 100000 1100111 1101111 1101111 1100100 1101 1010 1110111 1101001 1101100 1101100 101110 100010 1011011 100000 110011 100000 1011101 1101 1010 1101 1010 
[/input]
[output]
1001111 1101110 100000 1001010 1100001 1101110 1110101 1100001 1110010 1111001 100000 110001 100000 101100 100000 110001 110101 110011 110011 100000 101100 100000 1001101 1101001 1100011 1101000 1100001 1100101 1101100 100000 1000001 1101110 1100111 1100101 1101100 1101111 101100 100000 1110100 1101000 1100101 1101110 100000 1100110 1101001 1100110 1110100 1111001 101101 1110011 1100101 1110110 1100101 1101110 100000 1111001 1100101 1100001 1110010 1110011 100000 1101111 1101100 1100100 101100 100000 1110111 1110010 1101001 1110100 1100101 1110011 1101 1010 1100110 1110010 1101111 1101101 100000 1000110 1101100 1101111 1110010 1100101 1101110 1100011 1100101 100000 1110100 1101111 100000 1010100 1101111 1101101 1101101 1100001 1110011 1101111 100000 1100100 1100101 100111 100000 1000011 1100001 1110110 1100001 1101100 1101001 1100101 1110010 1101001 101100 100000 1100001 100000 1111001 1101111 1110101 1110100 1101000 100000 1101111 1100110 100000 1101110 1101111 1100010 1101100 1100101 100000 1010010 1101111 1101101 1100001 1101110 100000 1100110 1100001 1101101 1101001 1101100 1111001 101100 1101 1010 1110111 1101000 1101111 100000 1100001 1100110 1110100 1100101 1110010 1110111 1100001 1110010 1100100 1110011 100000 1100010 1100101 1100011 1100001 1101101 1100101 100000 1101000 1101001 1110011 100000 1100110 1100001 1110110 1101111 1110101 1110010 1101001 1110100 1100101 100000 1110000 1110101 1110000 1101001 1101100 111010 100000 100010 1001001 1100110 100000 1001001 100000 1100100 1101111 100000 1101110 1101111 1110100 100000 1110000 1101111 1110011 1110011 1100101 1110011 1110011 100000 1110100 1101000 1100101 1101 1010 1100001 1110010 1110100 100000 1101111 1100110 100000 1101110 1100001 1110110 1101001 1100111 1100001 1110100 1101001 1101110 1100111 100000 1110100 1101000 1100101 100000 1110011 1100101 1100001 100000 1101111 1100110 100000 1111001 1101111 1110101 1110010 100000 1110000 1101111 1110100 1100101 1101110 1110100 100000 1100111 1100101 1101110 1101001 1110101 1110011 101100 100000 1110100 1101000 1100001 1110100 100000 1100111 1100101 1101110 1101001 1110101 1110011 100000 1110111 1101001 1101100 1101100 1101 1010 1101110 1100101 1110110 1100101 1110010 1110100 1101000 1100101 1101100 1100101 1110011 1110011 100000 1100101 1111000 1100011 1110101 1110011 1100101 100000 1101101 1100101 101100 100000 1100001 1101110 1100100 100000 1101110 1100101 1101001 1110100 1101000 1100101 1110010 100000 1100100 1100101 1110011 1110000 1101001 1110011 1100101 100000 1101101 1111001 100000 1101001 1101110 1100101 1110001 1110101 1100001 1101100 1101001 1110100 1111001 101100 100000 1101110 1101111 1110010 100000 1100100 1100101 1101101 1100001 1101110 1100100 1101 1010 1101111 1100110 100000 1101101 1100101 100000 1110100 1101000 1100001 1110100 100000 1110111 1101000 1101001 1100011 1101000 100000 1001001 100000 1101000 1100001 1110110 1100101 100000 1101001 1110100 100000 1101110 1101111 1110100 100000 1101001 1101110 100000 1101101 1100101 100000 1110100 1101111 100000 1100111 1101001 1110110 1100101 111011 100000 1110011 1101001 1101110 1100011 1100101 100000 1110100 1101000 1100001 1110100 100000 1110111 1101000 1101001 1100011 1101000 100000 1110011 1110100 1100001 1101110 1100100 1110011 1101 1010 1100001 1101100 1101111 1101110 1100101 100000 1101001 1101110 100000 1100101 1110110 1100101 1110010 1111001 1110100 1101000 1101001 1101110 1100111 100000 1100011 1100001 1101110 100000 1101001 1101110 100000 1101110 1101111 1110100 1101000 1101001 1101110 1100111 100000 1100110 1101001 1101110 1100100 100000 1101001 1110100 1110011 100000 1100011 1101111 1110101 1101110 1110100 1100101 1110010 1110000 1100001 1110010 1110100 101110 100000 1010111 1101000 1100101 1110010 1100101 1100110 1101111 1110010 1100101 100000 1111001 1101111 1110101 1110010 1101 1010 1101100 1101111 1110010 1100100 1110011 1101000 1101001 1110000 101100 100000 1011111 1110100 1101000 1100101 100000 1101111 1101110 1101100 1111001 100000 1101100 1101001 1100111 1101000 1110100 100000 1101001 1101110 100000 1101111 1110101 1110010 100000 1100001 1100111 1100101 100000 1110110 1101111 1110101 1100011 1101000 1110011 1100001 1100110 1100101 1100100 100000 1110100 1101111 100000 1110100 1101000 1101001 1110011 100000 1110111 1101111 1110010 1101100 1100100 1110011 1011111 100000 1101000 1100001 1110110 1101001 1101110 1100111 1101 1010 1101110 1101111 100000 1100101 1110001 1110101 1100001 1101100 100000 1101111 1110010 100000 1110000 1100101 1100101 1110010 101100 100000 1100011 1100001 1101110 1101110 1101111 1110100 100000 1100110 1101001 1101110 1100100 100000 1110011 1100001 1110100 1101001 1110011 1100110 1100001 1100011 1110100 1101001 1101111 1101110 100000 1101001 1101110 100000 1110100 1101000 1100101 100000 1110111 1101111 1110010 1101011 100000 1101111 1100110 100000 1100001 1101110 1111001 100000 1101111 1110100 1101000 1100101 1110010 1101 1010 1101000 1100001 1101110 1100100 101110 100000 1001001 1100110 101100 100000 1110100 1101000 1100101 1110010 1100101 1100110 1101111 1110010 1100101 101100 100000 1110100 1101000 1101001 1110011 100000 1101111 1110010 100000 1110100 1101000 1100001 1110100 100000 1101001 1101110 100000 1110100 1101000 1100101 100000 1110111 1101111 1110010 1101011 1110011 100000 1110111 1101000 1101001 1100011 1101000 100000 1001001 100000 1101000 1101111 1110000 1100101 100000 1100001 1101110 1100100 100000 1110000 1110010 1101111 1101101 1101001 1110011 1100101 1101 1010 1110100 1101111 100000 1100101 1111000 1100101 1100011 1110101 1110100 1100101 100000 1110011 1101000 1101111 1110101 1101100 1100100 100000 1101000 1100001 1110000 1110000 1100101 1101110 100000 1110100 1101111 100000 1110000 1101100 1100101 1100001 1110011 1100101 100000 1111001 1101111 1110101 101100 100000 1001001 100000 1110011 1101000 1101111 1110101 1101100 1100100 100000 1100011 1100001 1101100 1101100 100000 1110100 1101000 1100001 1110100 100000 1110111 1101111 1110010 1101011 101100 100000 1101110 1101111 1110100 1101 1010 1100111 1101111 1101111 1100100 101100 100000 1100010 1110101 1110100 100000 1100110 1101111 1110010 1110100 1110101 1101110 1100001 1110100 1100101 101110 100000 1000001 1101110 1100100 100000 1101001 1100110 100000 1001001 100000 1110011 1101000 1101111 1110101 1101100 1100100 100000 1100101 1110110 1100101 1110010 100000 1100110 1100101 1100101 1101100 100000 1100001 1110011 1110011 1110101 1110010 1100101 1100100 100000 1110100 1101000 1100001 1110100 101101 101101 1100001 1110011 100000 1101000 1100001 1110011 1101 1010 1100010 1100101 1100101 1101110 100000 1110010 1100101 1110000 1101111 1110010 1110100 1100101 1100100 100000 1110100 1101111 100000 1101101 1100101 101101 101101 1001001 100000 1101000 1100001 1110110 1100101 100000 1100111 1101001 1110110 1100101 1101110 100000 1111001 1101111 1110101 1110010 100000 1101100 1101111 1110010 1100100 1110011 1101000 1101001 1110000 100000 1110011 1100001 1110100 1101001 1110011 1100110 1100001 1100011 1110100 1101001 1101111 1101110 100000 1101001 1101110 100000 1101111 1101110 1100101 1101 1010 1110100 1101000 1101001 1101110 1100111 100000 1101111 1110010 100000 1100001 1101110 1101111 1110100 1101000 1100101 1110010 101100 100000 1001001 100000 1110111 1101001 1101100 1101100 100000 1101101 1100001 1101011 1100101 100000 1100001 100000 1100111 1101001 1100110 1110100 100000 1110100 1101111 100000 1111001 1101111 1110101 100000 1101111 1100110 100000 1101101 1111001 100000 1110000 1110010 1100101 1110011 1100101 1101110 1110100 100000 1100001 1101110 1100100 100000 1101111 1100110 100000 1100001 1101100 1101100 1101 1010 1110100 1101000 1100001 1110100 100000 1110100 1101000 1100101 100000 1100110 1110101 1110100 1110101 1110010 1100101 100000 1101101 1100001 1111001 100000 1100010 1110010 1101001 1101110 1100111 100000 1101101 1100101 111011 100000 1100001 1101110 1100100 100000 1101001 1110100 100000 1110111 1101001 1101100 1101100 100000 1100010 1100101 100000 1100001 100000 1100111 1110010 1100101 1100001 1110100 100000 1110000 1100001 1101001 1101110 100000 1110100 1101111 100000 1101101 1100101 100000 1110100 1101111 100000 1100010 1100101 1101 1010 1110101 1101110 1100001 1100010 1101100 1100101 100000 1110100 1101111 100000 1110010 1100101 1100011 1100001 1101100 1101100 100000 1110100 1101000 1100101 100000 1110000 1100001 1110011 1110100 101100 100000 1101001 1101110 100000 1101111 1110010 1100100 1100101 1110010 100000 1110100 1101111 100000 1110011 1100101 1110010 1110110 1100101 100000 1111001 1101111 1110101 100000 1110011 1101111 100000 1101101 1110101 1100011 1101000 100000 1110100 1101000 1100101 100000 1101100 1101111 1101110 1100111 1100101 1110010 101100 1101 1010 1101001 1101110 1110011 1110100 1100101 1100001 1100100 100000 1101111 1100110 100000 1101000 1100001 1110110 1101001 1101110 1100111 100000 1101111 1101110 1101100 1111001 100000 1110100 1101000 1100101 100000 1100110 1110101 1110100 1110101 1110010 1100101 101100 100000 1110111 1101000 1101001 1100011 1101000 100000 1100011 1100001 1101110 1101110 1101111 1110100 100000 1100010 1100101 100000 1101100 1101111 1101110 1100111 101100 100000 1110011 1101001 1101110 1100011 1100101 100000 1001001 100000 1100001 1101101 100000 1100001 1101100 1101100 1101 1010 1110100 1101111 1101111 100000 1101111 1101100 1100100 101110 100000 1010100 1101000 1100101 1110010 1100101 100000 1101001 1110011 100000 1101110 1101111 1110100 1101000 1101001 1101110 1100111 100000 1101101 1101111 1110010 1100101 100000 1101100 1100101 1100110 1110100 100000 1100110 1101111 1110010 100000 1101101 1100101 100000 1110100 1101111 100000 1110011 1100001 1111001 101110 100000 1010010 1100101 1100001 1100100 100000 1101101 1111001 100000 1101000 1100101 1100001 1110010 1110100 100000 1100001 1101110 1100100 1101 1010 1101110 1101111 1110100 100000 1101101 1111001 100000 1101100 1100101 1110100 1110100 1100101 1110010 101100 100000 1100110 1101111 1110010 100000 1101101 1111001 100000 1110000 1100101 1101110 100000 1100011 1100001 1101110 1101110 1101111 1110100 100000 1100001 1110000 1110000 1110010 1101111 1100001 1100011 1101000 100000 1110100 1101000 1100101 100000 1100101 1111000 1110000 1110010 1100101 1110011 1110011 1101001 1101111 1101110 100000 1101111 1100110 100000 1101101 1111001 100000 1100111 1101111 1101111 1100100 1101 1010 1110111 1101001 1101100 1101100 101110 100010 1011011 100000 110011 100000 1011101 1101 1010 1101 1010  
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

[slide hideTitle]
# Problem with Solution: Write to File

[video src="https://videos.softuni.org/hls/Java/Java-Advanced/07-Streams-Files-and-Directories/EN/interactive-java-advanced-streams-files-and-directories-12-Write-To-File-Problem-and-solution-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[code-task title="Write to File" taskId="java-advanced-streams-files-lab-write-to-file" executionType="tests-execution" executionStrategy="java-code" requiresInput]
[code-editor language=java]
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Write your code here
    }
}
```
[/code-editor]
[task-description]
## Description

Read the file named "input.txt" that is provided for this exercise and write all its content to a file while skipping any punctuation. 

Skip the following symbols: `,`, `.`, `!`, `?`.

## Guidelines

You should already have all the required resources downloaded from the previous task.

For each exercise submit only the **output** of your program, **not the code**.

## Examples
| **Input** | **Output** |
| --- | --- |
| On January 1 , 1533 , Michael Angelo, then fifty-seven years old, writes | On January 1  1533  Michael Angelo then fifty-seven years old writes |


| **Input** | **Output** |
| --- | --- |
| Two households, both alike in dignity. | Two households both alike in dignity |
| In fair Verona, where we lay our scene. | In fair Verona where we lay our scene |

## Hints

- Create a FileInputStream to read the file
- Create a FileOutputStream to write to a file
- Create a list, containing all characters that you need to skip and check if the current char is contained in it

```java
if (!punctuation.contains((char) oneByte)) {
    out.write(oneByte);
}

```


[/task-description]
[code-io /]
[tests]
[test]
[input]
On January 1  1533  Michael Angelo then fifty-seven years old writes
from Florence to Tommaso de' Cavalieri a youth of noble Roman family
who afterwards became his favourite pupil: "If I do not possess the
art of navigating the sea of your potent genius that genius will
nevertheless excuse me and neither despise my inequality nor demand
of me that which I have it not in me to give; since that which stands
alone in everything can in nothing find its counterpart Wherefore your
lordship _the only light in our age vouchsafed to this worlds_ having
no equal or peer cannot find satisfaction in the work of any other
hand If therefore this or that in the works which I hope and promise
to execute should happen to please you I should call that work not
good but fortunate And if I should ever feel assured that--as has
been reported to me--I have given your lordship satisfaction in one
thing or another I will make a gift to you of my present and of all
that the future may bring me; and it will be a great pain to me to be
unable to recall the past in order to serve you so much the longer
instead of having only the future which cannot be long since I am all
too old There is nothing more left for me to say Read my heart and
not my letter for my pen cannot approach the expression of my good
will"\[ 3 \]
[/input]
[output]
On January 1  1533  Michael Angelo then fifty-seven years old writes
from Florence to Tommaso de' Cavalieri a youth of noble Roman family
who afterwards became his favourite pupil: "If I do not possess the
art of navigating the sea of your potent genius that genius will
nevertheless excuse me and neither despise my inequality nor demand
of me that which I have it not in me to give; since that which stands
alone in everything can in nothing find its counterpart Wherefore your
lordship _the only light in our age vouchsafed to this worlds_ having
no equal or peer cannot find satisfaction in the work of any other
hand If therefore this or that in the works which I hope and promise
to execute should happen to please you I should call that work not
good but fortunate And if I should ever feel assured that--as has
been reported to me--I have given your lordship satisfaction in one
thing or another I will make a gift to you of my present and of all
that the future may bring me; and it will be a great pain to me to be
unable to recall the past in order to serve you so much the longer
instead of having only the future which cannot be long since I am all
too old There is nothing more left for me to say Read my heart and
not my letter for my pen cannot approach the expression of my good
will"\[ 3 \]
[/output]
[/test]
[/tests]
[/code-task]
[/slide]