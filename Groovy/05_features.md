## Groovy Features
* Automatic Imports
* Optional semicolons & parens
* Optional return statements
* Optional datatype declaration
* Operator Overloading
* Safe Dereferencing
* Autoboxing
* Groovy Truth
* Embedded Quotes
* Heredocs
* GStrings

---V

* Automatic Imports

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

* Optional semicolons and parens
* Optional return statements
```groovy
String getFullName() {
    "${firstName} ${lastName}"
}
```

---V

* Optional datatype declaration
* Operator Overloading
```groovy
def date = new Date()
date.next()
(1..3).each{ println date++ }
```
* Safe Dereferencing
```groovy
def str = "A String"
str.size()

str = null
str.size() // Caught: java.lang.NullPointerException: Cannot invoke method size() 
         // on null object at CommandLine.run(CommandLine.groovy:2)
str?.size()
```

---V

* Autoboxing
```groovy
def i = 2
println i.class
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
StringBuffer sb = new StringBuffer()
if(sb) // false since the StringBuffer is empty
```

---V

* Embedded Quotes
```groovy
def s1 = 'My name is "Jane"'
def s2 = "My name is 'Jane'"
def s3 = "My name is \"Jane\""
```
* Heredocs
```groovy
String s = """This is a
multi-line String.
"You don't need to escape internal quotes".
"""
def ss = '''This
That and 
finally The Other '''
```
* GStrings
```groovy
def firstName = "James"
def lastName = "Strachan"
println "Hello ${firstName} ${lastName}, today is ${new Date()}"
```