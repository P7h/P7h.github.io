# Introduction

* What is Groovy?
* Code snippet showdown: Groovy vs. Java
* How Groovy helps?
* Few demos
* Books on Groovy
* Recommended Book

---V

## Groovy
>  “Groovy is like a super version of Java. It can leverage Java's enterprise capabilities but also has cool productivity features like closures, DSL support, builders and dynamic typing.”

<br>
Groovy = Java – boiler plate code<br>
              + mostly dynamic typing<br>
              + closures<br>
              + domain specific languages<br>
              + builders<br>
              + metaprogramming<br>
              + GDK library<br>

---V

## Obligatory "Hello World"

### Java
```java
public class HelloWorld {
	public static void main( String[] args ) {
		System.out.println( "Hello World" );
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
System.properties.sort().each { k,v ->
    println "$k = $v"
}
```

---V

## Food for thought
Can you guess what might be the output of this snippet?
```groovy
String.methods.each {
    println it
}
```

---V

## Demos

* Cat pictures from Flickr

* Build script showdown: Gradle vs. Maven

* Visualization app built using Groovy and Grails

* Griffon sample app for loading Database

---V

## Books on Groovy
[![Groovy Books](https://raw.github.com/P7h/P7h.github.io/master/Groovy/img/Groovy_Books.png)](http://www.amazon.com/s/ref=sr_il_ti_stripbooks?rh=n%3A283155%2Ck%3Agroovy+programming&lo=stripbooks)
[Various Groovy Books on Amazon](http://www.amazon.com/s/ref=sr_il_ti_stripbooks?rh=n%3A283155%2Ck%3Agroovy+programming&lo=stripbooks)

---V

## A thorough introduction to Groovy

[![Best book on Groovy](https://raw.github.com/P7h/P7h.github.io/master/Groovy/img/GinA.png)](http://www.manning.com/koenig)

[Groovy in Action aka GinA](http://www.manning.com/koenig)