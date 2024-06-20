Homework 8: Scheme Lists[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#homework-8-scheme-lists "Direct link to Homework 8: Scheme Lists")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   [hw08.zip](https://www.learncs.site/assets/files/hw08-912d428eb7876001702e96d040d986ca.zip)

_Due by 11:59pm on Thursday, April 11_

Instructions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#instructions "Direct link to Instructions")
---------------------------------------------------------------------------------------------------------------------------------

Download [hw08.zip](https://www.learncs.site/assets/files/hw08-912d428eb7876001702e96d040d986ca.zip). Inside the archive, you will find a file called [hw08.scm](https://cs61a.org//hw/hw08/hw08.scm), along with a copy of the `ok` autograder.

**Submission:** When you are done, submit the assignment by uploading all code files you've edited to Gradescope. You may submit more than once before the deadline; only the final submission will be scored. Check that you have successfully submitted your code on Gradescope. See [Lab 0](https://cs61a.org/lab/lab00#task-c-submitting-the-assignment) for more instructions on submitting assignments.

**Using Ok:** If you have any questions about using Ok, please refer to [this guide.](https://cs61a.org/articles/using-ok)

**Readings:** You might find the following references useful:

*   [Scheme Specification](https://cs61a.org/articles/scheme-spec/)
*   [Scheme Built-in Procedure Reference](https://cs61a.org/articles/scheme-builtins/)

**Grading:** Homework is graded based on correctness. Each incorrect problem will decrease the total score by one point. **This homework is out of 2 points.**

The 61A Scheme interpreter is included in each Scheme assignment. To start it, type `python3 scheme` in a terminal. To load a Scheme file called `f.scm`, type `python3 scheme -i f.scm`. To exit the Scheme interpreter, type `(exit)`.

### Scheme Editor[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#scheme-editor "Direct link to Scheme Editor")

All Scheme assignments include a web-based editor that makes it easy to run ok tests and visualize environments. Type `python3 editor` in a terminal, and the editor will open in a browser window (at `http://127.0.0.1:31415/`). To stop running the editor and return to the command line, type `Ctrl-C` in the terminal where you started the editor.

The `Run` button loads the current assignment's `.scm` file and opens a Scheme interpreter, allowing you to try evaluating different Scheme expressions.

The `Test` button runs all ok tests for the assignment. Click `View Case` for a failed test, then click `Debug` to step through its evaluation.

### Recommended VS Code Extensions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#recommended-vs-code-extensions "Direct link to Recommended VS Code Extensions")

If you choose to use VS Code as your text editor (instead of the web-based editor), install the [vscode-scheme](https://marketplace.visualstudio.com/items?itemName=sjhuangx.vscode-scheme) extension so that parentheses are highlighted.

Before:

![](https://www.learncs.site/assets/images/before-1fb62971706b817f8b61c7a23705e08a.png)

After:

![](https://www.learncs.site/assets/images/after-49c28554ee03a6642fe04e111fd59fd5.png)

In addition, the 61a-bot ([installation instructions](https://cs61a.org/articles/61a-bot)) VS Code extension is available for Scheme homeworks. The bot is also integrated into `ok`.

Required Questions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#required-questions "Direct link to Required Questions")
---------------------------------------------------------------------------------------------------------------------------------------------------

Required Questions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#required-questions-1 "Direct link to Required Questions")
-----------------------------------------------------------------------------------------------------------------------------------------------------

Getting Started Videos[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#getting-started-videos "Direct link to Getting Started Videos")
---------------------------------------------------------------------------------------------------------------------------------------------------------------

These videos may provide some helpful direction for tackling the coding problems on this assignment.

> To see these videos, you should be logged into your berkeley.edu email.

[YouTube link](https://youtu.be/playlist?list=PLx38hZJ5RLZeOPmZFG6vuUl71MdfpmBLe)

### Q1: Ascending[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#q1-ascending "Direct link to Q1: Ascending")

Implement a procedure called `ascending?`, which takes a list of numbers `s` and returns `True` if the numbers are in non-descending order, and `False` otherwise.

A list of numbers is non-descending if each element after the first is greater than or equal to the previous element. For example...

*   `(1 2 3 3 4)` is non-descending.
*   `(1 2 3 3 2)` is not.

> **Hint**: The built-in `null?` procedure returns whether its argument is `nil`.

> **Note**: The question mark in `ascending?` is just part of the procedure name and has no special meaning in terms of Scheme syntax. It is a common practice in Scheme to name procedures with a question mark at the end if it returns a boolean value.

    (define (ascending? s)  'YOUR-CODE-HERE)

Use Ok to unlock and test your code:

    python3 ok -q ascending -upython3 ok -q ascending

### Q2: My Filter[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#q2-my-filter "Direct link to Q2: My Filter")

Write a procedure `my-filter`, which takes a predicate `pred` and a list `s`, and returns a new list containing only elements of the list that satisfy the predicate. The output should contain the elements in the same order that they appeared in the original list.

**Note:** Make sure that you are not just calling the built-in `filter` function in Scheme - we are asking you to re-implement this!

    (define (my-filter pred s)  'YOUR-CODE-HERE)

Use Ok to unlock and test your code:

    python3 ok -q filter -upython3 ok -q filter

### Q3: Interleave[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#q3-interleave "Direct link to Q3: Interleave")

Implement the function `interleave`, which takes two lists `lst1` and `lst2` as arguments. `interleave` should return a new list that interleaves the elements of the two lists. (In other words, the resulting list should contain elements alternating between `lst1` and `lst2`, starting at `lst1`).

If one of the input lists to `interleave` is shorter than the other, then `interleave` should alternate elements from both lists until one list has no more elements, and then the remaining elements from the longer list should be added to the end of the new list.

    (define (interleave lst1 lst2)  'YOUR-CODE-HERE)

Use Ok to unlock and test your code:

    python3 ok -q interleave -upython3 ok -q interleave

### Q4: No Repeats[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#q4-no-repeats "Direct link to Q4: No Repeats")

Implement `no-repeats`, which takes a list of numbers `s`. It returns a list that has all of the unique elements of `s` in the order that they first appear, but no repeats.

For example, `(no-repeats (list 5 4 5 4 2 2))` evaluates to `(5 4 2)`.

> **Hint:** You may find it helpful to use `filter` with a `lambda` procedure to filter out repeats. To test if two numbers `a` and `b` are not equal, use `(not (= a b))`.

    (define (no-repeats s)  'YOUR-CODE-HERE)

Use Ok to test your code:

    python3 ok -q no_repeats

Submit[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#submit "Direct link to Submit")
---------------------------------------------------------------------------------------------------------------

Submit this assignment by uploading any files you've edited **to the appropriate Gradescope assignment.** [Lab 00](https://cs61a.org/lab/lab00/#submit-with-gradescope) has detailed instructions.

In addition, all students who are **not** in the mega lab must complete this [attendance form](https://go.cs61a.org/lab-att). Submit this form each week, whether you attend lab or missed it for a good reason. The attendance form is not required for mega section students.

Exam Practice[​](https://www.learncs.site/docs/curriculum-resource/cs61a/homework/hw08#exam-practice "Direct link to Exam Practice")
------------------------------------------------------------------------------------------------------------------------------------

The following are some Scheme List exam problems from previous semesters that you may find useful as additional exam practice.

1.  [Fall 2022 Final, Question 8: A Parentheses Scheme](https://cs61a.org/exam/fa22/final/61a-fa22-final.pdf#page=20)
2.  [Spring 2022 Final, Question 11: Beadazzled, The Scheme-quel](https://cs61a.org/exam/sp22/final/61a-sp22-final.pdf#page=23)
3.  [Fall 2021 Final, Question 4: Spice](https://cs61a.org/exam/fa21/final/61a-fa21-final.pdf#page=18)