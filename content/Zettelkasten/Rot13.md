---
title: "ROT13 Algorithm"
tags:
- fundamentals
- recursion
---
## A gentle introduction to algorithms in F#

The 'ROT13' algorithm is an introductory lesson in obfuscation that 'rotates' the alphabet by 13 positions (half of the full length of 26 characters) to create a new, harder-to-read result. It serves as an initial model for those that are new to cryptography to work out through inductive reasoning. 

```fsharp
(* Rot13 implemented in F# *)

open System.Text

let rotChar (c:char) offset = int c + offset |> char

let rot13 (str:string) =
    let rec rot (str:char list) (sb:StringBuilder) =
        match str with
        | [] -> sb.ToString()
        | c::cs -> match int c with
                   | cCode when (cCode > 77 && cCode <= 90) || (cCode > 109 && cCode <= 122) -> rot cs (rotChar c -13 |> sb.Append)
                   | _ -> rot cs (rotChar c 13 |> sb.Append)
        
    rot (str.ToCharArray() |> List.ofArray) (StringBuilder())


(* Calling the function to evaluate rot13 algorithm *)

printfn "%s" (rot13 "zlatan")

(* returns "myngna" *)

```

While this is *simple* in terms of algortithmic processing, this example also shows how recursive processing is structured in F#. 

[Source](https://github.com/AllAlgorithms/fsharp/blob/master/algorithms/ciphers/rot13.fsx)
