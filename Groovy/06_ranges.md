## Ranges
```groovy
def range = 1..3
println range.class
```
<br>

### Methods in IntRange
```groovy
groovy.lang.IntRange.methods.each { 
	println it
}
```

---V

### Few other examples
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