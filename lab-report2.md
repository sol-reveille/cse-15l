# Lab Report 2
Elaine Chao
A16894921

## Code change 1

![image](https://user-images.githubusercontent.com/34292064/165050001-232f0d61-9397-4779-ba45-b110368f1505.png)

file with failure-inducing input: [test-file.md](https://github.com/sol-reveille/markdown-parser/blob/main/test-file.md)

Symptom of the failure-inducing input:
The symptom was that the program would run in an infinite loop and eventually crash my computer, so there was no error message thrown when running the program with the failure-inducing input in the command line. Adding a print statement into the loop shows the infinite loop occurring as an output in the command line.

![image](https://user-images.githubusercontent.com/34292064/165194583-0469ecbd-d646-4ef1-b277-83d5132099a2.png)

The while loop in the code keeps running until the currentIndex variable equals or is greater than the length of the file. The currentIndex variable can only be updated to the the position of the last closed parentheses plus one. Since in test-file.md, the closed parenthesis is not the last character in the file, currentIndex is always less than the length of the file and so the while loop runs infinitely.

## Code change 2

![image](https://user-images.githubusercontent.com/34292064/165195693-ed59d0b6-05e4-4f30-b081-0ddf4c67141d.png)

file with failure-inducing input: [test-file3.md](https://github.com/sol-reveille/markdown-parser/blob/main/test-file3.md)

Symptom of the failure-inducing input:

![image](https://user-images.githubusercontent.com/34292064/165194121-b1091128-3dd7-4719-8b74-ae0a2af1d74d.png)

The bug was that since there are no parentheses in test-file3, the variables openParen and closeParen both had values of -1. This meant that in the next line we were trying to find the substring of markdown from 0 to -1, which is impossible, hence the symptom of having the error thrown.

## Code change 3

![image](https://user-images.githubusercontent.com/34292064/165196562-714c75f9-35a2-4e51-a9b8-e17ef7bb0ff1.png)

file with failure-inducing input: [test-file4.md](https://github.com/sol-reveille/markdown-parser/blob/main/test-file4.md)

Symptom of the failure-inducing input:

We want it to output [link goes here] but instead it outputs an empty list instead.

![image](https://user-images.githubusercontent.com/34292064/165195906-2a4f5ecd-867c-4fa7-98ce-9ae3b543d985.png)

The bug here is that the program would only output any line of text between two parentheses, so since the link in test-file4.md is not enclosed in parentheses, it does not get returned and so we are left with an empty list instead. This is fixed by writing a line that recognizes the space between the closing bracket and the exclamation point as a link as well.
