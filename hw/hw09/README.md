 Homework 9: Programs as Data, Macros[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#homework-9-programs-as-data-macros "Direct link to Homework 9: Programs as Data, Macros")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   [hw09.zip](https://www.learncs.site/assets/files/hw09-79d4a7fb62d63538c4cff2da66480a98.zip)

_Due by 11:59pm on Thursday, April 25_

Instructions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#instructions "Direct link to Instructions")
---------------------------------------------------------------------------------------------------------------------------------

Download [hw09.zip](https://www.learncs.site/assets/files/hw09-79d4a7fb62d63538c4cff2da66480a98.zip). Inside the archive, you will find a file called [hw09.scm](https://cs61a.org//hw/hw09/hw09.scm), along with a copy of the `ok` autograder.

**Submission:** When you are done, submit the assignment by uploading all code files you've edited to Gradescope. You may submit more than once before the deadline; only the final submission will be scored. Check that you have successfully submitted your code on Gradescope. See [Lab 0](https://cs61a.org/lab/lab00#task-c-submitting-the-assignment) for more instructions on submitting assignments.

**Using Ok:** If you have any questions about using Ok, please refer to [this guide.](https://cs61a.org/articles/using-ok)

**Readings:** You might find the following references useful:

*   [Scheme Specification](https://cs61a.org/articles/scheme-spec/)
*   [Scheme Built-in Procedure Reference](https://cs61a.org/articles/scheme-builtins/)

**Grading:** Homework is graded based on correctness. Each incorrect problem will decrease the total score by one point. **This homework is out of 2 points.**

The 61A Scheme interpreter is included in each Scheme assignment. To start it, type `python3 scheme` in a terminal. To load a Scheme file called `f.scm`, type `python3 scheme -i f.scm`. To exit the Scheme interpreter, type `(exit)`.

### Scheme Editor[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#scheme-editor "Direct link to Scheme Editor")

All Scheme assignments include a web-based editor that makes it easy to run ok tests and visualize environments. Type `python3 editor` in a terminal, and the editor will open in a browser window (at `http://127.0.0.1:31415/`). To stop running the editor and return to the command line, type `Ctrl-C` in the terminal where you started the editor.

The `Run` button loads the current assignment's `.scm` file and opens a Scheme interpreter, allowing you to try evaluating different Scheme expressions.

The `Test` button runs all ok tests for the assignment. Click `View Case` for a failed test, then click `Debug` to step through its evaluation.

### Recommended VS Code Extensions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#recommended-vs-code-extensions "Direct link to Recommended VS Code Extensions")

If you choose to use VS Code as your text editor (instead of the web-based editor), install the [vscode-scheme](https://marketplace.visualstudio.com/items?itemName=sjhuangx.vscode-scheme) extension so that parentheses are highlighted.

Before:

![](https://www.learncs.site/assets/images/before-1fb62971706b817f8b61c7a23705e08a.png)

After:

![](https://www.learncs.site/assets/images/after-49c28554ee03a6642fe04e111fd59fd5.png)

In addition, the 61a-bot ([installation instructions](https://cs61a.org/articles/61a-bot)) VS Code extension is available for Scheme homeworks. The bot is also integrated into `ok`.

Required Questions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#required-questions "Direct link to Required Questions")
---------------------------------------------------------------------------------------------------------------------------------------------------

Getting Started Videos[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#getting-started-videos "Direct link to Getting Started Videos")
---------------------------------------------------------------------------------------------------------------------------------------------------------------

These videos may provide some helpful direction for tackling the coding problems on this assignment.

> To see these videos, you should be logged into your berkeley.edu email.

[YouTube link](https://youtu.be/playlist?list=PLx38hZJ5RLZcRCa7WhQVKh5s5ZLfGV9hc)

Programs as Data: Chef Curry[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#programs-as-data-chef-curry "Direct link to Programs as Data: Chef Curry")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Recall that currying transforms a multiple argument function into a series of higher-order, one argument functions. In the next set of questions, you will be creating functions that can automatically curry a function of any length using the notion that programs are data!

### Q1: Cooking Curry[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#q1-cooking-curry "Direct link to Q1: Cooking Curry")

Implement the function `curry-cook`, which takes in a Scheme list `formals` and a quoted expression `body`. `curry-cook` should generate a program as a list which is a curried version of a lambda function. The outputted program should be a curried version of a lambda function with formal arguments equal to `formals`, and a function body equal to `body`. You may assume that all functions passed in will have more than 0 `formals`; otherwise, it would not be curry-able!

For example, if you wanted to curry the function `(lambda (x y) (+ x y))`, you would set `formals` equal to `'(x y)`, the `body` equal to `'(+ x y)`, and make a call to `curry-cook`: `(curry-cook '(x y) '(+ x y))`.

    scm> (curry-cook '(a) 'a)(lambda (a) a)scm> (curry-cook '(x y) '(+ x y))(lambda (x) (lambda (y) (+ x y)))

    (define (curry-cook formals body)    'YOUR-CODE-HERE)

Use Ok to test your code:

    python3 ok -q curry-cook

### Q2: Consuming Curry[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#q2-consuming-curry "Direct link to Q2: Consuming Curry")

Implement the function `curry-consume`, which takes in a curried lambda function `curry` and applies the function to a list of arguments `args`. You may make the following assumptions:

1.  If `curry` is an `n`\-curried function, then there will be at most `n` arguments in `args`.
2.  **If there are 0 arguments** (`args` is an empty list), then you may assume that `curry` has been fully applied with relevant arguments; in this case, `curry` now contains a value representing the output of the lambda function. Return it.

Note that there can be fewer `args` than `formals` for the corresponding lambda function `curry`! In the case that there are fewer arguments, `curry-consume` should return a curried lambda function, which is the result of partially applying `curry` up to the number of `args` provdied. See the doctests below for a few examples.

    scm> (define three-curry (lambda (x) (lambda (y) (lambda (z) (+ x (* y z)))) ))three-curryscm> (define eat-two (curry-consume three-curry '(1 2))) ; pass in only two arguments, return should be a one-arg lambda function!eat-twoscm> eat-two(lambda (z) (+ x (* y z)))scm> (eat-two 3) ; pass in the last argument; 1 + (2 * 3)7scm> (curry-consume three-curry '(1 2 3)) ; all three arguments at once7

    (define (curry-consume curry args)    'YOUR-CODE-HERE)

Use Ok to test your code:

    python3 ok -q curry-consume

Macros[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#macros "Direct link to Macros")
---------------------------------------------------------------------------------------------------------------

### Q3: Switch to Cond[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#q3-switch-to-cond "Direct link to Q3: Switch to Cond")

`switch` is a macro that takes in an expression `expr` and a list of pairs, `options`, where the first element of each pair is some value and the second element is a single expression. `switch` evaluates the expression contained in the list of `options` that corresponds to the value that `expr` evaluates to.

    scm> (switch (+ 1 1) ((1 (print 'a))                      (2 (print 'b)) ; (print 'b) is evaluated because (+ 1 1) evaluates to 2                      (3 (print 'c))))b

`switch` uses another procedure called `switch-to-cond` in its implementation:

    scm> (define-macro (switch expr options)                   (switch-to-cond (list 'switch expr options))     )

Your task is to define `switch-to-cond`, which is a procedure (not a macro) that takes a quoted `switch` expression and converts it into a `cond` expression with the same behavior. An example is shown below.

    scm> (switch-to-cond `(switch (+ 1 1) ((1 2) (2 4) (3 6))))(cond ((equal? (+ 1 1) 1) 2) ((equal? (+ 1 1) 2) 4) ((equal? (+ 1 1) 3) 6))

    (define-macro (switch expr options) (switch-to-cond (list 'switch expr options)))(define (switch-to-cond switch-expr)  (cons _________    (map      (lambda (option) (cons _______________ (cdr option)))      (car (cdr (cdr switch-expr))))))

Use Ok to test your code:

    python3 ok -q switch-to-cond

Check Your Score Locally[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#check-your-score-locally "Direct link to Check Your Score Locally")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

You can locally check your score on each question of this assignment by running

    python3 ok --score

**This does NOT submit the assignment!** When you are satisfied with your score, submit the assignment to Gradescope to receive credit for it.

Submit[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#submit "Direct link to Submit")
---------------------------------------------------------------------------------------------------------------

Submit this assignment by uploading any files you've edited **to the appropriate Gradescope assignment.** [Lab 00](https://cs61a.org/lab/lab00/#submit-with-gradescope) has detailed instructions.

In addition, all students who are **not** in the mega lab must complete this [attendance form](https://go.cs61a.org/lab-att). Submit this form each week, whether you attend lab or missed it for a good reason. The attendance form is not required for mega section students.

Exam Practice[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw09#exam-practice "Direct link to Exam Practice")
------------------------------------------------------------------------------------------------------------------------------------

Homework assignments will also contain prior exam questions for you to try. These questions have no submission component; feel free to attempt them if you'd like some practice!

Macros

1.  Fall 2019 Final Q9: [Macro Lens](https://cs61a.org/exam/fa19/final/61a-fa19-final.pdf#page=10)
2.  Summer 2019 Final Q10c: [Slice](https://cs61a.org/exam/su19/final/61a-su19-final.pdf#page=10)
3.  Spring 2019 Final Q8: [Macros](https://cs61a.org/exam/sp19/final/61a-sp19-final.pdf#page=8) 