## Groovy Features
* Automatic imports
* Optional semicolons & parens
* Optional return statements
* Optional datatype declaration
* Operator Overloading
* Safe Dereferencing
* Autoboxing
* Groovy Truth
* Embedded Quotes & Heredocs
* GStrings
* POJO vs. POGO
* Import aliasing

---V

* Automatic imports

```groovy
import java.lang.*;
import java.util.*;
import java.net.*;
import java.io.*;
import java.math.BigInteger;
import java.math.BigDecimal;

import groovy.lang.*;
import groovy.util.*;
```

---V

* Optional semicolons and parentheses
* Optional return statements

```groovy
firstName = "James"
lastName = "Strachan"

String getFullName() {
  "${firstName} ${lastName}"
}
println getFullName()
```

---V

* Optional datatype declaration
* Operator Overloading

```groovy
def date = new Date()
date.next()
(1..3).each{ println date++ }
```

---V
* Safe Dereferencing
Java

```java
if (order != null) {
    if (order.getCustomer() != null) {
        if (order.getCustomer().getAddress() != null) {
            System.out.println(order.getCustomer().getAddress());
        }
    }
}
```
<br>
Groovy

```groovy
println order?.customer?.address
```

---V
* Safe Dereferencing

```groovy
def str = "A String"
println str.size()

str = null
str.size() // Caught: java.lang.NullPointerException: Cannot invoke method size() 
           // on null object at CommandLine.run(CommandLine.groovy:2)
println str?.size()
```

---V

* Autoboxing

```groovy
def intNum = 2
println intNum.class
```
* Groovy Truth

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
StringBuilder sb = new StringBuilder()
if(sb) // false since the StringBuffer is empty
```

---V

* Embedded Quotes

```groovy
def s1 = 'You either die a "hero" or you live long enough to see yourself become the "villain".'
def s2 = "You either die a 'hero' or you live long enough to see yourself become the 'villain'."
def s3 = "You either die a \"hero\" or you live long enough to see yourself become the \"villain\"."
```
* Heredocs

```groovy
String s = """Harvey said "You either die a hero or 
you live long enough to see yourself become the villain.""
"""
def ss = '''This
That and 
finally The Other'''
```
* GStrings

```groovy
def firstName = "James"
def lastName = "Strachan"
println "Ahoy ${firstName} ${lastName}, today is ${new Date()}"
```

---V

* POJO

```java
public class Person {

	private String firstName;
	private String lastName;

	public String getFirstName() {
		return firstName;
	}

	public void setFirstName(String firstName) {
		this.firstName = firstName;
	}

	public String getLastName() {
		return lastName;
	}

	public void setLastName(String lastName) {
		this.lastName = lastName;
	}

	public String toString() {
		return firstName + " " + lastName;
	}
}
Person person = new Person();
person.setFirstName("James");
person.setLastName("Strachan");
  
System.out.println("Name: " + person);
```

---V
* POGO

```groovy
class Person {
    String firstName
    String lastName
    String toString() {
        return firstName + " " + lastName
    }
}
def person01 = new Person()
person01.firstName = "James"
person01.lastName = "Strachan"
println "Name: " + person01

def person02 = new Person()
person02.with {
    firstName = "Guillaume"
    lastName = "Laforge"
}
println "Name again: " + person02

def person03 = new Person(firstName: "Graeme", lastName: "Rocher")
println "Name yet again: " + person03
```

---V
* Import aliasing

```groovy
import java.text.SimpleDateFormat as SDF
SDF sdf = new SDF("MM/dd/yyyy")
println sdf.format(new Date())
```
--V
[Groovy style and language feature guidelines for Java developers] (http://groovy.codehaus.org/Groovy+style+and+language+feature+guidelines+for+Java+developers)