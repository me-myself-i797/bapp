# bapp
The early workings for a new programming framework and package manager.
(This will probably end up terribly but it will be a fun experiment regardless. I'll probably never actually get around to creating it, but this is a start.)

This project follows the principles of documentation-driven development: we start by writing the documentation which describes how the project will work, and then once we've finished writing the documentation, we will write the compiler.

The Bapp system will be built around BappScript, a new object-oriented programming language I eventually plan on creating. It will combine the best parts of both Scratch and Java into an easy-to-use and performant language. The syntax will be similar to Java, except with a few changes:

* when(condition){code} blocks - this block of code will execute when the condition is met, concurrently with any other code which is running; inspired by Scratch's "when I recieve message" block
* waitUntil(condition) blocks - this block of code will pause the thread until the condition is met
* simultaneously{} blocks - each line of code inside this block will run in its own thread
* Objects can call methods in the object which created them; this enables shared state
* All procedures run concurrently with the calling code, including object constructors
* Functions can access data and call other functions but can't modify data or call procedures, so don't have any side-effects, improving maintainability and reusability
* Functions can be static or exist inside objects but procedures and variables can only exist inside objects
* Imports are objects

These changes make code more maintainable and they improve performance through the use of concurrency.
For more information, see the wiki I'm writing.
