# Lab Report 5
Elaine Chao

A16894921

## Test One
I found the two different files by running vimdiff on the results.txt generated for both implementations by a bash script.

Link to test file: [https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md)

Neither implementation is correct.

My implentation output:

![image](https://user-images.githubusercontent.com/34292064/172263713-d7eb8476-5b45-4350-a040-269a2fb9141d.png)

Given implementation output:

![image](https://user-images.githubusercontent.com/34292064/172265242-5a45edc9-82c6-4495-a681-34b05dd7beb3.png)

Expected output: \[Foo*bar\]\]

Expected output according to VSCode Preview:

![image](https://user-images.githubusercontent.com/34292064/172263542-6879c327-59f3-469c-9773-377decd19123.png)

To fix this bug, I would need to add a whole new if statement to the code in order for check for links in the \[link\]\]: format. To accomplish this I would add another variable "secondclosedBracket" after this line of code

![image](https://user-images.githubusercontent.com/34292064/172264385-c7de52a4-8a04-416b-b2c1-9c242e28fccc.png)

Then I would add an if statement to check if there are double brackets and if so, take the text between the brackets as the link instead of the text between the parenthesis.

## Test Two
Link to test file: [https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/342.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/342.md)

Neither implementation is correct.

My implementation results in an infinite loop:

![image](https://user-images.githubusercontent.com/34292064/172264984-1fc71c71-ec94-4f21-9a55-5c856e54254e.png)

Given implementation output:

![image](https://user-images.githubusercontent.com/34292064/172265636-d10d36dc-7f6c-490c-a5fe-62719eedcf36.png)

Expected output (no link): \[\]

VSCode Preview:

![image](https://user-images.githubusercontent.com/34292064/172265531-45381a14-959b-49bb-9b84-48585f82efce.png)

The current issue with the given implementation is that it does not check for backticks.

![image](https://user-images.githubusercontent.com/34292064/172266466-8998f2db-5d4f-47b6-8260-2e5c93690bc4.png)

So before the highlighted line above, I would add two variables to store the position of the backticks. Then I would check if there are two backticks on the same line, and if there were, I would not check for brackets or parentheses between them. Then, those would be considered escaped and the only two brackets and parentheses that would be considered in the test case would be the open bracket and close parenthesis. That should then give the correct output considering the logic of the rest of the program.
