# bapp
The early workings for a new programming framework and package manager.
(This will probably end up terribly but it will be a fun experiment regardless. I'll probably never actually get around to creating it, but this is a start.)

The Bapp system will be built around BappScript, a new object-oriented programming language I eventually plan on creating. It will combine the best parts of both Scratch and Java into an easy-to-use and performant language. The syntax will be similar to Java, except with a few changes:

* when(condition){code} blocks - this block of code will execute when the condition is met, concurrently with any other code which is running; inspired by Scratch's "when I recieve message" block
* waitUntil(condition) blocks - this block of code will pause the thread until the condition is met
* simultaneously{} blocks - each line of code inside this block will run in its own thread
* Objects can call methods in the object which created them; this enables shared state
* Object constructors run concurrently by default
* Imports are objects

For more information, see the wiki I'll write soon.
