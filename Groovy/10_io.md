# Input Output

## Read a file line-by-line.
```groovy
new File("foo.txt").eachLine { line -> 
	println(line)
}
```

---V

## Read a file with a Reader.
```groovy
def count=0, MAXSIZE=100
new File("foo.txt").withReader { reader ->
  while (reader.readLine() != null) {
    if (++count > MAXSIZE) {
    	println "Read 100 lines already!"
    	break
	}
  }
}
```

---V

* Write a file with a Writer.

```groovy
def fields = ["a":"1", "b":"2", "c":"3"]
new File("foo.ini").withWriter { out ->
    fields.each() { key, value ->
        out.writeLine("${key}=${value}")
    }
}
```

---V

```groovy
def p = new StringBuilder()
[1:'a', 2:'b', 3:'c'].each {
    p << it.key + ': ' + it.value + '; '
}
assert p.toString() == '1: a; 2: b; 3: c; '

def q = new StringBuilder()
[1:'a', 2:'b', 3:'c'].each { k, v ->
    q << k + ': ' + v  + '; '
}
assert q.toString() == '1: a; 2: b; 3: c; '

def r = new StringBuilder()
[1:'a', 2:'b', 3:'c'].eachWithIndex { it, i ->
  r << it.key + ' : ' + it.value + '; '
}
assert r.toString() == '1 : a; 2 : b; 3 : c; '
```

--V
* Loading a properties file in Groovy
```groovy
def props = new Properties()
new File("message.properties").withInputStream { 
  stream -> props.load(stream) 
}

println "Some property = " + props["some arbit property"]
```groovy