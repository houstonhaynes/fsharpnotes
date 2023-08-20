---
title: "Map vs map"
tags:
- fundamentals
---
This was one of the first things that *initially* confused me about F#. When I looked at 'map' I thought to myself "oh, this is like R" which was one of the languages I was using for machine learning projects. I had also encountered the "map" operation in Scala and Python, though they work differently in each language (see the following sub-heading below). But as soon as I saw capitalized "M" *'Map'* in F# I was a bit confused. 

## Map is a special type of collection

Pretty quickly I figured out that "Map" is like a dictionary in C#, an ordered collection of key-value pairs. Here's a brief example of a Map in F#.

```fsharp {title="F# Map creation and value access", linenos=false}
let myMap = Map.ofList [ ("apple", 1); ("banana", 2) ]
let value = myMap.["apple"]  // value will be 1
```

This is a list of key-value tuples which create the Map. And while R doesn't have a specific "Map" construct, it *does* have the concept of a 'named list', which operates in much the same fashion.

```r {title="R named list creation and value access", linenos=false}
dict <- list(apple = 1, banana = 2)
dict$apple  # Accesses the value 1
```

This may wander into the deeper 'R' waters of hash map creation which is out of scope here. But from the 'dict' abbreviation it could be surmised that named lists are often referred to as 'dictionaries'. Those happen to exist in C# as a core collection type.

```csharp {title="C# Dictionary creation and value access", linenos=false}
using System;
using System.Collections.Generic;

public class MyDictionaryClass
{
    private Dictionary<string, int> MyDict { get; }

    public MyDictionaryClass()
    {
        MyDict = new Dictionary<string, int>
        {
            { "apple", 1 },
            { "banana", 2 }
        };
    }

    public int? GetValueByKey(string key)
    {
        if (MyDict.TryGetValue(key, out int value))
        {
            return value;
        }
        else
        {
            return null;
        }
    }
}

MyDictionaryClass myDictClass = new MyDictionaryClass();
int? value = myDictClass.GetValueByKey("apple"); // Should return 1
int? nonExistentValue = myDictClass.GetValueByKey("orange"); // Should return null
```

Once I had this sorted out things quickly fell into place.

## Lower case 'm' map as an operation in F#

This is considered a higher-order function in F# and is part of the standard library. It applies a given function to each item in a list (or other 'mappable' collection), and returns a new collection containing the results. So the 'higher order' bit is about how map takes whatever function you pass to it so that the map operation can process each value in the collection through that function to render a new value.

```fsharp {title="F# map operation over a list of integers", linenos=false}
[1; 2; 3; 4; 5] |> List.map (fun n -> n * n)

(* returns a new list of [1; 4; 9; 16; 25] *)
```

As a side note, the Python version of map is less used (as list comprehensions often replace it) the Scala implementation of 'map' is substantially similar to [the F# approach.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-mapmodule.html) Both Scala and Python, however, are used for applying a function to each element in a collection and generating a new collection based on the results.

While there's no 'map' in the core C# language, it offers something similar in the LINQ library with the 'Select' method.

```csharp {title="C# operation over a list of individual values", linenos=false}
using System.Collections.Generic;
using System.Linq;

public class NumberOperations
{
    private int[] numbers;

    public NumberOperations(int[] numbers)
    {
        this.numbers = numbers;
    }

    public List<int> GetSquaredNumbers()
    {
        return numbers.Select(x => x * x).ToList();
    }
}

NumberOperations numOps = new NumberOperations(new int[] { 1, 2, 3, 4, 5 });
List<int> squaredNumbers = numOps.GetSquaredNumbers(); 
// Should return a list containing [1, 4, 9, 16, 25]

```

## Less is More

One aspect that continues to surface with F# is its brevity - both its incredibly strong type inference and 'functional first' posture makes for very succinct code. Here, in this case, the **moment** of confusion led to a really expansive view of how well organized the F# language has been for nearly 20 years. Once you start looking at comparisons to other languages the relatively *low* cognitive burden of F# becomes one of its major advantages.
