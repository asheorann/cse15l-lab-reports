# LAB REPORT 4 #

In this lab report I will be demonstrating the task that requires us to change the main method so that rather than hardcoding the search on the ./technical directory, it uses the second command-line argument for the path to search

The following way of using vim to complete the task above utilizes 22 keys in total.

## PART 1: Step-by-Step Guide ##

**Following is the summary of the steps***

```

/Shift g/3k/9w/l/15x/args[1]/<esc>/:wq/<enter>

```

**Step 1:**
By pressing 'Shift g', we reached the bottom of the page regardless of where we started on the page
![Alt text](picture%20for%20lab%204/shiftG.png)


**Step 2:**
In this, we moved up three lines on the page
![Alt text](picture%20for%20lab%204/3k.png)


**Step 3:**
Here, we moved 9 words down (to the right)
![Alt text](picture%20for%20lab%204/9w.png)


**Step 4:**
By pressing l, we moved to the right by one
![Alt text](picture%20for%20lab%204/l.png)


**Step 5:**
By typing 15x, we removed 15 characters, essentially both quotes and the ./technical were removed
![Alt text](picture%20for%20lab%204/15x.png)


**Step 6:**
By typing 'i' we entered insert mode, so that we could insert the text described in the following step
![Alt text](picture%20for%20lab%204/i.png)


**Step 7:**
Here, we just inserted the desired text which was args[1]
![Alt text](picture%20for%20lab%204/args%5B1%5D.png)


**Step 8:**
Since we were still in insert mode, we pressed escape to go back into normal mode, we then did :wq which means save and exit and clicked the enter to put these chanages (saving and exiting) into effect
![Alt text](picture%20for%20lab%204/escape%20wq%20enter.png)


## Part 2: SSH vs SCP 

I think overall, I would prefer the method of ssh in the remote server, editing on vim, and running the bash file there. In terms of the actual typing both methods took my around 1 minute and 15 seconds, however, with the scp method it took me a bit longer as I was struggling to type the scp command. However, even if I assume that the scp was pastable, I think it overall was a more convenient process to edit and then run in the same place, i.e. use vim remotely and then run it remotely. As we had already discused the steps in order to complete the changes in lab, I did not feel as though there was a big difference between the two approaches. 

However, some factors that may contribute to me generally choosingto just use vs code and then copy over vs. use vim could be the following. First, what is the nature of the file if there are multiple differnt files I am continually looking between to understand code etc. I think using vs code and copying over would be a lot easier. On the other hand, if I solely need to play inside one file than vim would be better. Further, the larger the file is the better it would be just to edit it and run in on the same location (i.e. the vim option) as copying larger files requires more time and effort from the computer. While I do not have too much experience and therefore speed with working with vim, I do find that it is likely the faster method more most situations. 