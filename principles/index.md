# Software development principles for low-code

## Introduction
Using Linx or Stadium to do low-code development is just like using a modern programming language, but at a higher level. You can do most of the same things, just faster, which means it can get out of hand faster as well.

The following principles are there to help us navigate our way through the trade-offs we're constantly making when developing software. The code smells help us recognise when we've gone astray.

## Principles
Software development principles provide a framework for decision-making throughout the development process, influencing design, implementation, and maintenance.

- **KISS (Keep It Simple, Stupid)**: Avoid unnecessary complexity. Remember, no code is better than code, and code will be read much more than it will be changed
- **DRY (Don't Repeat Yourself)**: Don't write the same code in multiple places. This principle promotes reusability
- **YAGNI (You Aren't Gonna Need It)**: Only implement what you need now. Don’t implement things you think you might need. Also see KISS
- **SRP (Single Responsibility Principle)**: Every function, type, folder, service, or solution should have a single clearly defined responsibility
- **PLK (Principle of Least Knowledge)**: A function or type should know as little as possible about its surroundings. In other words, avoid dependencies on things not passed in as parameters
- **FF (Fail Fast)**: Fail quickly when an error occurs. Only catch exceptions when you know how to handle it
- **PLA (Principle of Least Astonishment)**: Readers of your code should not be surprised by the contents of a function, type, folder, or solution
- **BSR (Boy Scout Rule)**: Always leave the code cleaner than when you found it

## Code smells
Code smells are characteristics of software that indicate a deeper problem in the code. They are not bugs — they don't stop the program from functioning — but they are indicators of poor design or implementation choices that can negatively affect the software's maintainability, readability, and overall quality. Code smells are the result of principles not followed. Here's a list of common code smells:

- **Shotgun Surgery**: The need to make many changes in different parts of the codebase to achieve a single functionality change. [DRY, SRP]
- **Long Function**: Functions that are too long, making them hard to understand and maintain. [KISS]
- **Large Type**: A type that tries to do too much, often containing too many fields. [KISS]
- **Long Parameter List**: Functions that require a high number of parameters, which can make them difficult to understand and use. [KISS]
- **Data Clumps**: Groups of variables that are frequently used together and can be combined into a more cohesive object. [DRY]
- **Speculative Generality**: Writing code that is used to handle future, hypothetical scenarios but is not needed currently. [YAGNI]
- **Temporary Field or Variable**: Fields or Variables that are only set in certain conditions. Their presence can be confusing since they are not always used. [SRP, PLA]
- **Lazy Function**: A function that doesn’t do enough to justify its existence and should be refactored or removed. [KISS, YAGNI]
- **Inappropriate Intimacy**: A function dependent on resources unrelated to its purpose. [PLK]
- **Divergent Change**: When one function is often changed in different ways for different reasons. [SRP]
- **Message Chains**: A function that requests a chain of other functions, creating a tightly coupled chain between different areas. [PLK, KISS, YAGNI]
- **Middleman**: A function that does nothing but delegate to another function. [KISS, PLA, YAGNI]