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
* Functions can access data and call other functions but can't modify data or call procedures (except procedures which are part of objects which were constructed inside the object's scope), so don't have any side-effects, improving maintainability and reusability; they can't modify any parameters or call any procedures in objects which are passed as parameters
* Functions can be static or exist inside objects but procedures and variables can only exist inside objects
* Imports are objects

These changes make code more maintainable and they improve performance through the use of concurrency.
For more information, see the wiki I'm writing.

oh also in addition there will be the option to use a block-based language similar to Scratch and to do drag-and-drop UI design in the ShapeShift editor
but that's late-stage and we probably won't get there for years
first we need to design the language, then write the compiler and the WebGPU runtime, which should hopefully be done by the end of 2026 (although knowing me it probably won't and I may not have even gotten started), and also create a portable packaging format which runs everywhere and create a runtime based on wasmtime (that'll be easy once we've done the compiler since we can just get LLVM to generate WebAssembly code and then run it in wasmtime and the gui can be rendered by idk I'll figure it out I'll probably use WebGPU), then we'll be halfway there.
then we just gotta create a system which will enable widgets to be imported from Dart and React, and then import some standard widgets or make our own, and then it will basically be ready (except it won't run on Apple devices but eh they can make their own runtime)
the goal is to enable developers to write their program once, using a standard set of widgets, and then it will automatically style those widgets to follow each platform's UI guidelines but that's still years away

but also just to illustrate the point of how hard concurrency is in other languages and why BappScript's system is needed: Scratch and Greenfoot don't even bother with multithreaded concurrency. They fake it. And even Turbowarp, which is optimised for performance, fakes concurrency. (I got this information from Grok so it may not be fully accurate)
no wonder most software is so slow
<img width="2024" height="1598" alt="image" src="https://github.com/user-attachments/assets/978b9386-86b6-49f9-a77a-1bf7dea6ee41" />

<img width="2024" height="1598" alt="image" src="https://github.com/user-attachments/assets/cec3f1e8-9836-49eb-8d1e-e2496a91f35b" />
