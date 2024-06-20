Discussion 5 | CS 61A Spring 2024
=================================

Discussion 5: Trees[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc05#discussion-5-trees "Direct link to Discussion 5: Trees")
--------------------------------------------------------------------------------------------------------------------------------------------------

*   [disc05.pdf](https://www.learncs.site/assets/files/disc05-2cf1b0e996095933053755a467d5a939.pdf)

Pick someone in your group to [join Discord](https://cs61a.org/articles/discord). It's fine if multiple people join, but one is enough.

Now switch to Pensieve:

*   **Everyone**: Go to [discuss.pensieve.co](http://discuss.pensieve.co/) and log in with your @berkeley.edu email, then enter your group number. (Your group number is the number of your Discord channel.)

Once you're on Pensieve, you don't need to return to this page; Pensieve has all the same content (but more features). If for some reason Penseive doesn't work, return to this page and continue with the discussion.

Post in the `#help` channel on [Discord](https://cs61a.org/articles/discord/) if you have trouble.

Getting Started[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc05#getting-started "Direct link to Getting Started")
---------------------------------------------------------------------------------------------------------------------------------------

Everyone go around and say your name, just in case someone forgot.

**For fun:** Think of a big word with at least three syllables, such as "solitary" or "conundrum" or "ominous". Try to use it as many times as you can during today's discussion, but in ways that don't give away that it's your big word. At the end, your group will try to guess each person's big word. Whoever uses their big word the most times (and at least twice) without their group guessing it wins. (You win nothing; it's just a game.)

**To get help from a TA**, send a message to the `discuss-queue` channel with the @discuss tag and your discussion group number.

If you have fewer than 4 people in your group, you can merge with another group in the room with you.

The most common suggestion from last discussion was to add some hints, so we have. The second most common suggestion was to encourage more discussion and collaboration. Discuss and collaborate!

Trees[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc05#trees "Direct link to Trees")
---------------------------------------------------------------------------------------------------------

For a tree `t`:

*   Its root label can be any value, and `label(t)` returns it.
*   Its branches are trees, and `branches(t)` returns a list of branches.
*   An identical tree can be constructed with `tree(label(t), branches(t))`.
*   You can call functions that take trees as arguments, such as `is_leaf(t)`.
*   That's how you work with trees. No `t == x` or `t[0]` or `x in t` or `list(t)`, etc.
*   There's no way to change a tree (that doesn't violate an abstraction barrier).

Here's an example tree `t1`, for which its branch `branches(t1)[1]` is `t2`.

    t2 = tree(5, [tree(6), tree(7)])t1 = tree(3, [tree(4), t2])

![Example Tree](https://www.learncs.site/assets/images/example_tree_illustration-f92648cd31ed7e203a304e16bd59c08a.png)

A path is a sequence of trees in which each is the parent of the next.

You don't need to know how `tree`, `label`, and `branches` are implemented in order to use them correctly, but here is the implementation from lecture.

    def tree(label, branches=[]):    for branch in branches:        assert is_tree(branch), 'branches must be trees'    return [label] + list(branches)def label(tree):    return tree[0]def branches(tree):    return tree[1:]def is_leaf(tree):    return not branches(tree)def is_tree(tree):    if type(tree) != list or len(tree) < 1:        return False    for branch in branches(tree):        if not is_tree(branch):            return False    return True

### Q1: Warm Up[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc05#q1-warm-up "Direct link to Q1: Warm Up")

What value is bound to `result`?

    result = label(min(branches(max([t1, t2], key=label)), key=label))

How convoluted! (That's a big word.)

Here's a quick refresher on how `key` functions work with `max` and `min`,

`max(s, key=f)` returns the item `x` in `s` for which `f(x)` is largest.

    >>> s = [-3, -5, -4, -1, -2]>>> max(s)-1>>> max(s, key=abs)-5>>> max([abs(x) for x in s])5

Therefore, `max([t1, t2], key=label)` returns the tree with the largest label, in this case `t2`.

In case you're wondering, this expression does not violate an abstraction barrier. `[t1, t2]` and `branches(t)` are both lists (not trees), and so it's fine to call `min` and `max` on them.

### Q2: Has Path[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc05#q2-has-path "Direct link to Q2: Has Path")

Implement `has_path`, which takes a tree `t` and a list `p`. It returns whether there is a path from the root of `t` with labels `p`. For example, `t1` has a path from its root with labels `[3, 5, 6]` but not `[3, 4, 6]` or `[5, 6]`.

**Important**: Before trying to implement this function, discuss these questions from lecture about the recursive call of a tree processing function:

*   What recursive calls will you make?
*   What type of values do they return?
*   What do the possible return values mean?
*   How can you use those return values to complete your implementation?

If you get stuck, you can view our answers to these questions by clicking the hint button below, but _please_ don't do that until your whole group agrees.

**What recursive calls will you make?**

As you usual, you will call `has_path` on each branch `b`. You'll make this call after comparing `p[0]` to `label(t)`, and so the second argument to `has_path` will be the rest of `p`: `has_path(b, p[1:])`.

**What type of values do they return?**

`has_path` always returns a `bool` value: `True` or `False`.

**What do the possible return values mean?**

If `has_path(b, p[1:])` returns `True`, then there is a path through branch `b` for which `p[1:]` are the node labels.

**How can you use those return values to complete your implementation?**

If you have already checked that `label(t)` is equal to `p[0]`, then a `True` return value means there is a path through `t` with labels `p` using that branch `b`. A `False` value means there is no path through that branch, but there might be path through a different branch.

Run in 61A Code

If your group needs some guidance, you can click on the hints below, but please talk with your group first before reading the hints.

The first base case should check whether `p` is a list of length one with the label of `t` as its only element. The second base case should check if the first element of `p` matches the label of `t`.

When entering the recursive case, your code should already have checked that `p[0]` is equal to `label(t)`, and so all that's left to check is that `p[1:]` contains the labels in a path through one of the branches. One way is with this template:

    for ____:    if ____:        return Truereturn False

**Discussion Time!** Can the `else` case of `has_path` be written in just one line? Why or why not? You can ignore how fast the function will run. When your group has an answer, send a message to the discuss-queue channel with the @discuss tag, your discussion group number, and the message "Maybe?" and a member of the course staff will join your voice channel to hear your answer and give feedback.

### Q3: Find Path[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc05#q3-find-path "Direct link to Q3: Find Path")

Implement `find_path`, which takes a tree `t` with unique labels and a value `x`. It returns a list containing the labels of the nodes along a path from the root of `t` to a node labeled `x`.

If `x` is not a label in `t`, return `None`. Assume that the labels of `t` are unique.

First talk through how to make and use the recursive call. (Try it yourselves; don't just click the hint button. That's how you learn.)

**What recursive calls will you make?**

`find_path(b, x)` on each branch `b`.

**What type of values do they return?**

Each recursive call will either return `None` or a non-empty list of node labels.

**What do the possible return values mean?**

If `find_path(b, x)` returns `None`, then `x` does not appear in `b`. If `find_path(b, x)` returns a list, then it contains the node labels for a path through `b` that ends with the node labeled `x`.

**How can you use those return values to complete your implementation?**

If a list is returned, then it contains all of the labels in the path except `label(t)`, which must be placed at the front.

Run in 61A Code

Please don't view the hints until you've discussed with your group and can't make progress.

If `x` is the label of `t`, then return a list with one element that contains the label of `t`.

Assign `path` to the result of a recursive call to `find_path(b, x)` so that you can both check whether it's `None` and extend it if it's a list.

For a list `path` and a value `v`, the expression `[v] + path` creates a longer list that starts with `v` and then has the elements of `path`.

**Description Time!** When your group has completed this question, it's time to describe why this function does not have a base case that uses `is_leaf`. Come up with an explanation as a group, pick someone to present your answer, and then send a message to the discuss-queue channel with the @discuss tag, your discussion group number, and the message "Found it!" and a member of the course staff will join your voice channel to hear your description and give feedback.

Document the Occasion[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc05#document-the-occasion "Direct link to Document the Occasion")
---------------------------------------------------------------------------------------------------------------------------------------------------------

For each person, the rest of the group should try to guess their _big word_ (from the Getting Started section). The group only gets one guess. After they guess, reveal your _big word_ and how many times you used it during discussion.

Please all fill out the [attendance form](https://docs.google.com/forms/d/e/1FAIpQLSeqlK8l6WkScGr-RHR-kM4p5bnR9cllYrG95fDqPJspSlll7A/viewform) (one submission per person per week).