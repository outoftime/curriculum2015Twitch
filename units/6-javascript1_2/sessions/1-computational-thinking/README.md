#Lesson 1 - Computational Thinking

![image](http://cdn.idigitaltimes.com/sites/idigitaltimes.com/files/2015/06/08/r2d2-and-c3po-star-wars.jpg)

## Before Class

### Objective

Students will be able to analyze and predict the runtime behavior of JavaScript
code using environment diagrams.

### Key Points

* Computer programs run in sequence; at any given time, the program is
  evaluating one line of code
* At each line of the computer program, the program has a certain set of
  variables and functions defined. This is called the **environment**
* We can use environment diagrams to step through code and predict how it will
  behave, without having to run it on a computer.

### Assessment

Students will show progress toward reaching the objective based on their performance on the exit ticket.

### Vocabulary

* Environment
* Scope
* Local scope
* Global scope

### References

* http://albertwu.org/cs61a/notes/environments (college-level material, good
  for mentors, probably too advanced for students)

## During Class

### Do Now

1. Volunteer takes attendance. [Procedure found here](https://docs.google.com/document/d/19IIhqykr70vj7wnqyJYuQNTkd9GX56Xgl3omD42IcMk/edit).
2. [Do Now](assessments/do_now.md) Activity

### Opening

Today we will learn a technique for figuring out what JavaScript code is going
to do without having to run the code on a computer. Being able to reason about
the way code runs will help us become better programmers, especially when we
are trying to find bugs in our code.

### Introduction to New Material ("I Do")

#### Environment diagrams

On the left half of the board, write the code from the Do Now, except with a
descriptive name for the function:

```javascript
function square(i) {
  var answer = i * i;
  return answer;
}

var num1 = 5;
var num2 = square(num1);
```

Write line numbers to the left of each line of code, ideally in a different
color pen. Also label the blank “line 8” at the very end.

On the right side of the board, write a table with the headers **Line**,
**Global**, and **Local**:

Line | Global | Local
----:|--------|------
6    |        |

Explain that we’re going to solve the problem by following a specific
procedure, using the diagram you just drew. Tell the class that this is called
an environment diagram.

Give the definition of **environment** as the set of variables and functions
that are defined at a certain point in the code. The environment diagram is a
way to keep track of the program’s environment as we step through the code.

Prompt the students for the first line of code that will actually run. If they
do not correctly respond that it is line 6, remind them that a function is
defined as a piece of code that *only runs when called*; so the first code to
run has to be outside any function definition.

Now demonstrate drawing the environment diagram after line 4 executes:

Line | Global   | Local
----:|----------|------
6    |          |
7    | num1 [5] |

Draw the value of `num1` (4) in a box, then write the name of the variable to
the left of the box.

#### Local scope and function calls

Point out that, because line 7 contains a function call, we will jump to the
first line of the body of that function:

Line | Global   | Local
----:|----------|------
6    |          |
7    | num1 [5] |
2    | num1 [5] | i [5]

Emphasize that in environment diagrams, function parameters are treated exactly
like variables that we defined with `var` and assigned with `=`.

At this point, give the definition of *global* and *local* scope. Explain that
variables that are declared *outside of any function* are in the **global
scope**. Variables declared *inside a function, including function parameters*,
are in **local scope**.

There is no need to dwell on the finer points of lexical scoping and function
closures at this point.

Move on to the next line:

Line | Global   | Local
----:|----------|------
6    |          |
7    | num1 [5] |
2    | num1 [5] | i [5]
3    | num1 [5] | i [5]<br>answer [25]

### Guided Practice ("We Do")

### Independent Practice ("You Do")

#### Exit Ticket

Give [exit ticket](assessments/exit_ticket.md).

### Closing

## After Class

* Review student Do Now and Exit Tickets.
* Prepare for next lesson / hand off to next volunteer in rotation.

