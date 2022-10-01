In the following pages, I have described my step by step process in following through with Lab 1. For context, I have a Lenovo ThinkPad that uses Windows

**Step 1: Download VS Code**
I previously had Visual Studio Code downloaded for CSE 11. However, in the following pictures I describe where I had downloaded it from as well as the first slide that shows up when I open VS code. The picture below shows the website I downloaded VS Code from. 
![](pictures%20for%20lab%20report%202/2022-09-30%20(2).png)


This below is the visual when you open VS Code (there is perhaps a little bit of a different picture when you open it up for the first time, however, once you have created a new file from the top right corner the picture below is how your screen should look. 
![](pictures%20for%20lab%20report%202/2022-09-28%20(2).png)

**Step 2: Connect Remotely**  
In this I opened up VS Code and typed in: “ssh cs15lfa22qs@ieng6.ucsd.edu”; after this input it asked for my password. I had tried to change the password without changing my TritonLink password, however, that did not work (even after waiting for an hour); therefore, I changed my entire password and tried to log in again—which was successful. Below, I have included the screenshots of me signing in.
![](pictures%20for%20lab%20report%202/2022-09-30.png)

![](pictures%20for%20lab%20report%202/2022-09-30%20(1).png)

**Step 3: Try some commands**  
In the following screenshot I have tried a few commands including, ls, which lists the contents in a directory. Furthermore, I tried ls -a which also lists the hidden files. I also tried lac which shows and orders all the hidden files in a directory.
![](pictures%20for%20lab%20report%202/2022-09-30%20(3).png)

**Step 4: Moving Files with scp**

Here I first made the new file called WhereAmI from the file button in the top right corner. 
![](pictures%20for%20lab%20report%202/2022-09-30%20(4).png)
Next I added in the code that is written on the course webpage and compiled and ran the commands, I see the name of the operating system, the name of the user on my laptop, the path to my home and the directory I am in 
![](pictures%20for%20lab%20report%202/2022-09-30%20(5).png)

Below I have copied the file by running scp. Further, I used the ls command so we can see it in the ssh
![](pictures%20for%20lab%20report%202/2022-09-30%20(6).png)

I ran the java program again
![](pictures%20for%20lab%20report%202/2022-09-30%20(8).png)

**Step 6: Setting an SSH Key**

In the following picture I generated the randomart image and made a file in both the server and my computer
![](pictures%20for%20lab%20report%202/2022-09-30%20(9).png)

In the picture below you can see me testing using ssh and scp to copy the whereamI file once more; in this case I was able to do it without entering my password.
![](pictures%20for%20lab%20report%202/2022-09-30%20(10).png)

**Step 7: Optimizing Remote Running**

Below I have tried to run the ls and ls-lac commands on the remote server without having to log in (Staying in my computer just by putting quotes around them. 
![](pictures%20for%20lab%20report%202/2022-09-30%20(11).png)

Below is a screenshot of me running commands on the same line just separated by colons (something that greatly increases proficiency). 
![](pictures%20for%20lab%20report%202/2022-09-30%20(13).png)

Thank you for going through my blog!






