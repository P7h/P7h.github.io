# Introduction

* What is Groovy?
* Groovy vs. Java
* How Groovy helps?
* Few demos
* Books on Groovy

---V

## Groovy
>  “Groovy is like a super version of Java. It can leverage Java's enterprise capabilities but also has cool productivity features like closures, DSL support, builders and dynamic typing.”

Groovy = Java – boiler plate code<br>
              + mostly dynamic typing<br>
              + closures<br>
              + domain specific languages<br>
              + builders<br>
              + metaprogramming<br>
              + GDK library<br>

---V

## Obligatory "Hello World" program

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

## Simple Demos

Visualization app

Gradle build script

Displaying Cat pictures from Flickr

Griffon DB Load

---V

## Books on Groovy
[![Groovy Books](https://raw.github.com/P7h/P7h.github.io/master/Groovy/img/Groovy_Books.png)](http://www.amazon.com/s/ref=sr_il_ti_stripbooks?rh=n%3A283155%2Ck%3Agroovy+programming&lo=stripbooks)
