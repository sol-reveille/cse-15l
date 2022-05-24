# Lab Report 4

[My markdown-parser implementation](https://github.com/sol-reveille/markdown-parser)

[Reviewed markdown-parser implementation](https://github.com/BellaReal/markdown-parser)

## Snippet 1

According to the VSCode Markdown Preview, the last three links all work.

![image](https://user-images.githubusercontent.com/34292064/169922050-48db8ab9-bae8-4298-876c-cee8b9efbefc.png)

Therefore, the program should return a list of [\`google.com, google.com, ucsd.edu]

I wrote this test for snippet 1:

```
@Test
    public void testSnippet1() throws IOException{
        Path fileName = Path.of("snippet1.md");
        String content = Files.readString(fileName);
        assertEquals(List.of("`google.com", "google.com", "ucsd.edu"),
            MarkdownParse.getLinks(content));
    }
```

Test result for the reviewed implementation:
![image](https://user-images.githubusercontent.com/34292064/169922542-8f7416f1-2ac2-4c30-bf9b-33dea5cd0fc7.png)

## Snippet 2

The VSCode preview of the markdown file looks like:
![image](https://user-images.githubusercontent.com/34292064/169923500-2e154c57-e964-40aa-854a-e1abac24123e.png)

So the program returns the links ["a.com", "a.com(())", "example.com"]

The snippet 2 test I used is:
```
@Test
    public void testSnippet2() throws IOException{
        Path fileName = Path.of("snippet2.md");
        String content = Files.readString(fileName);
        assertEquals(List.of("a.com", "a.com(())", "example.com"),
            MarkdownParse.getLinks(content));
    }
```

Test result for the reviewed implementation:
![image](https://user-images.githubusercontent.com/34292064/169923426-9227b444-196b-43e0-8e74-227327e3e663.png)

## Snippet 3

These are the links that should work:
![image](https://user-images.githubusercontent.com/34292064/169923293-f902505e-92fe-44fa-bbce-4be871066fd0.png)

Snippet 3 test:
```
@Test
    public void testSnippet3() throws IOException {
        Path fileName = Path.of("snippet3.md");
        String content = Files.readString(fileName);
        assertEquals(List.of( "https://twitter.com",
    "https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule", "https://cse.ucsd.edu/"),
        MarkdownParse.getLinks(content));
    }
```

Test result for reviewed implementation:

![image](https://user-images.githubusercontent.com/34292064/169923360-1bbec75f-5809-42f4-a672-dd5ad1956266.png)
