---
title: Maps Explained
layout: post
date: 2014-11-18 20:00:00
categories: java tutorial
---

## What are maps?

Well, to quote the AP textbook:

> The `Map` interface in the Java standard class library matches--or maps--keys to values. An example of a map is a dictionary: the keys in the map are words and the values are definitions. Each word in the dictionary maps to its definition. Duplicate keys are not allowed (dictionaries are long enough as it is without repeating words!), so the keys in a map form a set.

>*Java Software Solutions for AP Computer Science, 3rd Edition, p. 510*

I think this explains it pretty clearly. Essentially, a map is a data structure that allows us to store certain data and then retrieve it based on a key.

## How do they work in Java?

Remember the concept of *abstraction*? Basically, abstraction allows different objects to provide programmers with the same access methods. It doesn't matter to you how the data is actually stored, but you can still access it in the same way.

Java applies this concept to maps. There are a bunch of different implementations of the generic [Map](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html) interface, including [HashMap](https://docs.oracle.com/javase/7/docs/api/java/util/HashMap.html), [TreeMap](https://docs.oracle.com/javase/7/docs/api/java/util/TreeMap.html), and [EnumMap](https://docs.oracle.com/javase/7/docs/api/java/util/EnumMap.html). While this may seem complicated, don't worry; these all have the same methods associated with them, they just store data differently at a low level. If you're interested, just take a look at the documentation linked above.

## How do I actually program with them?

Any `Map` is created in the same way.

{% highlight java %}
Map<KeyType, ValueType> exampleMap = new Map<KeyType, ValueType>();
{% endhighlight %}

This will create a new `Map` with keys of type `KeyType` and values of type `ValueType`. It may look complicated, but it really isn't so bad.

In a real program, you would replace `Map` with your chosen implementation. For instance,

{% highlight java %}
HashMap<Integer, String> hashMap= new HashMap<Integer, String>();
{% endhighlight %}

creates a HashMap with `Integer` keys and `String` values.

There are just a few functions associated with `Map`s that you need to know.

{% highlight java %}
// Returns the value stored at key
Map.get(key);

// Sets the value at key
Map.put(key, value);

// Removes a given key
Map.remove(key);

// Returns true if the Map contains the given value
Map.contains(value);

// Returns the number of elements in the Map
Map.size();

// Returns a Set containing all keys
Map.keySet();

// Returns true if a Map contains a given key
Map.containsKey(key);
{% endhighlight %}

It is unlikely that you will need the last two, but I have included them for completeness' sake.

## `EnumMap`

`EnumMap` is something of a special case. Structurally, it is very similar to a `HashMap`. However, it contains special optimizations for maps that use enumerated types as keys. As a result, it is significantly faster than using a `HashMap` for this same case.

## A Basic Example

Finally, here is a basic example of the usage of a `HashMap`.
 
 {% highlight java %}
/**
 * Source: http://www.java2novice.com/java-collections-and-util/hashmap/basic-operations/
 */
import java.util.HashMap;
 
public class MyBasicHashMap {
 
    public static void main(String a[]){
        HashMap<String, String> hm = new HashMap<String, String>();
        //add key-value pair to hashmap
        hm.put("first", "FIRST INSERTED");
        hm.put("second", "SECOND INSERTED");
        hm.put("third","THIRD INSERTED");
        System.out.println(hm);
        //getting value for the given key from hashmap
        System.out.println("Value of second: "+hm.get("second"));
        System.out.println("Is HashMap empty? "+hm.isEmpty());
        hm.remove("third");
        System.out.println(hm);
        System.out.println("Size of the HashMap: "+hm.size());
    }
}
{% endhighlight %}

The output of this will be

    {second=SECOND INSERTED, third=THIRD INSERTED, first=FIRST INSERTED}
    Value of second: SECOND INSERTED
    Is HashMap empty? false
    {second=SECOND INSERTED, first=FIRST INSERTED}
    Size of the HashMap: 2