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

<div style = "padding: 1em;">
</div>

Here, I used the command:

```
scp -r . cs15lwi22agd@ieng6.ucsd.edu:~/markdown-parse
```
which copied recursively all of my files of markdown-parse into a directory called markdown-parse on ieng6 (which had to be created, since it did not exist before). 


<div style = "padding: 1em;">
</div>

### **Compiling and Running MarkdownParse in ieng6**

<div style = "padding: 1em;">
</div>

Next, I logged into my ieng6, using `ssh`. 

<div style = "padding: 1em;">
</div>

![RunningMarkdownParseTest](Lab3Screenshots\RunningMarkdownParseTest.png)
<div style = "padding: 1em;">
</div>

When inputting the command `ls`, we see that there is a new directory called markdown-parse. I used the `make` command to run and compile the MarkdownParse files to test in which all test passed. 

<div style = "padding: 1em;">
</div>

### **Optimizing Running in One Line**

<div style = "padding: 1em;">
</div>

![OptimizingRunning](Lab3Screenshots\OptimizingRunningMarkdownParseTest.png)

Here using the command:
```
scp -r *.java *.md *.sh lib/ cs15lwi22agd@ieng6.ucsd.edu:markdown-parse;ssh cs15lwi22agd@ieng6.ucsd.edu "cd markdown-parse; bash run.sh"
```

I was able to copy over only the `.java`, `.md`, and `.sh` files into ieng6 in one line. In the same line, I was then able to ssh into my account and `cd` into the markdown-parse directory to `bash run.sh`.

<div style = "padding: 1em;">
</div>

![run-sh](Lab3Screenshots\run-sh.png)

<div style = "padding: 1em;">
</div>

There was some problems with just using `javac` and `java`, so I created this run.sh script with the commands: 
```
/software/CSE/oracle-java-se-14/jdk-14.0.2/bin/javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java MarkdownParse.java

/software/CSE/oracle-java-se-14/jdk-14.0.2/bin/java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
```

This enabled me to copy my MarkdownParse files to ieng6, compile, and run them all in one line. 