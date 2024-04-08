# Linx Style Guide

This style guide is for the low-code Linx Designer.

We spend much more time reading code than writing code. Conventions are there to improve software readability and allow developers to understand code faster and better.

Breaking with convention is allowed if it’s intentional. Always use the styles in this style guide except if doing so will make the code less understandable.

## Names

Names must clearly describe the object. Use `PascalCase` for all names. Don't use abbreviations except if they are well-known.

Guidelines for Linx components:
- Service: `[Noun]Service`, like `TimerService`.
- Type: `[Noun]`, like `Car`.
- Type property: `[Noun]`, like `Brand`.
- Boolean type property: `Is/Has[State]`, like `IsFast`.
- Function: `[Verb][Noun]`, like `GetCar`.
- Function parameter: `[Noun]`, like `Colour`.
- Setting: `[Noun]`, like `Key`.
- Variable: `[Noun]`, like `Car`.

## IfElse function

Name the IfElse function `If[Description]` and the conditions `[Verb][Noun]`, where the Verb reflects the boolean nature of the condition – words like Is, IsNot, Has, and Contains. Examples are

- Function: `IfWeather`, Conditions: `IsCold, IsWarm, IsRainy, IsDryAndWindy`.
- Function: `IfText`. Conditions: `ContainsLetters, ContainsNumbers, HasLessThanThreeCharacters`.