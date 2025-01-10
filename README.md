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

### &#x1F6A9; Information Leakage &#x1F6A9;

> Information leakage occurs when the same knowledge is used in multiple places, such as two different classes that both understand the format of a particular type of file.

This is probably very common existing code bases that I have worked with but did not understand that this is a problem. Need to be on the look-out for this and ensure to avoid it. Can see now how this hampers maintainability by introducing a hidden dependency between the classes.
