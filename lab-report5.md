# Lab Report 5
Elaine Chao
A16894921

## Test One
Link to test file: [https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md)

Neither implementation is correct.

My implentation output:

![image](https://user-images.githubusercontent.com/34292064/172263713-d7eb8476-5b45-4350-a040-269a2fb9141d.png)

Expected output: \[Foo*bar\]\]

Expected output according to VSCode Preview:

![image](https://user-images.githubusercontent.com/34292064/172263542-6879c327-59f3-469c-9773-377decd19123.png)

To fix this bug, I would need to add a whole new if statement to the code in order for check for links in the \[link\]\]: format. To accomplish this I would add another variable "secondclosedBracket" after this line of code

![image](https://user-images.githubusercontent.com/34292064/172264385-c7de52a4-8a04-416b-b2c1-9c242e28fccc.png)

It would check if there are double brackets and if so, take the text between the brackets as the link instead of the text between the parenthesis.

## Test Two
