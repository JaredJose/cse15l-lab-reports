# Lab Report 2 - Week 4
**Objective:** This report will focus on the debugging process that the Fiddler Crabs used to work through bugs in the markdown-parse project. 

## Bug 1: 
Image of code difference: ![Image](/images/report2/codeDiff1.png)

Link to failure inducing test file: [Click me!](https://github.com/JaredJose/markdown-parse/blob/main/new-test.md)

Symptom: ![Image](/images/report2/symptom1.png)

The symptom that results from this failure-inducing input is an infinite loop which eventually results in an OutOfMemoryError. The bug which causes this has to do with how currentIndex is adjusted inside of the while loop. At the moment of this bug, if the last string of characters in the file was not an image or link, then currentIndex would never become larger than the length of the markdown file and thus the loop would continue indefinitely. By checking if an opening bracket was found, we were able to subvert this and drop out of the loop if there was no indicator of another image/link in the remainder of the file. 

## Bug 2:
Image of code difference: ![Image](/images/report2/codeDiff2.png)

Link to failure inducing test file: [Click me!](https://github.com/JaredJose/markdown-parse/blob/main/test-file3.md)

Symptom: ![Image](/images/report2/symptom2.png)

Although this failure inducing input did not produce an incorrect output, the way that the code is functioning is still inherently incorrect. Based off of the input the first "click me!" in the brackets is not indicative of a link. However, the getLinks() method treats it as a flag that the next following parenthesees will contain a link. In this file, the next following parenthesees is a link, thus creating an appropriate output. To address this problem, our group determined that a key feature of a real Image or Link is that there must be an close bracket directly followed by an open parenthesees (`](`) for a link/image to exist. Therefore, our fix to address this bug is to check for those consective sets of characters. 

## Bug 3:
Image of code difference: ![Image](/images/report2/codeDiff3.png)

Link to failure inducing test file: [Click me!](https://github.com/JaredJose/markdown-parse/blob/main/test-file4.md)

Symptom: ![Image](/images/report2/symptom3.png)

In this case, the fix that the group implemented to address Bug 2 caused this new bug which manifested itself as getting stuck in an infinite loop. As a result of continuing whenever there was not a consecutive sequence of `](`, the program would never be able to reach the check for if an open bracket existed. Thus, the program was showing the same symptoms as in Bug 1. Thus, the solution to addressing this problem was to move the check for an opening bracket before the check for the consecutive `](`. Since the program new it was a not a link, it was continuing before adding contents into the toReturn ArrayList. However, its continues were actually contributing to the problem. 