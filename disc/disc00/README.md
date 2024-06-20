Discussion 0 | CS 61A Spring 2024
=================================

Discussion 0: Getting Started[​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc00#discussion-0-getting-started "Direct link to Discussion 0: Getting Started")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   [disc00.pdf](https://www.learncs.site/assets/files/disc00-fd55edbc1ffb6617f04d8cf499aa0693.pdf)

Congratulations, you found the Discussion 0 worksheet!

To find your discussion room, check your email. Unless you opted for the mega section, you should have received an email with your discussion group number, location, and time. All discussion groups meet in person. There are multiple groups at a time in each discussion room, so when you arrive, find your group.

Please start on Berkeley time, 10 minutes after the scheduled start time (12:40, 2:10, or 3:40). Feel free to introduce yourself to the rest of your group while you wait (and check that they really have the same group number as you do).

If you need help at any time, [join Discord](https://cs61a.org/articles/discord) and message `@discuss` in the `#help` channel. You can also email our course manager Jenna about any scheduling issues: [jiyeonwoo@berkeley.edu](mailto:jiyeonwoo@berkeley.edu)

Part 0: Meet your group and learn their names \[5 minutes\][​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc00#part-0-meet-your-group-and-learn-their-names-5-minutes "Direct link to part-0-meet-your-group-and-learn-their-names-5-minutes")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Order yourselves by birthday: January 1 at the start and December 31 at the end. Then, on your turn, say your name and where you're from, then say the same information for each person who had a turn already, starting from the most recent turn. For example, the intros might go:

*   **Eva**: I'm Eva from Minneapolis
*   **Lem**: I'm Lem from San Diego, and \[turning to Eva\] you're Eva from Minneapolis
*   **Alyssa**: I'm Alyssa from Sacramento, \[turning to Lem\] you're Lem from San Diego, and \[turning to Eva\] you're Eva from Minneapolis.

If you forget someone's name or where they're from, that's fine; everybody is here to learn. When it's someone's turn, give them time to try themselves, but if they need help, offer it.

_Tip_: Now is a great time to write down the names of the people in your group so that you can look them up later.

**Find your facilitator:** Now figure out who will be your facilitator for the rest of the discussion. Your facilitator is a group member who gets things started in various ways.

*   If you received an email saying that you're a facilitator, please let everyone know now by saying, "I'm the facilitator."
*   If there is no facilitator in your group for some reason, then the person with the latest birthday is the facilitator for today.
*   If there is more than one facilitator in your group for some reason, then the one with the latest birthday is the facilitator for today.

Part 1: Connect to Discord and Pensieve \[5 minutes\][​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc00#part-1-connect-to-discord-and-pensieve-5-minutes "Direct link to part-1-connect-to-discord-and-pensieve-5-minutes")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Pick someone in your group to [join Discord](https://cs61a.org/articles/discord), find your group's channel, and post "Hello, Staff!" in your group's Discord [text channel](https://support.discord.com/hc/en-us/articles/4412085582359-Text-Channels-Text-Chat-In-Voice-Channels#h_01FMJT412WBX1MR4HDYNR8E95X). It's fine if multiple people join, but one is enough.

There's a better version of this worksheet that helps groups collaborate. Join it now:

*   **Everyone**: Go to [discuss.pensieve.co](http://discuss.pensieve.co/) and log in with your @berkeley.edu email.
*   **Facilitator**: Click "Create Room" and share the room code (boxed in red in the screenshot below) with your group.
*   **Others**: Don't create a room; instead, click "Join Room" after typing in the room code that the facilitator shared with you.
*   Post in the `#help` channel on Discord if you have trouble.

![Pensieve room](https://www.learncs.site/assets/images/img3-e5592b88a990b145e54642835899ebd3.png)

Once you're on Pensieve, you don't need to return to this page; Pensieve has all the same content (but more features). If for some reason Penseive doesn't work, return to this page and continue with the discussion.

Part 2: Learn about each other \[30 minutes\][​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc00#part-2-learn-about-each-other-30-minutes "Direct link to part-2-learn-about-each-other-30-minutes")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Here's a game called partitions. Each round, you will split your group into two halves with equal numbers of people (or differing by 1 if there are an odd number of people). The goal is for both groups to find a rare fact that all of their members have in common, that no one in the other group also has in common. For example, Group A may find that they are all left-handed, while Group B may find that they all collect Pokémon cards. For each round follow these steps:

*   Step 1: Split into two equal halves (or differing by 1).
*   Step 2: The two groups separate for 10 minutes to talk and find some rare fact about them that they all share.
*   Step 3: After 10 minutes, regroup and have each group give their shared fact. If no one in the opposing group has that fact in common as well, then everyone in your group scores a point. (So in the above example, if Group A’s fact is that they’re all left-handed, and no one in Group B is left-handed, everyone in Group A scores a point.)

Play for 2 rounds using 2 different ways of splitting your group into halves.

**Important**: The facts you choose _cannot_ be determined by sight (such as height or hair color). They also _cannot_ be based on preferences (such as favorite TV show). Some ideas:

*   Places you've been: Paris, Disneyland, In-N-Out
*   Things you've tried: zip-lining, meditation, fishing
*   Stuff you can do: ski, crochet, juggle, recite digits of pi

When you're done, it's time for the final challenge! Find a fact that's true about all of you but you don't think is true of your TA. When you're ready, send a message to @discuss in your group's Discord [text channel](https://support.discord.com/hc/en-us/articles/4412085582359-Text-Channels-Text-Chat-In-Voice-Channels#h_01FMJT412WBX1MR4HDYNR8E95X) that says, "Fact time!" Wait for a TA to join, share your fact, and see if it's true of them too. Any facts related to age or education are off limits for the final challenge.

Part 3: Solve a problem together \[30 minutes\][​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc00#part-3-solve-a-problem-together-30-minutes "Direct link to part-3-solve-a-problem-together-30-minutes")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Imagine you can call only the following three functions:

*   `f(x)`: Subtracts one from an integer `x`
*   `g(x)`: Doubles an integer `x`
*   `h(x, y)`: Concatenates the digits of two different positive integers `x` and `y`. For example, `h(789, 12)` evaluates to `78912` and `h(12, 789)` evaluates to `12789`.

**Definition**: A _small expression_ is a call expression that contains only `f`, `g`, `h`, the number 5, and parentheses. All of these can be repeated. For example, `h(g(5), f(f(5)))` is a small expression that evaluates to 103.

What's the shortest _small expression_ you can find that evaluates to 2024?

Part 4: Document the occasion \[5 minutes\][​](https://www.learncs.site/docs/curriculum-resource/cs61a/dis/disc00#part-4-document-the-occasion-5-minutes "Direct link to part-4-document-the-occasion-5-minutes")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Take a group selfie and add it to the [text chat of your group's Discord channel](https://support.discord.com/hc/en-us/articles/4412085582359-Text-Channels-Text-Chat-In-Voice-Channels#h_01FMJT412WBX1MR4HDYNR8E95X).

Then, please all fill out the [attendance form](https://forms.gle/yH4KNcMN4VSd6mGG6) (one submission per person per week).

You're done! It's ok if you finish early. You can leave, or you can hang out and discuss how you might use a computer to find the shortest possible _small expression_ that evaluates to 2024. We'll talk about this in Lecture 2.