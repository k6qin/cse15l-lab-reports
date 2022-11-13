# **Week 7 Lab Report**
> *By Ken Qin*
---
* Part 1: Vim Commands

We want to change the name of the `start` parameter and its uses to `base`, here is how we do it in Vim.

First, we need to change our directory and run the file on Vim using these commands:       
`cd week6-skill-demo1<Enter>`
`vim DocSearchServer.java<Enter>`
Then, we can perform the following Vim commands to change the name:
`/start<Enter>cebase<Esc>n.n.n.:w<Enter>`
![image](sc1-week7.png)
This screenshot shows the results of performing `/start<Enter>` in Vim, which moves cursor to `start`.
![image](sc2-week7.png)
This screenshot shows the results of `ce`, which switches to input mode and delete the word `start`.
![image](sc3-week7.png)
This screenshot shows typing `base<Esc>`, replacing the text and returning to insert mode.
![image](sc4-week7.png)
![image](sc5-week7.png)
![image](sc6-week7.png)
These screenshots show using `n.` to change each occurence of `start` to `base`, which repeats for last search from cursor and uses `.` to perform previous command of replacing word.
![image](sc7-week7.png)
![image](sc8-week7.png)
Lastly, these two screenshots display the results of using `:w<Enter>` to save the changes to the file.

---
**Special Note**: Alternatively, an easy way to find and replace in the entire file using Vim is the following command: 
`:%s/start/base<Enter>:w<Enter>`, where `%s` is the range representing the entire file, `start` is the pattern we want to replace, and `base` is the string we want to replace with.
![image](sc9-week7.png)
![image](sc10-week7.png)
Above shows this alternative way of find and replace all, with this useful Vim command not covered in lectures.

---
* Part 2: Workflow Strategies

-On VSCode: 93 seconds, have to go through each line in the file to change the string, `scp` to remote, sign in to remote, and test the file there, takes much more time.

-On Vim: 35 seconds, using Vim shortcuts made changing the string faster, and since I am already in remote, I just have to run `bash test.sh` after made changes in Vim, which results in less time taken.

-Which of these two styles would you prefer using if you had to work on a program that you were running remotely, and why? What about the project or task might factor into your decision one way or another? (If nothing would affect your decision, say so and why!)

I would prefer to work in Vim if the program is running remotely, as it is much more efficient and time-saving, given that I am familiar with the Vim commands. However, if the project is more time-consuming, and does not require tasks that would be performed faster in Vim (multiple edit task), I would probably work with the first style, since time is not a concern and I am more familiar with that traditional style. Though, this decision is subject to change once I get more familiar with Vim.
