# Complete Guide For Using XPath In Selenium With Examples
https://www.lambdatest.com/blog/complete-guide-for-using-xpath-in-selenium-with-examples/

### **What is XPath?**
"XML Path" is a syntax for navigating HTML and XML documents to locate elements using the HTML DOM structure
	- In the context of HTML, this is for locating webpage elements 
	- XPath can be used to locate any element on a page based on:
		- tag name
		- ID
		- CSS class
		- and more..

### **Simple XPath Example**
```//tagname[@Attribute='Value']```
1.  **//**: denotes the current node
2.  **tagname**: denotes the tagname of the current node
3.  **@**: is the Select attribute
4.  **Attribute**: denotes the attribute of the node
5.  **Value**: denotes the value of the chosen attribute


### **Absolute vs. Relative XPath**

Example Site: https://accounts.lambdatest.com/register/

<u>Absolute Path</u>
This is the most basic form of XPath and uses the entire absolute path to locate an element within the HTML DOM
	- You have to include every single tag thats nested in order to get to the desired element
	- This makes it very sensitive to changes on the site because your path will break if they change that nested format at any point in time
		- This is why relative XPath is typically preferred

**Example**
```/html//div/div/div/div[1]/div/a/img```

This XPath will locate the GitHub logo within the 'Sign up with Github' button

<u>Relative Path</u>
Instead of using a single /, we can use a // to indicate that we want to use relative XPath
	- This begins the search from the middle of the DOM

**Example**
```//img[@src='/icons/github.svg']```

The above line locates the same element as before, but does not rely on the absolute path and is therefore much more flexible


### **XPath using Contains**
Contains() is a very useful method in XPath
	- It can be used for all elements whose value can change dynamically

**Syntax**
```//tagname[contains(@attribute, constantvalue)]```

**Example**
```//button[contains(@type,'submit')]```

The above example will locate the 'Free Sign Up' button from the example site

### **XPath using Logical Operators: OR & AND**

**Syntax**
```//tagname[@attribute1=value1 OR @attribute2=value1]```
```//tagname[@attribute1=value1 AND @attribute2=value1]```



### **XPath using Text()**
The text() method is used in XPath whenever we want to locate an element using text defined within an HTML tag
	- This is mostly useful if the HTML structure changes dynamically, but the text does not 

**Syntax**
```//tagname[text()=’Text of the Web Element’]```
