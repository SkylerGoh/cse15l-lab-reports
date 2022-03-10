<h1 align="center">
Week 10 Lab Report 5
</h1>
<h3 align= "center"> 

Markdown Comparison

</h3>

<div style = "padding: 1em;">
</div>

## **Two Differences Between Implementations**

<div style = "padding: 1em;">
</div>

## **How:**

<div style = "padding: 1em;">
</div>

For both cases shown below, I found these by running this script.sh file:

```

for file in test-files/*.md;
do
  echo $file
  java MarkdownParse $file
done

```

on both implementation in two separate Visual Studio Code editors. I then compared the results of both to see which test files differed in output. 

<div style = "padding: 1em;">
</div>

### **Case 1: test-files\32.md**

<div style = "padding: 1em;">
</div>

Output for my implementation: 

![MyTest32](Lab5Screenshots\MyTest32.png)

Output for given implementation: 

![OtherTest32](Lab5Screenshots\OtherTest32.png)

Test File 32:

![test32](Lab5Screenshots\Test32.png)

Expected Output:

![ExpectedTest32](Lab5Screenshots\ExpectedTest32.png)

According to VSC preview, Test 32 has a proper link. However I believe, this link is only the first part of the link that is underlined in white. Therefore, neither of the implementations were correct in this case.

<div style = "padding: 1em;">
</div>

### **Problem with Given Implementation for test file 32**

<div style = "padding: 1em;">
</div>

![GivenProblem32](Lab5Screenshots\GivenProblem32.png)

Here in the given implementation, the code is selectively discarding links that have spaces between them. However, in `test-file\32.md` the link contains a space and some text. This is causing the code to skip adding this link into toReturn which causes the program to give no output for this specific test case.

<div style = "padding: 1em;">
</div>

### **Case 2: test-files\510.md**

<div style = "padding: 1em;">
</div>

Output for my implementation: 

![MyTest32](Lab5Screenshots\MyTest510.png)

Output for given implementation: 

![OtherTest32](Lab5Screenshots\OtherTest510.png)

Test File 510:

![test32](Lab5Screenshots\Test510.png)

Expected Output:

![ExpectedTest32](Lab5Screenshots\ExpectedTest510.png)

According to VSC preview, `test-file\510.md` does not have a link since there is a space between the close bracket and open parentheses of the link. In this case, my implementation of markdown-parse outputed correctly while the given implementation did not and took `/url` as a link. 

<div style = "padding: 1em;">
</div>

### **Problem with Given Implementation for test file 510**

<div style = "padding: 1em;">
</div>

In this case, there is not a specific line of code causing the problem in the given implementation; but rather, there is a lack of code to catch the problem. The given implementation fails to check if there is any spaces or things inbetween the closed bracket and open parentheses, and therefore still outputting the non-link. 