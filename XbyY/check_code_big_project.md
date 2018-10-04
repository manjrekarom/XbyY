# Problem Statement
## How to properly verify or check program snippets for mistakes in bigger projects?
If you are working on a big project you won't be able to make thorough checks to on code. That is because you can only check it by linking your program with the main application. But testing it with main application is again very ponderous and time consuming.

## Category
Software Development, Unit Testing [Category1, category2, ..]

## Solution
### Using unit tests 
You can use unit tests for this. You can write these unit tests once and keep. These unit tests run seperately on your program so you don't actually have to have a flow that connects your program from the main application i.e. calling your program from Main Application. Since tests run seperately from the main application, you can do all sorts of things in testing and that wouldn't matter since your production application will be crisp by itself (it won't have console log statements and other things that are needed to be done to check manually). This is also autonomous, in the way that you don't have to do manual checks everytime you change the code. The tests can be made to run when the program changes.

## Tutorial
This is a tutorial on unit testing in Java. http://tutorials.jenkov.com/java-unit-testing/index.html

### Author
[Omkar Manjrekar](github.com/manjrekarom)
