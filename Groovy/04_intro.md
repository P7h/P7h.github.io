# Introduction

* What is Groovy?
* Type Systems
* Code snippet showdown: Groovy vs. Java
* How Groovy helps?
* Few demos
* Books on Groovy
* Recommended Book
* Groovy guys on Twitter

---V

## Tip
> Any Java file can be renamed as a Groovy file. And it will compile and execute just as fine.
> Groovy runs on the JVM.

---V

## Groovy
> Groovy is like a super version of Java. It can leverage Java's enterprise capabilities but also has cool productivity features like closures, DSL support, builders and dynamic typing.

<br>

```groovy
Groovy = Java – boiler plate code
              + mostly dynamic typing
              + closures
              + domain specific languages
              + builders
              + metaprogramming
              + GDK library
```

---V

## Type Systems
* In programming languages, a **type system** is a collection of rules that assign a property called a _type_ to the various constructs — such as variables, expressions, functions or modules, etc — a computer program is composed of.

> Groovy is [dynamically typed programming language](http://en.wikipedia.org/wiki/Dynamic_programming_language); while Java is [statically typed programming language](http://en.wikipedia.org/wiki/Type_system#Static_type-checking).

* Groovy

```groovy
def groovyString = "Peter Higgs"
println groovyString.class
```

<br>

* Java

```java
String javaString = "Satyendra Nath Bose";
```

---V

## Obligatory "Hello World"

### Java
```java
public class HelloWorld {
	public static void main(String[] args) {
		System.out.println("Hello World");
	}
}
```
<br>
### Groovy
```groovy
println "Hello World"
```

---V
## System Properties
### Java

```java
import java.util.Iterator;
import java.util.Properties;
import java.util.Set;
import java.util.SortedMap;
import java.util.TreeMap;

public class SystemProperties {
    public static void main(String[] args) {
        Properties properties = System.getProperties();
        SortedMap sortedSystemProperties = new TreeMap(properties);
        Set keySet = sortedSystemProperties.keySet();
        Iterator iterator = keySet.iterator();
        String key = null;
        while (iterator.hasNext()) {
            key = (String) iterator.next();
            System.out.println(key + " = " + properties.getProperty(key));
        }
    }
}
```

### Groovy

```groovy
System.properties.sort().each { key, value ->
    println "$key = $value"
}
```

---V

## Trivia
Guess what might be the output of this Groovy snippet?

```groovy
String.methods.each {
    println it
}
```

---V

## Demos

* Groovy program to fetch and display kitten pictures from Flickr.

* Java build script showdown: Maven vs. Gradle.

* Visualization app built using Groovy and Grails.

* Griffon sample app for loading dummy data to a database.

---V

## Books on Groovy
[![Groovy Books](https://raw.github.com/P7h/P7h.github.io/master/Groovy/img/Groovy_Books.png)](http://www.amazon.com/s/ref=sr_il_ti_stripbooks?rh=n%3A283155%2Ck%3Agroovy+programming&lo=stripbooks)
[Various Groovy Books on Amazon](http://www.amazon.com/s/ref=sr_il_ti_stripbooks?rh=n%3A283155%2Ck%3Agroovy+programming&lo=stripbooks)

---V

## A thorough introduction to Groovy

[![Best book on Groovy](https://raw.github.com/P7h/P7h.github.io/master/Groovy/img/GinA.png)](http://www.manning.com/koenig)

[Groovy in Action aka GinA](http://www.manning.com/koenig)

---V

## Groovy guys on Twitter

* [Guillaume Laforge's public Groovy Ecosystem List](https://twitter.com/glaforge/groovy-ecosystem/members)