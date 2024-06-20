Project 1: The Game of Hog
==========================

> ![5-sided die](data:image/gif;base64,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)
> 
> I know! I'll use my  
> Higher-order functions to  
> Order higher rolls.

Introduction[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#introduction "Direct link to Introduction")
-------------------------------------------------------------------------------------------------------------------------------

> **Important submission note:** For full credit:
> 
> *   Submit with Phase 1 complete by **Tuesday, January 30**, worth 1 pt.
> *   Submit the complete project by **Wednesday, February 7**.
> 
> Try to attempt the problems in order, as some later problems will depend on earlier problems in their implementation and therefore also when running `ok` tests.
> 
> You may complete the project with a partner.
> 
> You can get 1 bonus point by submitting the entire project by **Tuesday, February 6**. You can receive extensions on the project deadline and checkpoint deadline, but not on the early deadline, unless you're a DSP student with an accommodation for assignment extensions.

In this project, you will develop a simulator and multiple strategies for the dice game Hog. You will need to use _control statements_ and _higher-order functions_ together, as described in Sections 1.2 through 1.6 of [Composing Programs](https://www.composingprograms.com/), the online textbook.

> When students in the past have tried to implement the functions without thoroughly reading the problem description, they’ve often run into issues. 😱 **Read each description thoroughly before starting to code.**

### Rules[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#rules "Direct link to Rules")

In Hog, two players alternate turns trying to be the first to end a turn with at least `GOAL` total points, where `GOAL` defaults to 100. On each turn, the current player chooses some number of dice to roll, up to 10. That player's score for the turn is the sum of the dice outcomes. However, a player who rolls too many dice risks:

*   **Sow Sad**. If any of the dice outcomes is a 1, the current player's score for the turn is `1`.
    
*   _Example 1:_ The current player rolls 7 dice, 5 of which are 1's. They score `1` point for the turn.
    
*   _Example 2:_ The current player rolls 4 dice, all of which are 3's. Since Sow Sad did not occur, they score `12` points for the turn.
    

In a normal game of Hog, those are all the rules. To spice up the game, we'll include some special rules:

*   **Boar Brawl**. A player who rolls zero dice scores three times the absolute difference between the tens digit of the opponent’s score and the ones digit of the current player’s score, or 1, whichever is higher. The ones digit refers to the rightmost digit and the tens digit refers to the second-rightmost digit. If a player's score is a single digit (less than 10), the tens digit of that player's score is 0.
    
*   _Example 1:_
    
    *   The current player has `21` points and the opponent has `46` points, and the current player chooses to roll zero dice.
    *   The tens digit of the opponent's score is `4` and the ones digit of the current player's score is `1`.
    *   Therefore, the player gains `3 * abs(4 - 1) = 9` points.
*   _Example 2:_
    
    *   The current player has `45` points and the opponent has `52` points, and the current player chooses to roll zero dice.
    *   The tens digit of the opponent's score is `5` and the ones digit of the current player's score is `5`.
    *   Since `3 * abs(5 - 5) = 0`, the player gains `1` point.
*   _Example 3:_
    
    *   The current player has `2` points and the opponent has `5` points, and the current player chooses to roll zero dice.
    *   The tens digit of the opponent's score is `0` and the ones digit of the current player's score is `2`.
    *   Therefore, the player gains `3 * abs(0 - 2) = 6` points.
*   **Sus Fuss**. We call a number [_sus_](https://en.wikipedia.org/wiki/Sus_%28genus%29) if it has exactly 3 or 4 factors, including 1 and the number itself. If, after rolling, the current player's score is a sus number, they gain enough points such that their score instantly increases to the next prime number.
    
*   _Example 1:_
    
    *   A player has 14 points and rolls 2 dice that total 7 points. Their new score would be 21, which has 4 factors: 1, 3, 7, and 21. Because 21 is sus, the score of the player is increased to 23, the next prime number.
*   _Example 2:_
    
    *   A player has 63 points and rolls 5 dice that total 1 point. Their new score would be 64, which has 7 factors: 1, 2, 4, 8, 16, 32, and 64. Since 64 is not sus, the score of the player is unchanged.
*   _Example 3:_
    
    *   A player has 49 points and rolls 5 dice that total 18 points. Their new score would be 67, which is prime and has 2 factors: 1 and 67. Since 67 is not sus, the score of the player is unchanged.

Download starter files[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#download-starter-files "Direct link to Download starter files")
-------------------------------------------------------------------------------------------------------------------------------------------------------------

To get started, download all of the project code as a [zip archive](https://www.learncs.site/assets/files/hog-247bb4344c51ce4e87ef4a43738f291d.zip). Below is a list of all the files you will see in the archive once unzipped. For the project, you'll only be making changes to `hog.py`.

*   `hog.py`: A starter implementation of Hog
*   `dice.py`: Functions for making and rolling dice
*   `hog_gui.py`: A graphical user interface (GUI) for Hog (updated)
*   `ucb.py`: Utility functions for CS 61A
*   `hog_ui.py`: A text-based user interface (UI) for Hog
*   `ok`: CS 61A autograder
*   `tests`: A directory of tests used by `ok`
*   `gui_files`: A directory of various things used by the web GUI

You may notice some files other than the ones listed above too—those are needed for making the autograder and portions of the GUI work. Please do not modify any files other than `hog.py`.

Logistics[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#logistics "Direct link to Logistics")
----------------------------------------------------------------------------------------------------------------------

The project is worth 25 points, of which 1 point is for submitting Phase 1 by the checkpoint date of Tuesday, January 30.

You will turn in the following files:

*   `hog.py`

You do not need to modify or turn in any other files to complete the project. To submit the project, **submit the required files to the appropriate Gradescope assignment.**

For the functions that we ask you to complete, there may be some initial code that we provide. If you would rather not use that code, feel free to delete it and start from scratch. You may also add new function definitions as you see fit.

**However, please do not modify any other functions or edit any files not listed above**. Doing so may result in your code failing our autograder tests. Also, please do not change any function signatures (names, argument order, or number of arguments).

Throughout this project, you should be testing the correctness of your code. It is good practice to test often, so that it is easy to isolate any problems. However, you should not be testing _too_ often, to allow yourself time to think through problems.

We have provided an **autograder** called `ok` to help you with testing your code and tracking your progress. The first time you run the autograder, you will be asked to **log in with your Ok account using your web browser**. Please do so. Each time you run `ok`, it will back up your work and progress on our servers.

The primary purpose of `ok` is to test your implementations.

If you want to test your code interactively, you can run

     python3 ok -q [question number] -i 

with the appropriate question number (e.g. `01`) inserted. This will run the tests for that question until the first one you failed, then give you a chance to test the functions you wrote interactively.

You can also use the debugging print feature in OK by writing

     print("DEBUG:", x) 

which will produce an output in your terminal without causing OK tests to fail with extra output.

Graphical User Interface[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#graphical-user-interface "Direct link to Graphical User Interface")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

A **graphical user interface** (GUI, for short) is provided for you. At the moment, it doesn't work because you haven't implemented the game logic. Once you complete the play function, you will be able to play a fully interactive version of Hog!

Once you've done that, you can run the GUI from your terminal:

    python3 hog_gui.py

Getting Started Videos[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#getting-started-videos "Direct link to Getting Started Videos")
-------------------------------------------------------------------------------------------------------------------------------------------------------------

These videos may provide some helpful direction for tackling the coding problems on this assignment.

> To see these videos, you should be logged into your berkeley.edu email.

[YouTube link](https://youtu.be/playlist?list=PLx38hZJ5RLZebgMROlbtGHlmAbOjDegj5)

Phase 1: Rules of the Game[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#phase-1-rules-of-the-game "Direct link to Phase 1: Rules of the Game")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In the first phase, you will develop a simulator for the game of Hog.

### Problem 0 (0 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-0-0-pt "Direct link to Problem 0 (0 pt)")

The `dice.py` file represents dice using non-pure zero-argument functions. These functions are non-pure because they may have different return values each time they are called, and so a side-effect of calling the function is changing what will be returned when the function is called again.

Here's the documentation from `dice.py` that you need to read in order to simulate dice in this project.

    A dice function takes no arguments and returns a number from 1 to n(inclusive), where n is the number of sides on the dice.Fair dice produce each possible outcome with equal probability.Two fair dice are already defined, four_sided and six_sided,and are generated by the make_fair_dice function.Test dice are deterministic: they always cycles through a fixedsequence of values that are passed as arguments.Test dice are generated by the make_test_dice function.def make_fair_dice(sides):    """Return a die that returns 1 to SIDES with equal chance."""    ...four_sided = make_fair_dice(4)six_sided = make_fair_dice(6)def make_test_dice(...):    """Return a die that cycles deterministically through OUTCOMES.    >>> dice = make_test_dice(1, 2, 3)    >>> dice()    1    >>> dice()    2    >>> dice()    3    >>> dice()    1    >>> dice()    2

Check your understanding by unlocking the following tests.

    python3 ok -q 00 -u

You can exit the unlocker by typing `exit()`.

**Typing Ctrl-C on Windows to exit out of the unlocker has been known to cause problems, so avoid doing so.**

### Problem 1 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-1-2-pt "Direct link to Problem 1 (2 pt)")

Implement the `roll_dice` function in `hog.py`. It takes two arguments: a positive integer called `num_rolls` giving the number of times to roll a die and a `dice` function. It returns the number of points scored by rolling the die that number of times in a turn: either the sum of the outcomes or 1 _(Sow Sad)_.

*   **Sow Sad**. If any of the dice outcomes is a 1, the current player's score for the turn is `1`.
    
*   _Example 1:_ The current player rolls 7 dice, 5 of which are 1's. They score `1` point for the turn.
    
*   _Example 2:_ The current player rolls 4 dice, all of which are 3's. Since Sow Sad did not occur, they score `12` points for the turn.
    

To obtain a single outcome of a dice roll, call `dice()`. You should call `dice()` **exactly `num_rolls` times** in the body of `roll_dice`.

Remember to call `dice()` exactly `num_rolls` times **even if Sow Sad happens in the middle of rolling**. By doing so, you will correctly simulate rolling all the dice together (and the user interface will work correctly).

> **Note:** The `roll_dice` function, and many other functions throughout the project, makes use of _default argument values_—you can see this in the function heading:
> 
>     def roll_dice(num_rolls, dice=six_sided): ...
> 
> The argument `dice=six_sided` means that when `roll_dice` is called, the `dice` argument is **optional**. If no value for `dice` is provided, then `six_sided` is used by default.
> 
> For example, calling `roll_dice(3, four_sided)`, or equivalently `roll_dice(3, dice=four_sided)`, simulates rolling 3 four-sided dice, while calling `roll_dice(3)` simulates rolling 3 six-sided dice.

**Understand the problem**:

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 01 -u

> **Note:** You will not be able to test your code using `ok` until you unlock the test cases for the corresponding question.

**Write code and check your work**:

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 01

Check out the [Debugging Guide](https://cs61a.org/articles/debugging/)!

#### Debugging Tips[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#debugging-tips "Direct link to Debugging Tips")

If the tests don't pass, it's time to debug. You can observe the behavior of your function using Python directly. First, start the Python interpreter and load the `hog.py` file.

    python3 -i hog.py

Then, you can call your `roll_dice` function on any number of dice you want.

    >>> roll_dice(4)

You will find that the previous expression may have a different result each time you call it, since it is simulating random dice rolls. You can also use test dice that fix the outcomes of the dice in advance. For example, rolling twice when you know that the dice will come up 3 and 4 should give a total outcome of 7.

    >>> fixed_dice = make_test_dice(3, 4)>>> roll_dice(2, fixed_dice)7

> On most systems, you can evaluate the same expression again by pressing the up arrow, then pressing enter or return. To evaluate earlier commands, press the up arrow repeatedly.
> 
> If you find a problem, you first need to change your `hog.py` file to fix the problem, and save the file. Then, to check whether your fix works, you'll have to quit the Python interpreter by either using `exit()` or `Ctrl^D`, and re-run the interpreter to test the changes you made. Pressing the up arrow in both the terminal and the Python interpreter should give you access to your previous expressions, even after restarting Python.
> 
> Continue debugging your code and running the `ok` tests until they all pass.
> 
> One more debugging tip: to start the interactive interpreter automatically upon failing an `ok` test, use `-i`. For example, `python3 ok -q 01 -i` will run the tests for question 1, then start an interactive interpreter with `hog.py` loaded if a test fails.

### Problem 2 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-2-2-pt "Direct link to Problem 2 (2 pt)")

Implement `boar_brawl`, which takes the player's current score `player_score` and the opponent's current score `opponent_score`, and returns the number of points scored by Boar Brawl when the player rolls 0 dice.

*   **Boar Brawl**. A player who rolls zero dice scores three times the absolute difference between the tens digit of the opponent’s score and the ones digit of the current player’s score, or 1, whichever is higher. The ones digit refers to the rightmost digit and the tens digit refers to the second-rightmost digit. If a player's score is a single digit (less than 10), the tens digit of that player's score is 0.
    
*   _Example 1:_
    
    *   The current player has `21` points and the opponent has `46` points, and the current player chooses to roll zero dice.
    *   The tens digit of the opponent's score is `4` and the ones digit of the current player's score is `1`.
    *   Therefore, the player gains `3 * abs(4 - 1) = 9` points.
*   _Example 2:_
    
    *   The current player has `45` points and the opponent has `52` points, and the current player chooses to roll zero dice.
    *   The tens digit of the opponent's score is `5` and the ones digit of the current player's score is `5`.
    *   Since `3 * abs(5 - 5) = 0`, the player gains `1` point.
*   _Example 3:_
    
    *   The current player has `2` points and the opponent has `5` points, and the current player chooses to roll zero dice.
    *   The tens digit of the opponent's score is `0` and the ones digit of the current player's score is `2`.
    *   Therefore, the player gains `3 * abs(0 - 2) = 6` points.

> Don't assume that scores are below 100. Write your `boar_brawl` function so that it works correctly for any non-negative score.

> **Important:** Your implementation should **not** use `str`, lists, or contain square brackets `[` `]`. The test cases will check if those have been used.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 02 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 02

You can also test `boar_brawl` interactively by running `python3 -i hog.py` from the terminal and calling `boar_brawl` on various inputs.

### Problem 3 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-3-2-pt "Direct link to Problem 3 (2 pt)")

Implement the `take_turn` function, which returns the number of points scored for a turn by rolling the given `dice` `num_rolls` times.

Your implementation of `take_turn` should call both `roll_dice` and `boar_brawl` rather than repeating their implementations.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 03 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 03

### Problem 4 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-4-2-pt "Direct link to Problem 4 (2 pt)")

First, implement `num_factors`, which takes in a positive integer `n` and determines the number of factors that `n` has.

> 1 and `n` are both factors of `n`!

After, implement `sus_points` and `sus_update`.

*   `sus_points` takes in a player's score and returns the player's new score after applying the Sus Fuss rule (for example, `sus_points(5)` should return `5` and `sus_points(21)` should return `23`). You should use `num_factors` and the provided `is_prime` function in your implementation.
*   `sus_update` returns a player's total score after they roll `num_rolls` dice, taking both Boar Brawl and Sus Fuss into account. You should use `sus_points` in this function.

> **Hint:** You can look at the implementation of `simple_update` provided in `hog.py` and use that as a starting point for your `sus_update` function.

*   **Sus Fuss**. We call a number [_sus_](https://en.wikipedia.org/wiki/Sus_%28genus%29) if it has exactly 3 or 4 factors, including 1 and the number itself. If, after rolling, the current player's score is a sus number, they gain enough points such that their score instantly increases to the next prime number.
    
*   _Example 1:_
    
    *   A player has 14 points and rolls 2 dice that total 7 points. Their new score would be 21, which has 4 factors: 1, 3, 7, and 21. Because 21 is sus, the score of the player is increased to 23, the next prime number.
*   _Example 2:_
    
    *   A player has 63 points and rolls 5 dice that total 1 point. Their new score would be 64, which has 7 factors: 1, 2, 4, 8, 16, 32, and 64. Since 64 is not sus, the score of the player is unchanged.
*   _Example 3:_
    
    *   A player has 49 points and rolls 5 dice that total 18 points. Their new score would be 67, which is prime and has 2 factors: 1 and 67. Since 67 is not sus, the score of the player is unchanged.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 04 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 04

### Problem 5 (4 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-5-4-pt "Direct link to Problem 5 (4 pt)")

Implement the `play` function, which simulates a full game of Hog. Players take turns rolling dice until one of the players reaches the `goal` score, and the final scores of both players are returned by the function.

To determine how many dice are rolled each turn, call the current player's strategy function (Player 0 uses `strategy0` and Player 1 uses `strategy1`). A _strategy_ is a function that, given a player's score and their opponent's score, returns the number of dice that the current player will roll in the turn. An example strategy is `always_roll_5` which appears above `play`.

To determine the updated score for a player after they take a turn, call the `update` function. An `update` function takes the number of dice to roll, the current player's score, the opponent's score, and the dice function used to simulate rolling dice. It returns the updated score of the current player after they take their turn. Two examples of `update` functions are `simple_update` and`sus_update`.

If a player achieves the goal score by the end of their turn, i.e. after all applicable rules have been applied, the game ends. `play` will then return the final total scores of both players, with Player 0's score first and Player 1's score second.

Some example calls to `play` are:

*   `play(always_roll_5, always_roll_5, simple_update)` simulates two players that both always roll 5 dice each turn, playing with just the Sow Sad and Boar Brawl rules.
*   `play(always_roll_5, always_roll_5, sus_update)` simulates two players that both always roll 5 dice each turn, playing with the Sus Fuss rule in addition to the Sow Sad and Boar Brawl rules (i.e. all the rules).

> **Important:** For the user interface to work, a strategy function should be called only once per turn. Only call `strategy0` when it is Player 0's turn and only call `strategy1` when it is Player 1's turn.
> 
> **Hints**:
> 
> *   If `who` is the current player, the next player is `1 - who`.
> *   To call `play(always_roll_5, always_roll_5, sus_update)` and print out what happens each turn, run `python3 hog_ui.py` from the terminal.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 05 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 05

Check to make sure that you completed all the problems in Phase 1:

    python3 ok --score

Then, submit your work **to Gradescope** before the checkpoint deadline:

When you run `ok` commands, you'll still see that some tests are locked because you haven't completed the whole project yet. You'll get full credit for the checkpoint if you complete all the problems up to this point.

**Congratulations! You have finished Phase 1 of this project!**

Interlude: User Interfaces[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#interlude-user-interfaces "Direct link to Interlude: User Interfaces")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------

> There are no required problems in this section of the project, just some examples for you to read and understand. See Phase 2 for the remaining project problems.

### Printing Game Events[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#printing-game-events "Direct link to Printing Game Events")

We have built a simulator for the game, but haven't added any code to describe how the game events should be displayed to a person. Therefore, we've built a computer game that no one can play. (Lame!)

However, the simulator is expressed in terms of small functions, and we can replace each function by a version that prints out what happens when it is called. Using higher-order functions, we can do so without changing much of our original code. An example appears in `hog_ui.py`, which you are encouraged to read.

The `play_and_print` function calls the same `play` function just implemented, but using:

*   new strategy functions (e.g., `printing_strategy(0, always_roll_5)`) that print out the scores and number of dice rolled.
*   a new update function (`sus_update_and_print`) that prints the outcome of each turn.
*   a new dice function (`printing_dice(six_sided)`) that prints the outcome of rolling the dice.

Notice how much of the original simulator code can be reused.

Running `python3 hog_ui.py` from the terminal calls `play_and_print(always_roll_5, always_roll_5)`.

### Accepting User Input[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#accepting-user-input "Direct link to Accepting User Input")

The built-in `input` function waits for the user to type a line of text and then returns that text as a string. The built-in `int` function can take a string containing the digits of an integer and return that integer.

The `interactive_strategy` function returns a strategy that let's a person choose how many dice to roll each turn by calling `input`.

With this strategy, we can finally play a game using our `play` function:

Running `python3 hog_ui.py -n 1` from the terminal calls `play_and_print(interactive_strategy(0), always_roll_5)`, which plays a game betweem a human (Player 0) and a computer strategy that always rolls 5.

Running `python3 hog_ui.py -n 2` from the terminal calls `play_and_print(interactive_strategy(0), interactive_strategy(1))`, which plays a game between two human players.

You are welcome to change `hog_ui.py` in any way you want, for example to use different strategies than `always_roll_5`.

### Graphical User Interface (GUI)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#graphical-user-interface-gui "Direct link to Graphical User Interface (GUI)")

We have also provided a web-based graphical user interface for the game using a similar approach as `hog_ui.py` called `hog_gui.py`. You can run it from the terminal:

    python3 hog_gui.py

Like `hog_ui.py`, the GUI relies on your simulator implementation, so if you have any bugs in your code, they will be reflected in the GUI. This means you can also use the GUI as a debugging tool; however, it's better to run the tests first.

The source code for the Hog GUI is [publicly available on Github](https://github.com/Cal-CS-61A-Staff/cs61a-apps/tree/master/hog) but involves several other programming languages: Javascript, HTML, and CSS.

Phase 2: Strategies[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#phase-2-strategies "Direct link to Phase 2: Strategies")
---------------------------------------------------------------------------------------------------------------------------------------------------

In this phase, you will experiment with ways to improve upon the basic strategy of always rolling five dice. A _strategy_ is a function that takes two arguments: the current player's score and their opponent's score. It returns the number of dice the player will roll, which can be from 0 to 10 (inclusive).

### Problem 6 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-6-2-pt "Direct link to Problem 6 (2 pt)")

Implement `always_roll`, a higher-order function that takes a number of dice `n` and returns a strategy that always rolls `n` dice. Thus, `always_roll(5)` would be equivalent to `always_roll_5`.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 06 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 06

### Problem 7 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-7-2-pt "Direct link to Problem 7 (2 pt)")

A strategy only has a fixed number of possible argument values. For example, in a game to 100, there are 100 possible `score` values (0-99) and 100 possible `opponent_score` values (0-99), giving 10,000 possible argument combinations.

Implement `is_always_roll`, which takes a strategy and returns whether that strategy always rolls the same number of dice for every possible argument combination up to `goal` points.

> **Reminder:** The game continues until one player reaches `goal` points (in the above example, `goal` is set to `100`). Make sure your solution accounts for every possible combination for the specified `goal` argument.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 07 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 07

### Problem 8 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-8-2-pt "Direct link to Problem 8 (2 pt)")

Implement `make_averaged`, which is a higher-order function that takes a function `original_function` as an argument.

The return value of `make_averaged` is a function that takes in the same number of arguments as `original_function`. When we call this returned function on the arguments, it will return the average value of repeatedly calling `original_function` on the arguments passed in.

Specifically, this function should call `original_function` a total of `samples_count` times and return the average of the results of these calls.

> **Important:** To implement this function, you will need to use a new piece of Python syntax. We would like to write a function that accepts an arbitrary number of arguments, and then calls another function using exactly those arguments. Here's how it works.
> 
> Instead of listing formal parameters for a function, you can write `*args`, which represents all of the **arg**ument**s** that get passed into the function. We can then call another function with these same arguments by passing these `*args` into this other function. For example:
> 
>     >>> def printed(f):...     def print_and_return(*args):...         result = f(*args)...         print('Result:', result)...         return result...     return print_and_return>>> printed_pow = printed(pow)>>> printed_pow(2, 8)Result: 256256>>> printed_abs = printed(abs)>>> printed_abs(-10)Result: 1010
> 
> Here, we can pass any number of arguments into `print_and_return` via the `*args` syntax. We can also use `*args` inside our `print_and_return` function to make another function call with the same arguments.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 08 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 08

### Problem 9 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-9-2-pt "Direct link to Problem 9 (2 pt)")

Implement `max_scoring_num_rolls`, which runs an experiment to determine the number of rolls (from 1 to 10) that gives the maximum average score for a turn. Your implementation should use `make_averaged` and `roll_dice`.

If two numbers of rolls are tied for the maximum average score, return the lower number. For example, if both 3 and 6 achieve a maximum average score, return 3.

You might find it useful to read the doctest and the example shown in the doctest for this problem before doing the unlocking test.

> **Important:** In order to pass all of our tests, please make sure that you are testing dice rolls starting from 1 going up to 10, rather than from 10 to 1.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 09 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 09

### Running Experiments[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#running-experiments "Direct link to Running Experiments")

The provided `run_experiments` function calls `max_scoring_num_rolls(six_sided)` and prints the result. You will likely find that rolling 6 dice maximizes the result of `roll_dice` using six-sided dice.

To call this function and see the result, run `hog.py` with the `-r` flag:

    python3 hog.py -r

In addition, `run_experiments` compares various strategies to `always_roll(6)`. You are welcome to change the implementation of `run_experiments` as you wish. Note that running experiments with `boar_strategy` and `sus_strategy` will not have accurate results until you implement them in the next two problems.

Some of the experiments may take up to a minute to run. You can always reduce the number of trials in your call to `make_averaged` to speed up experiments.

Running experiments won't affect your score on the project.

### Problem 10 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-10-2-pt "Direct link to Problem 10 (2 pt)")

A strategy can try to take advantage of the _Boar Brawl_ rule by rolling 0 when it is most beneficial to do so. Implement `boar_strategy`, which returns 0 whenever rolling 0 would give **at least** `threshold` points and returns `num_rolls` otherwise. This strategy should **not** also take into account the Sus Fuss rule.

> **Hint**: You can use the `boar_brawl` function you defined in Problem 2.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 10 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 10

You should find that running `python3 hog.py -r` now shows a win rate for `boar_strategy` close to 66-67%.

### Problem 11 (2 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#problem-11-2-pt "Direct link to Problem 11 (2 pt)")

A better strategy will take advantage of both _Boar Brawl_ and _Sus Fuss_ in combination. For example, if a player has 53 points and their opponent has 60, rolling 0 would bring them to 62, which is a sus number, and so they would end the turn with 67 points: a gain of 67 - 53 = 14!

The `sus_strategy` returns 0 whenever rolling 0 would result in a score that is **at least** `threshold` points more than the player's score at the start of turn.

> **Hint**: You can use the `sus_update` function.

Before writing any code, unlock the tests to verify your understanding of the question:

    python3 ok -q 11 -u

Once you are done unlocking, begin implementing your solution. You can check your correctness with:

    python3 ok -q 11

You should find that running `python3 hog.py -r` now shows a win rate for `sus_strategy` close to 67-69%.

### Optional: Problem 12 (0 pt)[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#optional-problem-12-0-pt "Direct link to Optional: Problem 12 (0 pt)")

Implement `final_strategy`, which combines these ideas and any other ideas you have to achieve a high win rate against the baseline strategy. Some suggestions:

*   If you know the goal score (by default it is 100), there's no benefit to scoring more than the goal. Check whether you can win by rolling 0, 1 or 2 dice. If you are in the lead, you might decide to take fewer risks.
*   Instead of using a threshold, roll 0 whenever it would give you more points on average than rolling 6.

You can check that your final strategy is valid by running `ok`.

    python3 ok -q 12

Project submission[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/hog#project-submission "Direct link to Project submission")
-------------------------------------------------------------------------------------------------------------------------------------------------

Run `ok` on all problems to make sure all tests are unlocked and pass:

    python3 ok

You can also check your score on each part of the project:

    python3 ok --score

Once you are satisfied, submit this assignment by uploading `hog.py` **to Gradescope.** For a refresher on how to do this, refer to [Lab 00](https://cs61a.org/lab/lab00/#task-c-submitting-the-assignment).

You can add a partner to your Gradescope submission by clicking on **+ Add Group Member** under your name on the right hand side of your submission. Only one partner needs to submit to Gradescope.

**Congratulations, you have reached the end of your first CS 61A project!** If you haven't already, relax and enjoy a few games of Hog with a friend.