# Maps

```groovy
def map = [name:"Sachin Tendulkar", likes:"Cricket", id:10]
assert map instanceof java.util.Map

assert map.get("name") == "Sachin Tendulkar"
assert map["name"] == "Sachin Tendulkar"
assert map.name == "Sachin Tendulkar"

assert map.get("id") == 10
assert map['id'] == 10
assert map.id == 10

map['status'] = "Retired"
assert map == [name:'Sachin Tendulkar', likes:'Cricket', id:10, status:'Retired']
```

---V

### Maps

* Iterating a Map. 
```groovy
def map = ['Android': '4.4.2', 
		   'iPhone': 'iOS7', 
		   'Windows': 'Win8', 
		   'BlackBerry': 'BlackBerry10'
		   ]

map.each { k, v -> 
    println "${k} = ${v}"
}
```

---V

### Maps

* _+_ and _<<_ operators can be used to add elements to the Map. 
* But _<<_ produces a new map while _+_ modifies the Map.

```groovy
def map01 = [name:"Sachin Tendulkar", likes:"Cricket", id:10, country:"India"]
println map01

map01 << [name:"Roger Federer", likes:"Tennis", id:101]
println map01

def map02 = [name:"Sachin Tendulkar", likes:"Cricket", id:10, status: "Retired"]
println map02

map02 += map01
println map02
```

---V

### Maps

* Variants of iterating a Map. 
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