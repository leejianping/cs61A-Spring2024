# Lab 1: Functions, Control | CS 61A Spring 2024
==============================================

Lab 1: Functions, Control[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#lab-1-functions-control "Direct link to Lab 1: Functions, Control")
------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   [lab01.zip](https://www.learncs.site/assets/files/lab01-a931ac14abc3de4d9162988666fd9c2f.zip)

_Due by 11:59pm on Wednesday, January 24._

Starter Files[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#starter-files "Direct link to Starter Files")
--------------------------------------------------------------------------------------------------------------------------------

Download [lab01.zip](https://www.learncs.site/assets/files/lab01-a931ac14abc3de4d9162988666fd9c2f.zip). Inside the archive, you will find starter files for the questions in this lab, along with a copy of the [Ok](https://cs61a.org//lab/lab01/ok) autograder.

Required Questions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#required-questions "Direct link to Required Questions")
-----------------------------------------------------------------------------------------------------------------------------------------------

Getting Started Videos[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#getting-started-videos "Direct link to Getting Started Videos")
-----------------------------------------------------------------------------------------------------------------------------------------------------------

These videos may provide some helpful direction for tackling the coding problems on this assignment.

> To see these videos, you should be logged into your berkeley.edu email.

[YouTube link](https://youtu.be/playlist?list=PLx38hZJ5RLZdIweNNPm4tZYMrVXd76H_l)

Review[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#review "Direct link to Review")
-----------------------------------------------------------------------------------------------------------

Here are the most common ways to run Python on a file.

1.  Using no command-line options will run the code in the file you provide and return you to the command line. If your file just contains function definitions, you'll see no output unless there is a syntax error.
    
        python3 lab00.py
    
2.  **`-i`**: The `-i` option runs the code in the file you provide, then opens an interactive session (with a `>>>` prompt). You can then evaluate expressions, for example calling functions you defined. To exit, type `exit()`. You can also use the keyboard shortcut `Ctrl-D` on Linux/Mac machines or `Ctrl-Z Enter` on Windows.
    
    If you edit the Python file while running it interactively, you will need to exit and restart the interpreter in order for those changes to take effect.
    
    Here's how we can run `lab00.py` interactively:
    
        python3 -i lab00.py
    
3.  **`-m doctest`**: Runs the doctests in a file, which are the examples in the docstrings of functions.
    
    Each test in the file consists of `>>>` followed by some Python code and the expected output.
    
    Here's how we can run the doctests in `lab00.py`:
    
         python3 -m doctest lab00.py
    
    When our code passes all of the doctests, no output is displayed. Otherwise, information about the tests that failed will be displayed.
    

In 61A, we use a program called OK for autograding labs, homeworks, and projects.

To use Ok to test a function, run the following command (replacing `FUNCTION` with the name of the function):

    python3 ok -q FUNCTION

If your function contains a call to `print` that starts with `"DEBUG:"`, then this line will be ignored by OK. (Otherwise, including extra `print` calls can cause tests to fail because of the additional output displayed.)

    print("DEBUG:", x)

There are more features described on the [Using OK page](https://cs61a.org/articles/using-ok). **You can quickly generate most ok commands at [ok-help](https://go.cs61a.org/ok-help).**

Here are examples of the division-related operators in Python 3:

| True Division: `/`  
(decimal division) | Floor Division: `//`  
(integer division) | Modulo: `%`  
(remainder) | | --- | --- | --- | |

    >>> 1 / 50.2>>> 25 / 46.25>>> 4 / 22.0>>> 5 / 0ZeroDivisionError

|

    >>> 1 // 5 # truncate result of true division0>>> 25 // 46>>> 4 // 22>>> 5 // 0ZeroDivisionError

|

    >>> 1 % 51>>> 25 % 41>>> 4 % 20>>> 5 % 0ZeroDivisionError

|

A `ZeroDivisionError` occurs when dividing by 0.

One useful technique involving the `%` operator is to check whether a number `x` is divisible by another number `y`:

    x % y == 0

For example, in order to check if `x` is an even number: `x % 2 == 0`

Most functions that you define will contain a `return` statement that provides the value of the call expression used to call the function.

When Python executes a `return` statement, the function call terminates immediately. If Python reaches the end of the function body without executing a `return` statement, the function returns `None`.

In contrast, the `print` function is used to display values. Unlike a `return` statement, when Python evaluates a call to `print`, the function does _not_ terminate immediately.

    def what_prints():    print('Hello World!')    return 'Exiting this function.'    print('61A is awesome!')>>> what_prints()Hello World!'Exiting this function.'

> Notice also that `print` will display text **without the quotes**, but `return` will preserve the quotes.

What Would Python Display? (WWPD)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#what-would-python-display-wwpd "Direct link to What Would Python Display? (WWPD)")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Q1: WWPD: Control[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q1-wwpd-control "Direct link to Q1: WWPD: Control")

> Use Ok to test your knowledge with the following "What Would Python Display?" questions:
> 
>     python3 ok -q control -u

    >>> def xk(c, d):...     if c == 4:...         return 6...     elif d >= 4:...         return 6 + 7 + c...     else:...         return 25>>> xk(10, 10)______23>>> xk(10, 6)______23>>> xk(4, 6)______6>>> xk(0, 0)______25

    >>> def how_big(x):...     if x > 10:...         print('huge')...     elif x > 5:...         return 'big'...     if x > 0:...         print('positive')...     else:...         print(0)>>> how_big(7)         # A returned string is displayed with single quotes______'big'>>> print(how_big(7))  # A printed string has no quotes______big>>> how_big(12)______hugepositive>>> print(how_big(12))______hugepositiveNone>>> print(how_big(1), how_big(0))______positive0None None

    >>> n = 3>>> while n >= 0:...     n -= 1...     print(n)______210-1

    >>> negative = -12>>> while negative:  # All numbers are true values except 0...    if negative + 6:...        print(negative)...    negative += 3______-12-9-3

### Q2: Debugging Quiz[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q2-debugging-quiz "Direct link to Q2: Debugging Quiz")

The following is a quick quiz on different debugging techniques that will be helpful for you to use in this class. You can refer to the [debugging article](https://cs61a.org/articles/debugging/) to answer the questions.

Use Ok to test your understanding:

    python3 ok -q debugging-quiz -u

Write Code[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#write-code "Direct link to Write Code")
-----------------------------------------------------------------------------------------------------------------------

### Q3: Falling Factorial[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q3-falling-factorial "Direct link to Q3: Falling Factorial")

Let's write a function `falling`, which is a "falling" factorial that takes two arguments, `n` and `k`, and returns the product of `k` consecutive numbers, starting from `n` and working downwards. When `k` is 0, the function should return 1.

    def falling(n, k):    """Compute the falling factorial of n to depth k.    >>> falling(6, 3)  # 6 * 5 * 4    120    >>> falling(4, 3)  # 4 * 3 * 2    24    >>> falling(4, 1)  # 4    4    >>> falling(4, 0)    1    """    "*** YOUR CODE HERE ***"

Use Ok to test your code:

    python3 ok -q falling

### Q4: Divisible By k[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q4-divisible-by-k "Direct link to Q4: Divisible By k")

Write a function `divisible_by_k` that takes positive integers `n` and `k`. It prints all positive integers less than or equal to `n` that are divisible by `k` from smallest to largest. Then, it returns how many numbers were printed.

    def divisible_by_k(n, k):    """    >>> a = divisible_by_k(10, 2)  # 2, 4, 6, 8, and 10 are divisible by 2    2    4    6    8    10    >>> a    5    >>> b = divisible_by_k(3, 1)  # 1, 2, and 3 are divisible by 1    1    2    3    >>> b    3    >>> c = divisible_by_k(6, 7)  # There are no integers up to 6 divisible by 7    >>> c    0    """    "*** YOUR CODE HERE ***"

Use Ok to test your code:

    python3 ok -q divisible_by_k

### Q5: Sum Digits[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q5-sum-digits "Direct link to Q5: Sum Digits")

Write a function that takes in a nonnegative integer and sums its digits. (Using floor division and modulo might be helpful here!)

    def sum_digits(y):    """Sum all the digits of y.    >>> sum_digits(10) # 1 + 0 = 1    1    >>> sum_digits(4224) # 4 + 2 + 2 + 4 = 12    12    >>> sum_digits(1234567890)    45    >>> a = sum_digits(123) # make sure that you are using return rather than print    >>> a    6    """    "*** YOUR CODE HERE ***"

Use Ok to test your code:

    python3 ok -q sum_digits

Syllabus Quiz[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#syllabus-quiz "Direct link to Syllabus Quiz")
--------------------------------------------------------------------------------------------------------------------------------

### Q6: Syllabus Quiz[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q6-syllabus-quiz "Direct link to Q6: Syllabus Quiz")

Please fill out the [Syllabus Quiz](https://go.cs61a.org/syllabus-quiz), which confirms your understanding of CS 61A [course policies](https://cs61a.org/articles/about/).

Check Your Score Locally[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#check-your-score-locally "Direct link to Check Your Score Locally")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------

You can locally check your score on each question of this assignment by running

    python3 ok --score

**This does NOT submit the assignment!** When you are satisfied with your score, submit the assignment to Gradescope to receive credit for it.

Submit[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#submit "Direct link to Submit")
-----------------------------------------------------------------------------------------------------------

Submit this assignment by uploading any files you've edited **to the appropriate Gradescope assignment.** [Lab 00](https://cs61a.org/lab/lab00/#submit-with-gradescope) has detailed instructions.

In addition, all students who are **not** in the mega lab must complete this [attendance form](https://go.cs61a.org/lab-att). Submit this form each week, whether you attend lab or missed it for a good reason. The attendance form is not required for mega section students.

Optional Questions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#optional-questions "Direct link to Optional Questions")
-----------------------------------------------------------------------------------------------------------------------------------------------

> These questions are optional. If you don't complete them, you will still receive credit for lab. They are great practice, so do them anyway!

### Q7: WWPD: What If?[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q7-wwpd-what-if "Direct link to Q7: WWPD: What If?")

> Use Ok to test your knowledge with the following "What Would Python Display?" questions:
> 
>     python3 ok -q if-statements -u
> 
> **Hint**: `print` (unlike `return`) does _not_ cause the function to exit.

    >>> def ab(c, d):...     if c > 5:...         print(c)...     elif c > 7:...         print(d)...     print('foo')>>> ab(10, 20)______10foo

    >>> def bake(cake, make):...     if cake == 0:...         cake = cake + 1...         print(cake)...     if cake == 1:...         print(make)...     else:...         return cake...     return make>>> bake(0, 29)______12929>>> bake(1, "mashed potatoes")______mashed potatoes'mashed potatoes'

### Q8: Double Eights[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q8-double-eights "Direct link to Q8: Double Eights")

Write a function that takes in a number and determines if the digits contain two adjacent 8s.

    def double_eights(n):    """Return true if n has two eights in a row.    >>> double_eights(8)    False    >>> double_eights(88)    True    >>> double_eights(2882)    True    >>> double_eights(880088)    True    >>> double_eights(12345)    False    >>> double_eights(80808080)    False    """    "*** YOUR CODE HERE ***"

Use Ok to test your code:

    python3 ok -q double_eights