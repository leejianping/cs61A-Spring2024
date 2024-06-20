Lab 7: Inheritance, Linked Lists
================================

_Due by 11:59pm on Wednesday, March 13._

Starter Files[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#starter-files "Direct link to Starter Files")
--------------------------------------------------------------------------------------------------------------------------------

Download [lab07.zip](https://www.learncs.site/assets/files/lab07-e9dc3f9f66fede35f4393fbec8910f9e.zip). Inside the archive, you will find starter files for the questions in this lab, along with a copy of the [Ok](https://cs61a.org//lab/lab07/ok) autograder.

Required Questions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#required-questions "Direct link to Required Questions")
-----------------------------------------------------------------------------------------------------------------------------------------------

Getting Started Videos[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#getting-started-videos "Direct link to Getting Started Videos")
-----------------------------------------------------------------------------------------------------------------------------------------------------------

These videos may provide some helpful direction for tackling the coding problems on this assignment.

> To see these videos, you should be logged into your berkeley.edu email.

[YouTube link](https://youtu.be/playlist?list=PLx38hZJ5RLZf149ILKTCfQ11eVDRm8KS1)

Inheritance[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#inheritance "Direct link to Inheritance")
--------------------------------------------------------------------------------------------------------------------------

Consult the drop-down if you need a refresher on Inheritance. It's okay to skip directly to the questions and refer back here should you get stuck.

To avoid redefining attributes and methods for similar classes, we can write a single **base class** from which more specialized classes **inherit**. For example, we can write a class called `Pet` and define `Dog` as a **subclass** of `Pet`:

    class Pet:    def __init__(self, name, owner):        self.is_alive = True    # It's alive!!!        self.name = name        self.owner = owner    def eat(self, thing):        print(self.name + " ate a " + str(thing) + "!")    def talk(self):        print(self.name)class Dog(Pet):    def talk(self):        super().talk()        print('This Dog says woof!')

Inheritance represents a hierarchical relationship between two or more classes where one class **is a** more specific version of the other: a dog **is a** pet (We use **is a** to describe this sort of relationship in OOP languages, and not to refer to the Python `is` operator).

Since `Dog` inherits from `Pet`, the `Dog` class will also inherit the `Pet` class's methods, so we don't have to redefine `__init__` or `eat`. We do want each `Dog` to `talk` in a `Dog`\-specific way, so we can **override** the `talk` method.

We can use `super()` to refer to the superclass of `self`, and access any superclass methods as if we were an instance of the superclass. For example, `super().talk()` in the `Dog` class will call the `talk` method from the `Pet` class, but passing the `Dog` instance as the `self`.

### Q1: WWPD: Inheritance ABCs[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q1-wwpd-inheritance-abcs "Direct link to Q1: WWPD: Inheritance ABCs")

> **Important:** For all WWPD questions, type `Function` if you believe the answer is `<function...>`, `Error` if it errors, and `Nothing` if nothing is displayed.
> 
> Use Ok to test your knowledge with the following "What Would Python Display?" questions:
> 
>     python3 ok -q inheritance-abc -u

    >>> class A:...   x, y = 0, 0...   def __init__(self):...         return>>> class B(A):...   def __init__(self):...         return>>> class C(A):...   def __init__(self):...         return>>> print(A.x, B.x, C.x)____________>>> B.x = 2>>> print(A.x, B.x, C.x)____________>>> A.x += 1>>> print(A.x, B.x, C.x)____________>>> obj = C()>>> obj.y = 1>>> C.y == obj.y____________>>> A.y = obj.y>>> print(A.y, B.y, C.y, obj.y)____________

Class Practice[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#class-practice "Direct link to Class Practice")
-----------------------------------------------------------------------------------------------------------------------------------

Let's say we'd like to model a bank account that can handle interactions such as depositing funds or gaining interest on current funds. In the following questions, we will be building off of the `Account` class. Here's our current definition of the class:

    class Account:    """An account has a balance and a holder.    >>> a = Account('John')    >>> a.deposit(10)    10    >>> a.balance    10    >>> a.interest    0.02    >>> a.time_to_retire(10.25)  # 10 -> 10.2 -> 10.404    2    >>> a.balance                # Calling time_to_retire method should not change the balance    10    >>> a.time_to_retire(11)     # 10 -> 10.2 -> ... -> 11.040808032    5    >>> a.time_to_retire(100)    117    """    max_withdrawal = 10    interest = 0.02    def __init__(self, account_holder):        self.balance = 0        self.holder = account_holder    def deposit(self, amount):        self.balance = self.balance + amount        return self.balance    def withdraw(self, amount):        if amount > self.balance:            return "Insufficient funds"        if amount > self.max_withdrawal:            return "Can't withdraw that amount"        self.balance = self.balance - amount        return self.balance

### Q2: Retirement[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q2-retirement "Direct link to Q2: Retirement")

Add a `time_to_retire` method to the `Account` class. This method takes in an `amount` and returns how many years the holder would need to wait in order for the current `balance` to grow to at least `amount`, assuming that the bank adds the interest (calculated as the current `balance` multiplied by the `interest` rate) to the `balance` at the end of each year.

    ```def time_to_retire(self, amount):    """Return the number of years until balance would grow to amount."""    assert self.balance > 0 and amount > 0 and self.interest > 0    "*** YOUR CODE HERE ***"

    Use Ok to test your code:

python3 ok -q Account

      ### Q3: FreeCheckingImplement the `FreeChecking` class, which is like the `Account` class from lecture except that it charges a withdraw fee `withdraw_fee` after withdrawing `free_withdrawals` number of times. If a withdrawal is unsuccessful, it still counts towards the number of free withdrawals remaining, but no fee for the withdrawal will be charged.

class FreeChecking(Account): """A bank account that charges for withdrawals, but the first two are free!

    >>> ch = FreeChecking('Jack')>>> ch.balance = 20>>> ch.withdraw(100)  # First one's free. Still counts as a free withdrawal even though it was unsuccessful'Insufficient funds'>>> ch.withdraw(3)    # Second withdrawal is also free17>>> ch.balance17>>> ch.withdraw(3)    # Ok, two free withdrawals is enough, as free_withdrawals is only 213>>> ch.withdraw(3)9>>> ch2 = FreeChecking('John')>>> ch2.balance = 10>>> ch2.withdraw(3) # No fee7>>> ch.withdraw(3)  # ch still charges a fee5>>> ch.withdraw(5)  # Not enough to cover fee + withdraw'Insufficient funds'"""withdraw_fee = 1free_withdrawals = 2"*** YOUR CODE HERE ***"

    Use Ok to test your code:

python3 ok -q FreeChecking

      ## Linked ListsConsult the drop-down if you need a refresher on Linked Lists. It's okay to skip directly to the questions and refer back here should you get stuck.A linked list is a data structure for storing a sequence of values. It is more efficient than a regular built-in list for certain operations, such as inserting a value in the middle of a long list. Linked lists are not built in, and so we define a class called `Link` to represent them. A linked list is either a `Link` instance or `Link.empty` (which represents an empty linked list).A instance of `Link` has two instance attributes, `first` and `rest`.

class Link: """A linked list.

    >>> s = Link(1)>>> s.first1>>> s.rest is Link.emptyTrue>>> s = Link(2, Link(3, Link(4)))>>> s.first = 5>>> s.rest.first = 6>>> s.rest.rest = Link.empty>>> s                                    # Displays the contents of repr(s)Link(5, Link(6))>>> s.rest = Link(7, Link(Link(8, Link(9))))>>> sLink(5, Link(7, Link(Link(8, Link(9)))))>>> print(s)                             # Prints str(s)<5 7 <8 9>>"""empty = ()def __init__(self, first, rest=empty):    assert rest is Link.empty or isinstance(rest, Link)    self.first = first    self.rest = restdef __repr__(self):    if self.rest is not Link.empty:        rest_repr = ', ' + repr(self.rest)    else:        rest_repr = ''    return 'Link(' + repr(self.first) + rest_repr + ')'def __str__(self):    string = '<'    while self.rest is not Link.empty:        string += str(self.first) + ' '        self = self.rest    return string + str(self.first) + '>'

    The `rest` attribute of a `Link` instance should always be a linked list: either another `Link` instance or `Link.empty`. It SHOULD NEVER be `None`.To check if a linked list is empty, compare it to `Link.empty`. Since there is only ever one empty list, we can use `is` to compare, but `==` would work too.

def is\_empty(s): """Return whether linked list s is empty.""" return s is Link.empty:

    ### Q4: WWPD: Linked ListsRead over the `Link` class. Make sure you understand the doctests.> Use Ok to test your knowledge with the following "What Would Python Display?" questions:> > ```> python3 ok -q link -u> ```> > Enter `Function` if you believe the answer is `<function ...>`, `Error` if it errors, and `Nothing` if nothing is displayed.> > If you get stuck, try drawing out the box-and-pointer diagram for the linked list on a piece of paper or loading the `Link` class into the interpreter with `python3 -i lab08.py`.

> > > link = Link(1000) link.first **\_\_**1000 link.rest is Link.empty **\_\_**True link = Link(1000, 2000) **\_\_**AssertionError link = Link(1000, Link()) **\_\_**TypeError
> > > 
> > >     

    >>> link = Link(1, Link(2, Link(3)))>>> link.first______1>>> link.rest.first______2>>> link.rest.rest.rest is Link.empty______True>>> link.first = 9001>>> link.first______9001>>> link.rest = link.rest.rest>>> link.rest.first______3>>> link = Link(1)>>> link.rest = link>>> link.rest.rest is Link.empty______False>>> link.rest.rest.rest.rest.first______1>>> link = Link(2, Link(3, Link(4)))>>> link2 = Link(1, link)>>> link2.first______1>>> link2.rest.first______2

    >>> link = Link(5, Link(6, Link(7)))>>> link                 # Look at the __repr__ method of Link______Link(5, Link(6, Link(7)))>>> print(link)          # Look at the __str__ method of Link______<5 6 7>

### Q5: Duplicate Link[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#q5-duplicate-link "Direct link to Q5: Duplicate Link")

Write a function `duplicate_link` that takes in a linked list `s` and a value `val`. It mutates `s` so that each element equal to `val` is followed by an additional `val` (a duplicate copy). It returns `None`.

> **Note**: In order to insert a link into a linked list, reassign the `rest` attribute of the `Link` instances that have `val` as their `first`. Try drawing out a doctest to visualize!

    def duplicate_link(s, val):    """Mutates s so that each element equal to val is followed by another val.    >>> x = Link(5, Link(4, Link(5)))    >>> duplicate_link(x, 5)    >>> x    Link(5, Link(5, Link(4, Link(5, Link(5)))))    >>> y = Link(2, Link(4, Link(6, Link(8))))    >>> duplicate_link(y, 10)    >>> y    Link(2, Link(4, Link(6, Link(8))))    >>> z = Link(1, Link(2, (Link(2, Link(3)))))    >>> duplicate_link(z, 2) # ensures that back to back links with val are both duplicated    >>> z    Link(1, Link(2, Link(2, Link(2, Link(2, Link(3))))))    """    "*** YOUR CODE HERE ***"

Use Ok to test your code:

    python3 ok -q duplicate_link

Check Your Score Locally[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#check-your-score-locally "Direct link to Check Your Score Locally")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------

You can locally check your score on each question of this assignment by running

    python3 ok --score

**This does NOT submit the assignment!** When you are satisfied with your score, submit the assignment to Gradescope to receive credit for it.

Submit[​](https://www.learncs.site/docs/curriculum-resource/cs61a/lab/lab01#submit "Direct link to Submit")
-----------------------------------------------------------------------------------------------------------

Submit this assignment by uploading any files you've edited **to the appropriate Gradescope assignment.** [Lab 00](https://cs61a.org/lab/lab00/#submit-with-gradescope) has detailed instructions.

In addition, all students who are **not** in the mega lab must complete this [attendance form](https://go.cs61a.org/lab-att). Submit this form each week, whether you attend lab or missed it for a good reason. The attendance form is not required for mega section students.