## Metaprogramming

* Metaprogramming refers to writing code that can dynamically change its behavior at runtime.
* A Meta-Object Protocol [MOP] refers to the capabilities in a dynamic language that enable metaprogramming.
* In Groovy, the MOP consists of four distinct capabilities within the language: reflection, metaclasses, categories, and expandos.

```groovy
println "Hello".toUpperCase()

String.metaClass.toUpperCase = {
        delegate.toLowerCase()
}

println "Hello".toUpperCase()
```

---V

```groovy
Integer.metaClass.isEven = {  ->
    delegate % 2 == 0
}
println 7.isEven()
println 10.isEven()
```

<br>
```groovy
Integer.metaClass.static.isEven = { number ->
    number % 2 == 0
}
Integer.isEven(1)
Integer.isEven(2)
```