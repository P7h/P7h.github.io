## Lists

```groovy
def list = [1, 2, 3, 4]
assert list.size == 4
assert list.size() == 4
assert list.class == ArrayList
```
<br>
```groovy
def list = []
assert list.size() == 0
list << 5
assert list.size() == 1
list << 'a' << 'e' << 'i'
assert list == [5,  'a', 'e', 'i']
```

---V

## Lists

```groovy
assert [0, 1, 2] + 3 + [4, 5] + 6 == [0, 1, 2, 3, 4, 5, 6]
assert [0, 1, 2].plus(3).plus([4, 5]).plus(6) == [0, 1, 2, 3, 4, 5, 6]

def list = [0, 1, 2, 3]
list += 4
list += [5, 6]
assert list == [0, 1, 2, 3, 4, 5, 6]
assert list[3] == 3
assert list.getAt(5) == 5

list.putAt(5, -5)
assert list[5] == -5
assert list[-4] == 3
assert list[-4] * 2 == 6
assert list * 2 == [0, 1, 2, 3, 4, -5, 6, 0, 1, 2, 3, 4, -5, 6]

assert ('a'..'g')[3..5] == ['d', 'e', 'f']
```

---V

## Lists

```groovy
assert [1,[2,3]].flatten() == [1,2,3]
assert [1,2,3].intersect([4,3,1])== [3,1]
assert [1,2,3].disjoint([4,5,6])

list = [1,2,3]
popped = list.pop()
assert popped == 3
assert list == [1,2]

assert [1,2].reverse() == [2,1]
assert [3,1,2].sort() == [1,2,3]
```

---V

## Lists

```groovy
def list = [1, 2, 3, 4, 5]
def sublist = list.subList(2, 4)
sublist[0] = 9
assert list == [1, 2, 9, 4, 5]
list[3] = 11
assert sublist == [9, 11]
```
<br>

```groovy
def range = ('a'..'f')
range.eachWithIndex{ it, i -> 
    println "$i: $it"
}
assert range.join(', ') == 'a, b, c, d, e, f'
```

---V

## Lists
* Double each element in a List using a closure

```groovy
def doubled = [1,2,3].collect { item ->
	item * 2
}
assert doubled == [2,4,6]
```
<br>

* Divide a list into 2 lists with one list containing only unique elements and another only duplicates.
```groovy
list=[1, 2, 7, 2, 2, 4, 7, 11, 5, 2, 5]
def uniques = [] as Set, dups = [] as Set
list.each {
	uniques.add(it) || dups.add(it)
}
uniques.removeAll(dups)
assert uniques == [1, 4, 11] as Set && dups == [2, 5, 7] as Set
```