# Java-Code-Collection
Collection of Java code-snippets that are good to know by heart! 
Knowing these things will help you in code interviews, and in situations where you don't have access to Google,
but still need to do Java (Such as in an apocalypse)

# How to iterate through a HashMap?

```java
public class JavaGoodToKnow(){

	private HashMap<String, Integer> personToAge = new HashMap<>();
    
    public JavaGoodToKnow(){
        personToAge.put("Bill", 62);
        personToAge.put("Lana", 26);
        personToAge.put("Jeff", 54);
    }
    
     public void iterateThroughMap(){
        //Keys only
        for(String key : personToAge.keySet()){
            //Do something with each key
        }

        //Values only
        for(Integer value : personToAge.values()){
            //Do something with each value
        }

        //Keys and values
        for(Map.Entry<String, Integer> entry : personToAge.entrySet()){
            String name = entry.getKey();
            int age = entry.getValue();
            
            //Do something with keys and values
        }
    }

}

``` 

# How to use lambda expressions to sort objects?

import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

```java

public class JavaGoodToKnow {

    private ArrayList<Person> persons;

    public JavaGoodToKnow(){
        this.persons = new ArrayList<>();

        persons.add(new Person("Bill", 65, 'M'));
        persons.add(new Person("Ali", 38, 'M'));
        persons.add(new Person("Cathrine", 33, 'F'));
    }

    public void sortPersonList(){
        persons.sort((a, b) -> a.getName().compareTo(b.getName()));
    }

}

``` 

# How to use lambda expressions and streams to filter objects?

```java

import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

public class JavaGoodToKnow {

    private ArrayList<Person> persons;

    public JavaGoodToKnow(){
        this.persons = new ArrayList<>();

        persons.add(new Person("Bill", 65, 'M'));
        persons.add(new Person("Ali", 38, 'M'));
        persons.add(new Person("Cathrine", 33, 'F'));
    }

	//Creates a new list containing persons that are over forty
    public void filterAndCollect(){
       List<Person> overForty = persons.stream().filter(p -> p.getAge() > 40).collect(Collectors.toList());
    }
}

``` 

# How to use lambda expressions and streams to call a method on each object in a list?

```java
public class JavaGoodToKnow {

    private ArrayList<Person> persons;

    public JavaGoodToKnow(){
        this.persons = new ArrayList<>();

        persons.add(new Person("Bill", 65, 'M'));
        persons.add(new Person("Ali", 38, 'M'));
        persons.add(new Person("Cathrine", 33, 'F'));
    }

	//Creates a new list that only contains ages of people
    public void operationOnEveryObject(){
        List<Integer> ages = persons.stream().map(Person::getAge).collect(Collectors.toList());
    }
}


``` 
