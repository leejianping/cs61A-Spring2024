Discussion 12 | CS 61A Spring 2024
==================================

Discussion 12: Final Review[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#discussion-12-final-review "Direct link to Discussion 12: Final Review")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   [disc12.pdf](https://www.learncs.site/assets/files/disc12-60dd80ec62b0e565d4a3721800d350b8.pdf)

**Reminder:** Use Discord for voice chat with the course staff. Write to `@discuss` in the `#discuss-queue` channel on Discord at any time, and a member of the course staff will join your group's voice channel.

Pick someone in your group to [join Discord](https://cs61a.org/articles/discord). It's fine if multiple people join, but one is enough.

Now switch to Pensieve:

*   **Everyone**: Go to [discuss.pensieve.co](http://discuss.pensieve.co/) and log in with your @berkeley.edu email, then enter your group number. (Your group number is the number of your Discord channel.)

Once you're on Pensieve, you don't need to return to this page; Pensieve has all the same content (but more features). If for some reason Penseive doesn't work, return to this page and continue with the discussion.

Post in the `#help` channel on [Discord](https://cs61a.org/articles/discord/) if you have trouble.

**Pro tip:** Any of you can type a question into your group's Discord [channel's text chat](https://support.discord.com/hc/en-us/articles/4412085582359-Text-Channels-Text-Chat-In-Voice-Channels#h_01FMJT412WBX1MR4HDYNR8E95X) with the `@discuss` tag, and a member of the course staff will respond.

Getting Started[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#getting-started "Direct link to Getting Started")
---------------------------------------------------------------------------------------------------------------------------------------

If you have only 1 or 2 people in your group, you can join the other group in the room with you.

**Ice breaker:** Everybody say your name and the non-CS/EECS course that you're most excited about taking next semester.

Lists[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#lists "Direct link to Lists")
---------------------------------------------------------------------------------------------------------

The two most common mutation operations for lists are item assignment and the `append` method.

    >>> s = [1, 3, 4]>>> t = s  # A second name for the same list>>> t[0] = 2  # this changes the first element of the list to 2, affecting both s and t>>> s[2, 3, 4]>>> s.append(5)  # this adds 5 to the end of the list, affecting both s and t>>> t[2, 3, 4, 5]

There are many other list mutation methods:

*   `append(elem)`: Add `elem` to the end of the list. Return `None`.
*   `extend(s)`: Add all elements of iterable `s` to the end of the list. Return `None`.
*   `insert(i, elem)`: Insert `elem` at index `i`. If `i` is greater than or equal to the length of the list, then `elem` is inserted at the end. This does not replace any existing elements, but only adds the new element `elem`. Return `None`.
*   `remove(elem)`: Remove the first occurrence of `elem` in list. Return `None`. Errors if `elem` is not in the list.
*   `pop(i)`: Remove and return the element at index `i`.
*   `pop()`: Remove and return the last element.

### Q1: Word Rope[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#q1-word-rope "Direct link to Q1: Word Rope")

**Definition:** A _rope_ in Python is a list containing only one-letter strings except for the last element, which may either be a one-letter string or a rope.

Implement `word_rope`, a Python function that takes a non-empty string `s` containing only letters and spaces that does not start or end with a space. It returns a _rope_ containing the letters of `s` in which each word is in a separate list.

**Important:** You may not use slicing or the `split`, `find`, or `index` methods of a string. Solve the problem using list operations.

**Reminder:** `s[-1]` evaluates to the last element of a sequence `s`.

Run in 61A Code

In this implementation, `result` is a rope and `word` is a list within that rope which is still being constructed. When `x` is a space, add an empty list to the end of `word` and assign `word` to this empty list. Otherwise, add `x` to the end of `word`.

Linked Lists[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#linked-lists "Direct link to Linked Lists")
------------------------------------------------------------------------------------------------------------------------------

A linked list is a `Link` object or `Link.empty`.

You can mutate a `Link` object `s` in two ways:

*   Change the first element with `s.first = ...`
*   Change the rest of the elements with `s.rest = ...`

You can make a new `Link` object by calling `Link`:

*   `Link(4)` makes a linked list of length 1 containing 4.
*   `Link(4, s)` makes a linked list that starts with 4 followed by the elements of linked list `s`.

    class Link:    """A linked list is either a Link object or Link.empty    >>> s = Link(3, Link(4, Link(5)))    >>> s.rest    Link(4, Link(5))    >>> s.rest.rest.rest is Link.empty    True    >>> s.rest.first * 2    8    >>> print(s)    <3 4 5>    """    empty = ()    def __init__(self, first, rest=empty):        assert rest is Link.empty or isinstance(rest, Link)        self.first = first        self.rest = rest    def __repr__(self):        if self.rest:            rest_repr = ', ' + repr(self.rest)        else:            rest_repr = ''        return 'Link(' + repr(self.first) + rest_repr + ')'    def __str__(self):        string = '<'        while self.rest is not Link.empty:            string += str(self.first) + ' '            self = self.rest        return string + str(self.first) + '>'

### Q2: Linear Sublists[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#q2-linear-sublists "Direct link to Q2: Linear Sublists")

**Definition:** A _sublist_ of linked list `s` is a linked list of some of the elements of `s` in order. For example, `<3 6 2 5 1 7>` has sublists `<3 2 1>` and `<6 2 7>` but not `<5 6 7>`.

**Definition:** A _linear sublist_ of a linked list of numbers `s` is a sublist in which the difference between adjacent numbers is always the same. For example `<2 4 6 8>` is a linear sublist of `<1 2 3 4 6 9 1 8 5>` because the difference between each pair of adjacent elements is 2.

Implement `linear` which takes a linked list of numbers `s` (either a `Link` instance or `Link.empty`). It returns the longest linear sublist of `s`. If two linear sublists are tied for the longest, return either one.

Run in 61A Code

There are three cases:

*   If `rest` is empty, return a one-element list containing just `first`.
*   If `rest.first` is in the linear sublist that starts with `first`, then build a list that contains `first`, and `rest.first`.
*   Otherwise, `complete(first, rest.rest)`.

This while loop is creating a `candidate` linear sublist for every two possible starting values: `s.first` and `t.first`. The rest of the linear sublist must be in `t.rest`.

Scheme[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#scheme "Direct link to Scheme")
------------------------------------------------------------------------------------------------------------

### Q3: Increasing Rope[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#q3-increasing-rope "Direct link to Q3: Increasing Rope")

**Definition:** A _rope_ in Scheme is a non-empty list containing only numbers except for the last element, which may either be a number or a rope.

Implement `up`, a Scheme procedure that takes a positive integer `n`. It returns a rope containing the digits of `n` that is the shortest rope in which each pair of adjacent numbers in the same list are in increasing order.

**Reminder**: the `quotient` procedure performs floor division, like `//` in Python. The `remainder` procedure is like `%` in Python.

Run in 61A Code

Compare `first` to `(car result)` to decide whether to `cons` the value `first` onto the `result` or whether to form a new list that contains `first` and `result` as elements.

To correctly call `helper` from within `up`, build a rope that only contains the last digit of `n`: `(remainder n 10)`.

SQL[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#sql "Direct link to SQL")
---------------------------------------------------------------------------------------------------

A `SELECT` statement describes an output table based on input rows. To write one:

1.  Describe the **input rows** using `FROM` and `WHERE` clauses.
2.  **Group** those rows and determine which groups should appear as output rows using `GROUP BY` and `HAVING` clauses.
3.  Format and order the **output rows** and columns using `SELECT` and `ORDER BY` clauses.

`SELECT` _(Step 3)_ `FROM` _(Step 1)_ `WHERE` _(Step 1)_ `GROUP BY` _(Step 2)_ `HAVING` _(Step 2)_ `ORDER BY` _(Step 3)_;

Step 1 may involve joining tables (using commas) to form input rows that consist of two or more rows from existing tables.

The `WHERE`, `GROUP BY`, `HAVING`, and `ORDER BY` clauses are optional.

### Q4: A Secret Message[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#q4-a-secret-message "Direct link to Q4: A Secret Message")

A substitution cipher replaces each word with another word in a table in order to encrypt a message. To decode an encrypted message, replace each word `x` with its corresponding `y` in a code table.

Write a select statement to decode the `original` message _It's The End_ using the `code` table.

Run in 61A Code

Join the `original` and `code` tables and make sure that the joined roles have the same `word` and `x`.

What happens now? Write another select statement to decode this encrypted message using the same `code` table.

Run in 61A Code

Join `original` with `code AS a` and `code AS b` to create six-column rows like: `2|The|The|Happens|Happens|Go`, The _Go_ at the end is part of the decoded message.

**Scheduling time:** This is the last discussion, but you could schedule a meeting with your group next week to study for the exam. Your regular discussion room and time should be available during RRR week if you want to use it.

Document the Occasion[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc12#document-the-occasion "Direct link to Document the Occasion")
---------------------------------------------------------------------------------------------------------------------------------------------------------

Please all fill out the [attendance form](https://docs.google.com/forms/d/e/1FAIpQLSeqlK8l6WkScGr-RHR-kM4p5bnR9cllYrG95fDqPJspSlll7A/viewform) (one submission per person per week).

**Important:** Please help put the furniture in the room back where you found it before you leave. Thanks!