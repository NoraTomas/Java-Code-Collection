# Java-Code-Collection
Collection of Java code-snippets that are good to know by heart! 
Knowing these things will help you in code interviews, and in situations where you don't have access to Google,
but still need to do Java (Such as in an apocalypse)

# How to iterate through a HashMap?

```java
private HashMap<String, Integer> personToAge = new HashMap<>();

public class JavaGoodToKnow(){
    
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
            
            //Do something with keys an values
        }
    }

}

``` 