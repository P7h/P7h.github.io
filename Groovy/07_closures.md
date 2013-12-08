## Closures
* Closure is a free-standing, named block of code. 
* It is behavior that doesn’t have a surrounding class.

```groovy
def addNumbers = { x, y -> 
	x + y
}
println addNumbers(4, 3)
```
<br>

* Closures with parameters

```groovy
def printSum = { a, b -> 
	print a + b
}
printSum 5, 7
```

---V

### Implicit variables

* A Closure that takes a single argument may omit the parameter definition of the Closure.

```groovy
def printStr = { 
	print it
}
printStr "Printing with custom method"
```

```groovy
String.methods.each {
    println it
}
```

---V

### Currying

* Transform function with particular number of parameters and returns a function with some of the parameter values fixed, creating a new function.
* Curry as many parameters as required.
* The first curry call fills in the leftmost parameter.
* Each subsequent call fills in the next parameter to the right.
* Given:

```groovy
f: (X x Y) -> Z
```

* Then:

```groovy
curry(f): X -> (Y -> Z) 
```

* Tax calculation:
```groovy
def calculateTax = { taxRate, amount ->
	amount + (taxRate * amount)
}

def tax = calculateTax.curry(0.1)

(10..15).each {
	println "Total cost: ${tax(it)}"
}
```

---V

### Loop variants

```groovy
def result = ''
def compute = { 
    if (!it) {
        result = '0'
    } else {
        result += it
    }
}
5.times compute
assert '01234' == result

0.upto 7, compute
assert '01234567' == result

0.step 10, 2, compute
assert '02468' == result
```