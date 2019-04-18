---
redirect_from:
  - "/prerequisites/pre"
interact_link: content/Prerequisites/pre.ipynb
kernel_name: python3
has_widgets: false
title: 'Prerequisites'
prev_page:
  url: /Overview/Overview
  title: 'Overview'
next_page:
  url: /Process/process
  title: 'Process'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Markdown Cells

You can document the computational process in a literate way, alternating descriptive text with code, using rich text. In IPython this is accomplished by marking up text with the Markdown language. The corresponding cells are called Markdown cells. The Markdown language provides a simple way to perform this text markup, that is, to specify which parts of the text should be emphasized (italics), bold, form lists, etc.

Markdown cells that can contain text, images and equations.  They are written using a combination of Github flavored markdown, HTML, and Latex (a subset for math supported by [MathJax](https://www.mathjax.org).

[Markdown](http://daringfireball.net/projects/markdown) is a popular markup language that is a superset of HTML. Github has implemented an extended version which is supported by the Jupyter notebook.

When a Markdown cell is executed, the Markdown code is converted into the corresponding formatted rich text. 

## Markdown Basics

In [Modal Editor](basics.ipynb#Modal-Editor), you should have learned how to get into and out of edit mode. Briefly, double-click on a cell to enter edit mode. Click on the "Run Cell" button, or hit <kbd>ctrl+enter</kbd> or <kbd>shift+enter</kbd> to render the cell.
 
To keep this simple, I will only show the rendered output.  To see the markdown source that created the cell, double-click on it to enter edit mode.

### Creating a Markdown Cell

You can click on your document where you want to create a new cell, then either:

* Click on the menubar button for "insert cell below" (looks like a plus sign) and then on the menubar change the pulldown menu from "Code" to "Markdown".

or 

* From command mode, hit <kbd>a</kbd>, to insert cell above or <kbd>b</kbd> to insert cell below.  Then hit <kbd>m</kbd> to change it to a markdown cell and <kbd>enter</kbd> to enter edit mode.


## Headers

You should use markdown headers to organize your documents. They will appear larger and bolder than other text and can be referenced by hyperlinks.

# Chapter 1
##  1.1
###  1.1.1
###  1.1.2
#### 1.1.1.1
##### 1.1.1.1.1

Less-commonly these formats are used:

Alt-H1
======

Alt-H2
------

### Emphasis

*italics* _italics_

**bold** __bold__

**_both_** _**both**_

~~Strikethrough~~

## Lists

Build unordered lists using *, +, or -

* One
- Sublist
    - This
  - Sublist
    + That
    + The other thing
* Two
  - Sublist
* Three
  - Sublist

Build ordered lists using numbers.  Any number will do.

1. Here we go
    1. Sublist
    1. Sublist
        1. Subsublist
1. There we go
1. Now this

## Blockquotes
Put '>' at the start of quoted lines. You can use markdown syntax in the quote.  You do not need to put in line feeds. 
> Beautiful is better than ugly.
> Explicit is better than implicit.
> Simple is better than complex.
> Complex is better than complicated.
> Flat is better than nested.
> Sparse is better than dense.
> Readability counts.

And
> Special cases **aren't** special enough to break the rules. Although practicality beats purity. Errors should never pass silently. Unless explicitly silenced.

You can also nest them:
> Level 1
>> Level 2
>>> level 3

## Code
To include inline code snippets, you enclose the code in backticks and include
the language name for syntax highlighting.

No syntax highlighting:
```
def f(x):
    """Returns the square of x."""
    return x**2
```

Python Highlighting:
```python
def f(x):
    """Returns the square of x."""
    return x**2
```
or C
```c
if (i=0; i<n; i++) {
    printf("hello %d\n", i);
    x += 4;
}
```

## Horizontal Rules

---

## Tables

Tables can be created by adding vertical bars between each cell, and by adding a line of dashes (also separated by bars) beneath the header. 

|Item Number|Description|Cost|
|-|-|-|
|1234|Mouse Pad|\$9.99|
|001238|Monitor|\$295.99|
|106|Keyboard|\$55.00|

You can align columns by using colons:

|Item Number|Description|Cost|
|-|:-:|-:|
|1234|Mouse Pad|\$9.99|
|001238|Monitor|\$295.99|
|106|Keyboard|\$55.00|

## Links

Link to another site

[Jupyter's website](http://jupyter.org)

Same link with a tooltip:

[Jupyter's website](http://jupyter.org "Go to jupyter.org")

Link to a header in this document

[Back to Lists](#Lists)

Link to a header in another document

[Modal Editor](basics.ipynb#Modal-Editor)

# Equations

Courtesy of [MathJax](https://www.mathjax.org), you can include mathematical expressions both inline: 
$e^{i\pi} + 1 = 0$  and displayed:

$$e^x=\sum_{i=0}^\infty \frac{1}{i!}x^i$$
Inline expressions can be added by surrounding the latex code with `$`:
```
$e^{i\pi} + 1 = 0$
```

Expressions on their own line are surrounded by `$$`:
```latex
$$e^x=\sum_{i=0}^\infty \frac{1}{i!}x^i$$
```

More examples:

$$\begin{equation*}
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0
\end{vmatrix}  
\end{equation*}$$

When $a \ne 0$, there are two solutions to $(ax^2 + bx + c = 0)$ and they are
$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

You should check the [MathJax](https://www.mathjax.org) site for more details
about how much LaTex is implemented.

$$
Testing
\color{lime}{LIME}black
\mathscr{\color{red}{Red Script}}
$$


$$
\require{mhchem}
\ce{C6H5-CHO}
\ce{$A$ ->[\ce{+H2O}] $B$}
\ce{SO4^2- + Ba^2+ -> BaSO4 v}
$$

$$
\require{enclose}
\enclose{circle}[mathcolor="red"]{x}
\enclose{circle}[mathcolor="red"]{\color{black}{x}}
\enclose{circle,box}{x}
\enclose{circle}{\enclose{box}{x}}
$$

# HTML

You can also mix HTML5 with your markdown.

<s>To strike something out</s>

~~To strike something out~~

You can change font size, family and color using the HTML5 style tag.
<p style="color:red">Hello World</p>
<p style="color:green">Hello World</p>
<h1 style="color:blue;">Blue Header</h1>
<p style="color: orange;
    font-family: courier;
    font-size: 300%;">
Hello World</p>

You can do the same to the ```<HR>``` element.

<hr style="height:10px">
<hr style="height:10px; background-color:red">
<hr style='background-color:#000000;color:#000000;height:2px;width:50%;'>
<hr style="background-color:orange; width:50%; height:5px;" >
<hr style="border-width: 2px;
           border-style: solid;
           border-color: green; 
           width: 50%;
           height: 20px;
           background-color: white;
           ">
<hr style = 'background-color:#000000; border-width:0; color:#000000; height:2px; lineheight:0; display: inline-block; text-align: left; width:50%;' >

# Fonts

<h1 style="color:blue;background:black">This is a Blue Heading on a Black Background</h1>
<p style="color:blue;">This is Blue Text</p>
<p style="color:red;font-size: 200%">This is red text at 200%</p>
<p style="color:orange;font-size:300%;font-family:courier">This is  orange at 300% in courier</p>
<p style="color:green;font-size:300%;font-family:'Times New Roman', Times, serif">This is  green at 300% in Times</p>
<p style="font-family:'Comic Sans MS', cursive, sans-serif;font-size:300%"> Comic Sans (if available)</p>
<p style="font-family:sans-serif;font-size:300%">sans-serif</p>
<p style="font-family:monospace;font-size:300%">monospace 0123</p>

## Bootstrap and CSS

Classic Jupyter includes [Bootstrap](http://getbootstrap.com/), so we can use it there. But if we do, JupyterLab will render our pages differently.
We recommend you use CSS to style your output. You can do this with a code cell as below, or create a function to set the CSS.



{:.input_area}
```python
%%html

<style>
.yellowbg {
    color: #8a6d3b;
    background-color: #fcf8e3;
    border-color: #faebcc;
    padding: 15px;
    border: 1px solid transparent;
    border-radius: 2px;
}
.bluebg {
    color: #31708f;
    background-color: #d9edf7;
    border-color: #bce8f1;
    padding: 15px;
    border: 1px solid transparent;
    border-radius: 2px;
}
</style>
```



<div markdown="0" class="output output_html">

<style>
.yellowbg {
    color: #8a6d3b;
    background-color: #fcf8e3;
    border-color: #faebcc;
    padding: 15px;
    border: 1px solid transparent;
    border-radius: 2px;
}
.bluebg {
    color: #31708f;
    background-color: #d9edf7;
    border-color: #bce8f1;
    padding: 15px;
    border: 1px solid transparent;
    border-radius: 2px;
}
</style>

</div>


<div class="yellowbg">
Brown text on a yellow background with padding
</div>

<p class="bluebg">
Blue text on a lightblue background with padding.  This is just an example of how you can create paragraph styles with CSS.<br><br>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. In egestas fringilla mollis. Nunc nisi lectus, vulputate sed magna non, gravida molestie sem. Nullam quis ante eu dui tincidunt vestibulum. Suspendisse sit amet consequat ante. Curabitur quis sem urna. Aenean eu ex purus. Donec et ex ornare, ultrices massa ut, ultricies sapien. Ut pellentesque arcu eu laoreet semper. Vivamus maximus ullamcorper vulputate. Quisque pharetra lacus non fringilla volutpat. Etiam vitae euismod felis. Nulla at mattis sapien, et faucibus turpis.
</p>


We can use icons from font-awesome

<i class="fa fa-camera" aria-hidden="true"></i>
<i class="fa fa-camera fa-3x" aria-hidden="true"></i>
<i class="fa fa-camera fa-5x" aria-hidden="true"></i>

<i class="fa fa-cog fa-spin fa-3x fa-fw"></i>


## Colors
[Color Names Supported by All Browsers](http://www.w3schools.com/colors/colors_names.asp)
