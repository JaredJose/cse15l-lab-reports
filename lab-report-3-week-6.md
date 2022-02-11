# Lab Report 3 - Week 6
**Objective:** This report will focus on detailing the set-up and benefits of streamlining one's ssh Configuration

## `config` file
File Contents: ![Image](/images/report3/nano.png)

This `config` file is relatively short and contains just a few fields. These fields correspond to the items before and after the "@" in cse15lwi22xxx@ieng6.ucsd.edu. The file also contains the alias that you will use in lieu of the entire line. In order to create this config file I used nano (which is a linux command line text editor). The image above shows the contents of the file in the nano editor. 

## Logging in!
`ssh`ing in: ![Image](/images/report3/ssh_alias.png)

As you can see at the top of the image, I was able to log in to `ieng6` without having to type out the entire cse15lwixxx@ieng6.ucsd.edu . Due to having also created an ssh-key pair, this creates an extremely streamlined process which is significantly faster than the process we used Week 1. An additional note is that the alias "ieng6" can be whatever one wants. 

## `scp` Using Alias
Before: ![Image](/images/report3/before-alias-scp.png)

After: ![Image](/images/report3/after-alias-scp.png)

As a direct result of setting up this alias, the command to scp a file to ieng6 was shortened from `scp file cse15lwi22xxx@ieng6.ucsd.edu:~/` to just `scp file ieng6:~/`. This is much shorter and makes copying files a much more streamlined process. This also shows that the alias you chose for your configuration can be used in lieu of `cse15lwi22xxx@ieng6.ucsd.edu` in any case where it would previously be needed. 

---

Conclusion: Utilziing the config file to create an alias for the relatively long user@host string makes it significantly easier to interact with the server. The set-up is also relatively painless and can be completed extremely quickly. 