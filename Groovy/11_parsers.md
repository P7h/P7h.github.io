## Builders and Parsers

* Extensive support building and parsing HTML, XML and JSON.

## Building a XML file

```groovy
def stringWriter = new StringWriter()
def builder = new groovy.xml.MarkupBuilder(stringWriter)
builder.numbers {
    description 'Squares and factors of 10..15'
    for (i in 10..15) {
        number (value: i, square: i*i) {
            for (j in 2..<i) {
                if (i % j == 0) {
                    factor (value: j)
                }
            }
        }
    }
}
println stringWriter
```
---V

## Building a JSON file
```groovy
import groovy.json.*
import groovy.xml.*
 
class Player {
    String name
    List faveGrounds = []
}
 
class FaveGround {
    String ground
    String city
}
 
Player playr = new Player(name:"Sachin Tendulkar")
playr.faveGrounds << new FaveGround(ground: "Wankede", city:"Mumbai")
playr.faveGrounds << new FaveGround(ground: "SCG", city:"Sydney")

def builder = new JsonBuilder() 
def root = builder.players {
    player {
        name "${playr.name}"
 
        faveGrounds(
            playr.faveGrounds.collect{ 
               FaveGround faveGround -> [ground: faveGround.ground, city: faveGround.city]
            }    
        )
    }
}
println builder.toPrettyString()
```

---V

```xml
<langs type="languages">
  <language>Python</language>
  <language>Groovy</language>
  <language>Java</language>
</langs>
```

def langs = new XmlParser().parse("langs.xml")
println "type = ${langs.attribute("type")}"
langs.language.each{
  println it.text()
}
```