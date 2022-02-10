<h1 align="center">
Week 6 Lab Report 3
</h1>
<h3 align= "center"> 

Copying whole directories with `scp -r` 

</h3>

<div style = "padding: 1em;">
</div>

### **Copying MarkdownParse directory to ieng6**

<div style = "padding: 1em;">
</div>

![Copying MarkdownParse pt1](Lab3Screenshots\Scp-r-pt1.png)

![Copying MarkdownParse pt2](Lab3Screenshots\Scp-r-pt2.png)

![Copying MarkdownParse pt3](Lab3Screenshots\Scp-r-pt3.png)

Here, I used the command:

```
scp -r . cs15lwi22agd@ieng6.ucsd.edu:~/markdown-parse
```
which copied recursively all of my files of markdown-parse into a directory called markdown-parse on ieng6 (which had to be created). 

