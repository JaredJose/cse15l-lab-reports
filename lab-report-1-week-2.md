# Lab Report 1 - Week 2
**Objective:** This report will describe the overall process of logging into a course-specific account on `ieng6`. 
## Step 1: **Installing VSCode**:

In this course, we utilize the terminal found inside VSCode to accomplish this. The installation link for VSCode can be found here: [Link](https://code.visualstudio.com/#alt-downloads). There are working versions for Mac, Windows, and Linux. In order to install the IDE, download the appropriate installer and follow the instructions of the setup wizard. 
![Image](/images/report1/VSCodeInstall.png)
## Step 2: **Remotely Connecting**:

In order to log into an account on `ieng6`, your computer must have a way to "talk" to the server. This is where the VSCode terminal comes into play. By using `ssh` or *Secure Shell Protocol*, we are able to establish a connection between our client and the `ieng6` server. To connect to `ieng6` open the terminal and enter `ssh cs15lwi22zz@ieng6.ucsd.edu`. In your case, replace the `zz` wtih your assigned letters. The following image shows what a successful connection looks like. 
![Image](/images/report1/Connecting.png)
*As you can see, the text where the cursor is has changed from my laptop to the server*
## Step 3: **Trying Some Commands**: 

There are some basic commands that you may find useful to try such as ...
1. `cd` = select directory
2. `ls` = lists files in current directory
3. `pwd` = print working directory
4. `mkdir` = make file (directory)
5. `cat` = allows you to print contents of a file

![Image](/images/report1/Commands.png)
## Step 4: **Moving Files with** `scp`:

The `scp` command is used to copy files from a client to a server. Therefore, if you are trying to send a file to a server, the command should be run on your **client** terminal and **not** on the server. The synta for using `scp` is `scp <file name> <server:directory>`. In the case of copying a file to the home directory of `ieng6`, the syntax looks like `scp <file name> <cs15lwi22xx@ieng6.ucsd.edu:~/>`. 
![Image](/images/report1/scpExample.png)
## Step 5: **Setting an SSH Key**:

One of the most time consuming parts of interacting with the server is having to re-enter your password each time you send a command involving your account on `ieng6`. As you might have noticed in my previous screenshots, I was not prompted to enter a password. This is because I have setup a pair of SSH Keys, with one on my client and one on the server which work in lieu of a password. To accomplish this, you use `ssh-keygen` on your client to generate the public and private keys. Then you use scp to copy the public key over to the server. 
![Image](/images/report1/sshKey.png)

## Step 6: **Optimizing Remote Running**

The number one tip for helping to increase effeciency when interacting with the remote server is to queue up commands and then use the arrow keys to repeat them when necessary. Especially if you are not a skileld typist, using the arrow keys really does help to make repeating commands a less arduous process. The other tip that we found useful was queueuing up commands on an `ssh` by using `ssh cs15lwi22xx@ieng6.ucsd.edu "command1; command2;"`. This allows you to run commands on the server in the same step as connecting. This also made a significant increase in terms of effeciently connecting to the server. 
In my testing I was able to get a common task, like pushing a file to the server, then executing said file on the server down to 5 keystrokes: 
1. **Up Arrow** to retrieve `scp` command
2. **Enter** to execute the `scp`
3. **Up Arrow** x2 to retrieve `ssh` command. Here I would utilize the ability to queue up multiple commands to be ran on the server directly after `ssh`ing in.
4. **Enter** to execute the `ssh` line. 
![Image](/images/report1/optimization.png)

## **Conclusion**
I hope that this guide gave a good introduction and some helpful tidbits about connecting to and interacting with a remote server. Although this is not comprehensive and is very much the tip of the iceberg, it should serve as a good place to start your commandline journey. 
