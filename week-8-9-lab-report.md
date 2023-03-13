# Lab Report 5 - Abel Preciado
## Selected Lab / Report: Lab Week 7 / Report 4, Doing commands quickly
### Background Information
This lab was focused on speeding up the process of working in the terminal. We were given multiple ways to speed up our work flow, mainly through setting up an `ssh` key so that we didn't have to type our password in everytime to login to ieng6, in addition to instruction regarding using `<tab>` and searching through our command history. While at first I was quite slow at completing all the tasks, taking around 5 minutes to complete them all (if I recall correctly), I was able to get it down to under 30 seconds after consulting with my lab members and section tutor regarding some common tricks. With a bash script, I could only assume it would be just as fast if not faster then my previous best time, which I will test later in this report.

### How I got under 15 seconds
To minimize the amount of time spent, I minimized the amount of time spent actually typing commands. After my section tutor informed us of a student in another section who managed to get under 30 seconds through command chaining, I consulted ChatGPT on how that was done in bash. ChatGPT returned with this information:

Image Placeholder :D

With that in mind, I started working on chaining commands together. I knew that using `ssh` to login to the server would have to remain its own command, since if I tried to chain commands after `ssh`, they wouldn't be executed on the remote server and instead would wait until I logged out and returned to my local terminal. Additionally, I wasn't aware of a way to alter text directly in the command line, so I would still have to use `nano` to manually edit the file in step 7, but steps 5-6 and 8-9 I could chain together, reducing the total number of commands ran to just 4 commands, instead of the previous 11 commands. The commands I ran are listed below:
* `ssh cs15lwi23awg@ieng6.ucsd.edu`
* `git clone git@github.com:IgnisHyper/lab7.git; cd lab7; javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java; java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
* `nano ListExamples.java`
* `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java; java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests; git add ListExamples.java; git commit -m "hehe"; git push`
These commands allowed me to reduce my time quite a bit, but I still wasn't satisfied. I returned to ChatGPT and asked it about altering text directly in the command line without having to use `nano` or `vim`. ChatGPT replied with this response:

Image Placeholder D:

The `sed` command was the command that seemed most fitting for my purposes. I proceeded to further ask ChatGPT about how to alter text on a specific line:

Another image placeholder D:

After some experiments with changing lines using `sed`, along with determining the proper line numbers, I came up with the command `sed -i '43s/.*/      index2 += 1;/' ListExamples.java` which successfully altered the buggy line in `ListExamples.java` to a fixed line, meaning I would no longer need to use `nano` to manually fix the bug! With that in mind, I managed to just have to run two commands:
* `ssh cs15lwi23awg@ieng6.ucsd.edu`
* `git clone git@github.com:IgnisHyper/lab7.git; cd lab7; javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java; java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests; sed -i '43s/.*/      index2 += 1;/' ListExamples.java; javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java; java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests; git add ListExamples.java; git commit -m "hehe"; git push`
I'll note that I ran these commands before both on my laptop and on the remote server so that I could easily search for them using the `<ctrl> + r` command search shortcut, bring my time down even more. It may not be the prettiest command in the world, and any other developer who tried to read it may struggle, but it allowed me to get my total time to around 10 seconds (if I recall correctly)!

### Using a `bash` script
Using a bash script would have been helpful for two main reasons:
1. It would be easier to debug
2. It would be easier to read
I would likely not create a `bash` script for running the `ssh` command, since 
