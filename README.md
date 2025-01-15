# A Philosophy of Software Design

Notes on the book A Philosophy of Software Design, John K, Ousterhout, Yaknyam Press (2021).

## Book Details

**Title** A Philosophy of Software Design  
**Author** John K. Ousterhout  
**Publisher** Yaknyam Press, 2021  
**Length** 190 Pages  

## Motivation For Reading

Book is about the bigger picture of software design which to this day is a topic not often covered in literature or courses, despite being important for efficient software development. 

The book have generally been well received and it being short it seems obvious that it is worth the time to read this book.

## Red Flags

List of topics that the author calls red flags, that should be avoided in the code base.

### &#x1F6A9; Shallow Module &#x1F6A9;

> A shallow module is one whose interface is complicated relative to the functionality it provides. Shallow modules don’t help much in the battle against complexity, because the benefit they provide (not having to learn about how they work internally) is negated by the cost of learning and using their interfaces. Small modules tend to be shallow.

Shallow modules is an indication of design that could be improved upon. The complicated interface increases the time it takes to learn how to use the module. Shallow modules also tend to leak information about the underlying implementation that can create coupling, making it impossible to refactor the module without also having to refactor all the modules that use the module.

### &#x1F6A9; Information Leakage &#x1F6A9;

> Information leakage occurs when the same knowledge is used in multiple places, such as two different classes that both understand the format of a particular type of file.

This is probably very common existing code bases that I have worked with but did not understand that this is a problem. Need to be on the look-out for this and ensure to avoid it. Can see now how this hampers maintainability by introducing a hidden dependency between the classes.

### &#x1F6A9; Temporal Decomposition ### &#x1F6A9;

> In temporal decomposition, execution order is reflected in the code structure: operations that happen at different times are in different methods or classes. If the same knowledge is used at different points in execution, it gets encoded in multiple places, resulting in information leakage.

The word temporal relates to something time-related, like in which order something occurs in time. Example of temporal decomposition is to have one class that provides a interface to open a connection to something and then have the closing of the connection in another class. This should be avoided, both open and close of the connection belongs to the same class. That open and close occurs in different point in time does not matter.

### &#x1F6A9; Repetition ### &#x1F6A9;

> A similar piece of code appearing over and over again indicates room for improvement of abstractions.

The code can be broken out to a function to resolve this issue. Another way to resolve this can be to have `goto` statement. Even if `goto` should generally be avoided so can it be useful for error handling, making it possible to separate the normal flow of the code from error handling parts.

### &#x1F6A9; Conjoined Functions ### &#x1F6A9;

> A function shall be possible to understand in isolation.

If you can't understand the implementation of one function without also understanding the implementation of another, there is a problem with the design.

