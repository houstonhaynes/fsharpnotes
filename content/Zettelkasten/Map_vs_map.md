---
title: "Map vs map"
tags:
- fundamentals
---
This was one of the first things that *initially* confused me about F#. When I looked at 'map' I thought to myself "oh, this is like R" which was one of the languages I was using for machine learning projects. I had also encountered the "map" operation in Scala and Python, though they work differently in each language (see the following sub-heading below). But as soon as I saw capitalized "M" *'Map'* in F# I was a bit confused. 

## Map is a special type of collection

Pretty quickly I figured out that "Map" is like a dictionary in C#, and ordered collection of key-value pairs.

```fsharp
(* F# operation  *)
let myMap = Map.ofList [ ("apple", 1); ("banana", 2) ]
let value = myNewMap.["apple"]  // value will be 1
```

This is a list of key-value tuples which are fed into a Map. And while R doesn't have a specific "Map" construct, it *does* have the concept of a named list, which operates in much the same fashion.

```r
# this is R code 
dict <- list(apple = 1, banana = 2)
dict$apple  # Accesses the value 1
```

## Lower case 'm' map as an operation in F#

This is considered a higher-order function in F# and is part of the standard library. It applies a given function to each item in a list (or other 'mappable' collection), and returns a new collection containing the results. So the 'higher order' bit is about how map takes whatever function you pass to it so that the map operation can process each value in the collection through that function to render a new value.

```fsharp
(* F# operation that 'pipes' a list into a map operation that multiples each value by itself *)

[1; 2; 3; 4; 5] |> List.map (fun n -> n * n)

(* returns a new list of [1; 4; 9; 16; 25] *)
```

While the Python version of map is less used (as list comprehensions often replace it) the Scala implementation of 'map' is substantially similar to [the F# approach.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-mapmodule.html) Both Scala and Python, however, are used for applying a function to each element in a collection and generating a new collection based on the results.

While there's no 'map' in the core C# language, it offers something similar in the LINQ library with the 'Select' method.

```csharp
// C# operation over a list of individual values
using System;
using System.Linq;

class Program
{
    static void Main()
    {
        int[] numbers = { 1, 2, 3, 4, 5 };
        var squaredNumbers = numbers.Select(x => x * x).ToArray(); // Select method 
        
        // Output the squared numbers
        foreach (var num in squaredNumbers)
        {
            Console.WriteLine(num);
        }
    }
}
```
