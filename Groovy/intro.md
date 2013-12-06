# Introduction

* What is Groovy?
* Groovy vs. Java
* How Groovy helps?

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
<br>

### Groovy
```groovy
System.properties.sort().each { k,v ->
    println "$k = $v"
}
```

---V

## Features
* Automatic Imports
* Optional semicolons
* Optional parens
* Optional return statements
* Optional datatype declaration
* Optional Exception handling
* Operator Overloading
* Safe Dereferencing (?)
* Autoboxing
* Groovy Truth
* Embedded Quotes
* Heredocs
* GStrings

---V

### Automatic Imports

```groovy
import java.lang.* ;
import java.util.* ;
import java.net.* ;
import java.io.* ;
import java.math.BigInteger;
import java.math.BigDecimal;

import groovy.lang.* ;
import groovy.util.* ;
```

---V

### Optional semicolons
### Optional parens
### Optional return statements
```groovy
String getFullName() {
    "${firstName} ${lastName}"
}
```
### Optional datatype declaration

---V

### Optional Exception handling
### Operator Overloading
```groovy
def d = new Date()
d.next()
(1..3).each{ println d++ }
```
### Safe Dereferencing (?)
```groovy
def s = "A String"
s.size()

s = null
s.size() // Caught: java.lang.NullPointerException: Cannot invoke method size() 
         // on null object at CommandLine.run(CommandLine.groovy:2)
s?.size()
```

---V

### Autoboxing
```groovy
def i = 2
println i.class
```
### Groovy Truth

```groovy
//true
if(1) // any non-zero value is true
if(-1)
if(!null) // any non-null value is true
if( "John" ) // any non-empty string is true
Map family = [dad: "John" , mom: "Jane" ]
if(family) // true since the map is populated
String[] sa = new String[1]
if(sa) // true since the array length is greater than 0
StringBuffer sb = new StringBuffer()
sb.append( "Hi" )
if(sb) // true since the StringBuffer is populated

//false
if(0) // zero is false
if(null) // null is false
if( "" ) // empty strings are false
Map family = [:]
if(family) // false since the map is empty
String[] sa = new String[0]
if(sa) // false since the array is zero length
StringBuffer sb = new StringBuffer()
if(sb) // false since the StringBuffer is empty
```

---V

### Embedded Quotes
```groovy
def s1 = 'My name is "Jane"'
def s2 = "My name is 'Jane'"
def s3 = "My name is \"Jane\""
```
### Heredocs
```groovy
String s = """This is a
multi-line String.
"You don't need to escape internal quotes" , he said.
"""
def ss = '''This
That, The Other '''
```
### GStrings
```groovy
def name = "John"
println "Hello ${name}. Today is ${new Date()}"
```

---

