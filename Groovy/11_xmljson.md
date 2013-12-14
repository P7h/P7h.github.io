## Builders and Parsers

* Extensive support building and parsing HTML, XML and JSON.

---V

### Building a XML file

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

### Building a JSON file

```groovy
import groovy.json.*
 
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

### Reading an XML file

```xml
<langs type="languages">
    <language>Python</language>
    <language>Groovy</language>
    <language>Java</language>
</langs>
```

```groovy
def langs = new XmlParser().parse("langs.xml")
println "type = ${langs.attribute("type")}"
langs.language.each{
    println it.text()
}
```

---V

### Reading an XML file using XMLSlurper

```groovy
def CAR_RECORDS = '''
    <records>
      <car name='HSV Maloo' make='Holden' year='2006'>
        <country>Australia</country>
        <record type='speed'>Production Pickup Truck with speed of 271kph</record>
      </car>
      <car name='P50' make='Peel' year='1962'>
        <country>Isle of Man</country>
        <record type='size'>Smallest Street-Legal Car at 99cm wide and 59 kg in weight</record>
      </car>
      <car name='Royale' make='Bugatti' year='1931'>
        <country>France</country>
        <record type='price'>Most Valuable Car at $15 million</record>
      </car>
    </records>
  '''

def records = new XmlSlurper().parseText(CAR_RECORDS)

def allNodes = records.depthFirst().collect { 
    println it
}
```

---V

### Reading a JSON file JSONSlurper

```groovy
import groovy.json.*

def jsonText = '''
{
  "limit":{
    "track":1234
  }
}       
'''

def json = new JsonSlurper().parseText(jsonText)

def limit = json.limit
assert limit.track == 1234
```