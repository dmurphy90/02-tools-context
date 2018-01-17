**Questions:**
**1. When this code is run in Node, e.g. node index.js, what are the two stages of execution for this file called, and which order do they happen in?**
The two stages of execution are the creation stage and the activation/execution stage, the creation stage occurs first followed by the execution stage when functions are called upon.


**2. Write an explanation, using as much space as you need, relating to how the first stage of execution for this file operates.**
The first stage, the creation stage, runs through your files and when it comes across a function being called it enters into the scope of the function and creates a new execution context at the top of the stack. When it hits line 8 it encounters a new nested function and creates another execution stack pushing that to the top.


**-For example, identify the high level steps in a line by line overview and then define what each of those steps are accomplishing.**
Line 3 defines that there is a global variable named foo
Line 5 defines there there is a function bar()
Line 16 the function bar is called upon and another execution stack is entered within the function bar() and the properties have values assigned
Line 13 the function baz() is called upon and another execution stack is entered and properties have been assigned with foo being overwritten again
Line 6 is redefining the variable foo within the scope of function bar()
Line 8 defines that there is a function named baz() which is taking in the argument of foo from the function bar()
Line 17 the variable foo which has been changed by bar is printed
Line 18 the variable bam is called upon which has been defined by baz()

**3. Write an explanation, using as much space as you need, relating to how the second stage of execution for this file operates.**
The second stage, the activation/code execution stage, begins when it hits a function that is called upon. It then creates a new execution scope within the function and assigns any properties within the function that have remained largely undefined so far.

**-For example, identify the high level steps in a line by line overview and then define what each of those steps are accomplishing.**
Line 3 defines that there is a global variable named foo
Line 5 defines there there is a function bar()
Line 16 the function bar is called upon and another execution stack is entered within the function bar() and the properties have values assigned
Line 13 the function baz() is called upon and another execution stack is entered and properties have been assigned with foo being overwritten again
Line 6 is redefining the variable foo within the scope of function bar()
Line 8 defines that there is a function named baz() which is taking in the argument of foo from the function bar()
Line 17 the variable foo which has been changed by bar is printed
Line 18 the variable bam is called upon which has been defined by baz()


**4.During the second stage of execution how many scopes have been registered by the engine?**
During the second stage 2 scopes have been registered by the enegine
**-Which segments of the code do they belong to?**
The first new scope for bar belongs to lines 5 through 14, and the second new scope belongs to lines 8 through 12
**-Please identify any variables/refs and which scope each belongs to?**
Var foo belongs to global, then belongs to bar() when it is redefined, and finally blongs to baz() when redefined again. Var bam belongs exclusively to the scope of baz()

**5.When line 13 invokes the baz function, which foo will be assigned a value of bam? More specifically, bam will be assigned to the foo in ??? scope. Give a brief description in your own words to support your conclusion.**
Bam will be assigned to the scope of foo in baz() since it is being reassigned on the most recent execution stack and is the last reassignment of the variable foo

**6. Which scope, if any, will the variable bam on line 11 be registered to when the first stage of execution occurs on this file? Provide a brief description in your own words to support your conclusion.**
The variable bam will be assigned to the global scope first since it has not encountered any function calls to begin a new execution context within the stack.

**7. For each line, 16 through 19, what is the return value for each?**
Line 16 returns undefined
Line 17 returns "bar"
Line 18 returns "yay"
Line 19 gives me an error saying baz is not defined because it is declared inside of bar