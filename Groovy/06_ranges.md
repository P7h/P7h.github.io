## Ranges
* Groovy offers a native datatype for Ranges.
* Ranges are specified using the double-dot range operator .. between the left and right bounds.

```groovy
def range = 1..10
println range.class
println range instanceof List
range = 1..<10
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