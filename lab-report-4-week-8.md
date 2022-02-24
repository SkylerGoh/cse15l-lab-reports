<h1 align="center">
Week 8 Lab Report 4
</h1>
<h3 align= "center"> 

Markdown Snipppets

</h3>

<div style = "padding: 1em;">
</div>

### **Links for Markdown Parse**

<div style = "padding: 1em;">
</div>

[Link to personal implementation of MarkdownParse](https://github.com/SkylerGoh/markdown-parse-group.git)

<div style = "padding: 1em;">
</div>

[Link to reviewed implementation of MarkdownParse](https://github.com/SkylerGoh/markdown-parse-lab8.git)

<div style = "padding: 1em;">
</div>

### **Expected Output for Snippets**

<div style = "padding: 1em;">
</div>

![Snippet1](Lab4Screenshots\Snippet1.png)

<div style = "padding: 1em;">
</div>

According to the VsCode preview for this snippet, MarkdownParse 
is expected to return:  
```
[`google.com,google.com,ucsd.edu]
```
<div style = "padding: 1em;">
</div>

![Snippet2](Lab4Screenshots\Snippet2.png)

<div style = "padding: 1em;">
</div>

For Snippet 2, MarkdownParse is expected to return:  
```
[a.com,a.com(()),example.com]
```

<div style = "padding: 1em;">
</div>

![Snippet3](Lab4Screenshots\Snippet3.png)

<div style = "padding: 1em;">
</div>

For Snippet3, MarkdownParse is expected to return: 

```
[https://www.twitter.com,https://ucsd-cse15l-w22.github.io/,https://cse.ucsd.edu/]
```

<div style = "padding: 1em;">
</div>

### **Test methods for Snippets**

<div style = "padding: 1em;">
</div>

![SnippetTests](Lab4Screenshots\SnippetTests.png)

<div style = "padding: 1em;">
</div>

The code above shows how I implemented these snippets into test methods. Using jUnit, I simply put the expected output as a list of Strings and called MarkdownParse.getLinks on the snippet.md files for each respective snippet. 

<div style = "padding: 1em;">
</div>

### **My Implementation When Running Tests**

<div style = "padding: 1em;">
</div>

When running these test on my implementation of MarkdownParse. My implementation failed all tests shown below:

![MyImplementation](Lab4Screenshots\MyImplementationOutput.png)

<div style = "padding: 1em;">
</div>

* In the case of my implementation for snippet 1, my MarkdownParse wrongly included url.com into the output. 

* For snippet 2, MarkdownParse only took half of the parentheses of the second link a.com(()) (Ouput was `a.com((` ).

* For snippit 3, MarkdownParse included the spaces when taking the links. 

<div style = "padding: 1em;">
</div>

### **Reviewed Implementation When Running Tests**

<div style = "padding: 1em;">
</div>

![ReviewedImplementation](Lab4Screenshots\ReviewedImplementationOutput.png)

<div style = "padding: 1em;">
</div>

In the reviewed implementation of MarkdownParse, it only failed 2 out of the 3 tests. The one that passed was the test method of snippet 2. 

* For Snippet 1, it also included `url.com` as an output when it should have not.
* For Snippet 3, it had an `java.lang.StringIndexoutOfBoundsException` when running. 

<div style = "padding: 1em;">
</div>

### **Thoughts on Fixing These Errors**

<div style = "padding: 1em;">
</div>

1. I believe there is a less than 10 line solution to checking for inline backticks
for my implementation that would solve the issue with snippet 1 and all other
relavant cases. I would simply keep track of possible backticks through a variable called openbacktick. If I am able to find another backtick on the same line that means I can skip whatever is within those backticks and set currentIndex to the index of the closebacktick. If there is not another backtick, I would continue as normal parsing the file.
2. I believe there is not a less than 10 line solution for nested parenthesis, brackets, or escape brackets in the issue for snippet 2 and all related cases. I would have to possibly write a new method to help me keep track of open parentheses and their closed counterpart. 
3. I believe there is a less than 10 line solution for newlines within brackets and parentheses. When adding the link to the output, I could call `String.trim()` on the link to remove any whitespace or newlines to the output. 





