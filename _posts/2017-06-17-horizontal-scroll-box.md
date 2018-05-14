---
layout: post
title:  "Horizontal scroll box"
date:   2017-06-17 10:07:39 -0700
category: Web_Designing
img: /static/IMG/3.jpg
color: green
tags: 
- HTML
- CSS
---
## Horizontal Scroll box for blogger
If you are a Blogger, you have to create horizontal scrolling boxes for showing your codes. It is not easy to setup [SyntaxHighlighter](http://alexgorbatchev.com/SyntaxHighlighter/) or [Prism](http://prismjs.com) for Blogger and WordPress. However you can create beautiful horizontal scroll boxes for codes. In this post I will show you how it becomes possible. Go to your blogger control panel and create a new post. Before copying this code make sure that you are using HTML editor mode. Whenever you want a code snippet you can use following code.
```markdown
<style>
.divScroll{ 
            white-space: nowrap; 
            overflow-x: scroll;
            font-size:14px;
            height:auto;
            width:auto;
            background-color:#bdbdbd;
        }
</style>
<div class="divScroll">
"Your Code"
</div>
```
If you have any trouble with `<` and `>` use instead `&lt;` and `&gt;` respectively.You can change background color to any light color. This code can be used for making horizontal scrolling table, text area etc. Unfortunately this code never works with HTML editor of your WordPress. Since wordpress never allow you to edit CSS for a specific post. Inorder to make horizontal text area on a WordPress blog you can use following code.
```markdown
<div style="border: 1px solid black; overflow-x: auto; white-space: nowrap; height: auto; width: auto; color: black; background-color: white;">
INSERT TEXT HERE
</div>
```
