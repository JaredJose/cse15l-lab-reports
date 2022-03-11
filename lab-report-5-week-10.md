# Lab Report 5 - Week 10
**Objective:** This report will highlight differences in my lab groups implementation of markdown-parse compared to the provided implementation of markdown-parse when ran against the commonmark-spec tests. 

## Isolating Differences
---
In order to highlight differences in the outputs, we used an implementation of `getLinks()` which worked on a file directory versus just a singular `.md` file. We then saved the output of said run to a file called `results.txt`. We did this process for both our groups implementation of MarkdownParse and the provided implementation of MarkdownParse. Then, in order to highlight the differences between our implementation and the provided implementation, we used the `diff` command to compare the `results.txt` files. 

The actual command that I ran on my `ieng6` instance is as follows: 

```diff ~/week9/jared-md-parse/markdown-parse/results.txt ~/week9/markdown-parse/results.txt```. 

The resulting output of this is:

![Image](/images/report5/diff_output.png)

## Test Difference 1: test file `201.md`
---
Contents of `201.md`: 

![Image](/images/report5/201-contents.png)

Our implementation of markdown-parse produced the output of `[]`. The provided implementation of markdown-parse produced the output of `[baz]`. The correct output is `[]`. 

The potential location of the problem within the provided implementation of markdown-parse is located here: 

![Image](/images/report5/201-potential-problem.png)

This snippet is problematic because it does ensure that there is no gap between the `)` and the `[` in the potential link. The line merely checks for if there exists a space or a new line inside the potential link before adding it to the list of links. There should be more checks here to ensure that the `potentialLink` is actually a link. 

## Test Difference 1: test file `489.md`
---
Contents of `489.md`:

![Image](/images/report5/489-contents.png)

Our implementation of markdown-parse produced the output of `[foo bar]` (with foo and bar on separate lines) while the provided implementation of markdown-parse produced the output of `[]`. The correct output is `[]`. 

The location of the problem within our group's implementation of markdown-parse is located here: 

![Image](/images/report5/489-potential-problem.png)

This snippet is problematic because it does not check to see if there is a new-line character insde of the link portion of the sequence. A new-line character would invalidate the link and thus make it not produce a link. Since our implementation does not check for this, it produces an incorrect output. 

---
## Conclusion
---
This lab report should highlight some of the differences between my group's `getLinks()` implementation when comapred to the provided `markdown-parse` implementation. This report should also highlight how finding external tests from the internet can help shed some light as to what is and what isn't working on your project. 