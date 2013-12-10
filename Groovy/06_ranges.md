## Ranges
* Groovy offers a native datatype for Ranges.
* Ranges are specified using the double-dot range operator .. between the left and right bounds.

```groovy
def range = 1..3
println range.class
println range instanceof Range
def alphabets = 'a'..'z'
println alphabets.class
alphabets.each {
    print it
}
```

```groovy
IntRange.methods.each { 
	println it
}
```

---V

* Traditional mainstream languages
Data can be stored in variables, passed around, combined in structured ways to form more complex data; code stays put where it is defined.

* Languages supporting closures
Data _and code_ can be stored in variables, passed around, combined in structured ways to form more complex algorithms and data.

```groovy
doubleNum = { 
	num -> num * 2
}
assert doubleNum(3) == 6

def processThenPrint = { num, closure ->
    num = closure(num);
}
assert processThenPrint(3, doubleNum) == 6
assert processThenPrint(10) { it / 2 } == 5
```

---V

### Few other methods of Range

```groovy
def i = 1..5
println i.size()
println i.from
println i.to
println i.contains(1)
println i.contains(9)
println i.reverse()
```
<br>

```groovy
def today = new Date()
def nextWeek = today + 7
(today..nextWeek).each {
    println it
}
```