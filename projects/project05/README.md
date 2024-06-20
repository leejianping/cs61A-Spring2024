Optional Contest: Scheme Art | CS 61A Spring 2024
=================================================

Optional Contest: Scheme Art[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/scheme_contest#optional-contest-scheme-art "Direct link to Optional Contest: Scheme Art")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   [scheme\_contest.zip](https://www.learncs.site/assets/files/scheme_contest-9cd30ff71e159090e06d9952e990e0cb.zip)

> The output is art,  
> But what about its source code?  
> It's just as abstract.

Instructions[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/scheme_contest#instructions "Direct link to Instructions")
------------------------------------------------------------------------------------------------------------------------------------------

> This contest is completely optional!

Entries are due at **11:59pm on Wednesday, April 24th.**

Here are the steps to enter the contest:

1.  Download [scheme\_contest.zip](https://www.learncs.site/assets/files/scheme_contest-9cd30ff71e159090e06d9952e990e0cb.zip).
    
2.  Download the file `abstract_turtle.zip` from [this link](https://www.learncs.site/assets/files/abstract_turtle-0b04ea2c0963973049d299d600173c80.zip). Then, unzip the file into your `scheme_contest` directory. The unzipped folder should contain files including `canvas.py` and `color_names.py`. Alternatively, if you'd prefer to install using the `pip` command, you can run `pip3 install abstract-turtle` instead of downloading this zip file.
    
3.  Complete the `contest.scm` file (you can render your drawing with `python3 scheme contest.scm --pillow-turtle --turtle-save-path output`). See the [Scheme Built-in Reference on graphics](https://cs61a.org/articles/scheme-builtins/#turtle-graphics) for a description of drawing procedures.
    
    *   If this command doesn't work, try running `python3 scheme contest.scm --turtle-save-path output` instead. The main difference is that this command uses the `tkinter` library, while the former command uses the `pillow` library. Both should generate the same output.
4.  Upload `output.png` which was created by the previous command.
    

In `contest.scm`, the `draw` procedure should draw your entry and then exit on click.

All entries, including their source code, will be distributed to your fellow students for voting. Please **do not include personal info in your submission.**

> **Important:** when you are ready to submit, follow **both** these steps:
> 
> *   Submit your `contest.scm` file to the **Scheme Contest** assignment on Gradescope.
> *   Fill out the [contest form](https://forms.gle/FtHnvNcx1jRvZLDS7). Make sure the information here is correct, since we'll be using it to generate your entry in the Scheme art gallery.
> 
> **Troubleshooting:** Are you experiencing the error `name 'builtins' is not defined` when trying to render your artwork? If so, add the following line to the top of `scheme_builtins.py`: `import builtins`. You might also be asked to install some dependencies when you try to render your image, and if you do so, it should properly create your visualization. If you don't see this error (it has usually been popping up for select Windows users), you do not need to add the additional import.

Contest Description[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/scheme_contest#contest-description "Direct link to Contest Description")
---------------------------------------------------------------------------------------------------------------------------------------------------------------

Create a visualization of an iterative or recursive process of your choosing, using turtle graphics. Your implementation must be written entirely in Scheme using the interpreter you have built. All computation must be done in Scheme.

We will have two categories of submissions:

*   _Featherweight_: Fewer than 512 Scheme tokens (including parentheses)
*   _Heavyweight_: Fewer than 4096 Scheme tokens (including parentheses)

**No single token may contain more than 50 characters.** If your entry requires more tokens than are allowed in the heavyweight category, please contact the course staff for special permission to submit an even longer entry.

You can check the number of tokens in a Scheme file called `contest.scm` by running the following command:

    python3 scheme_tokens.py contest.scm

Entries (code and images) will be posted online, and winners will be selected by popular vote. The top three entries in each category will be announced on Ed after voting is closed.

To improve your chance of success, you are welcome to include a title and descriptive [haiku](http://en.wikipedia.org/wiki/Haiku) in the comments of your entry, which will be included in the voting.

Contest Rules[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/scheme_contest#contest-rules "Direct link to Contest Rules")
---------------------------------------------------------------------------------------------------------------------------------------------

Before submission, please ensure that your entry abides by these guidelines:

*   Entries must not contain tokens that contain more than 50 characters and must be submitted under the correct category (featherweight/heavyweight).
*   Entries must not contain any political content.
*   Entries must not contain any offensive, sexually explicit, or ethically objectionable content.
*   Entries must not contain any personal information.
*   Entries must match your code. That is, the Scheme code you submit must be able to exactly generate the output graphic file you submit.
*   Entries must be static images (no animations). We encourage you to experiment with animations on your own, but you may not submit animated artwork for this contest.

We reserve the right to disqualify any entries that do not follow these guidelines.

Past Entries[​](https://www.learncs.site/docs/curriculum-resource/cs61a/project/scheme_contest#past-entries "Direct link to Past Entries")
------------------------------------------------------------------------------------------------------------------------------------------

For inspiration, you can peruse these galleries of past entries. Please note that certain submissions may not follow the current guidelines.

*   [Fall 2023]
*   [Summer 2023]
*   [Spring 2023]
*   [Fall 2022]
*   [Summer 2022]
*   [Spring 2022](https://github.com/caiscoding/CS61A-Spring2022/tree/main)
*   [Fall 2021]
*   [Summer 2021]
*   [Spring 2021]
*   [Fall 2020]
*   [Summer 2020]
*   [Spring 2020]
*   [Fall 2019]
*   [Summer 2019]
*   [Spring 2019]
*   [Fall 2018]
*   [Summer 2018]
*   [Spring 2018]
*   [Fall 2017]
*   [Summer 2017]
*   [Spring 2017]
*   [Fall 2016]
*   [Summer 2016]
*   [Spring 2016]
*   [Fall 2015]
*   [Spring 2015]
*   [Fall 2014]
*   [Spring 2014]
*   [Fall 2013]
*   [Spring 2013]
*   [Fall 2012]