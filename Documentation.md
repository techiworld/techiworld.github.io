---
layout: default
title: Docs
prism: true
---

This is multi-purpose Jekyll template made by Chipprogrammer. I am not a web designer. But I put some awesome effort to make this theme possible since I have some enthusiasm in Webdesigning. This Jekyll theme has some awesome include features. But errors and omissions are allowed. Since I mentioned earlier I am not a **web designer**.
# 1. Regular Markdown features

Here we are using Kramdown for markdown. This jekyll theme is also made inorder to made compatible with kramdown.
## 1.1 Heading
following are the levels of headings:
<pre class="line-numbers">
<code class="language-markdown">
{% raw %}
# Level-1 headings
## Level-2 heading
### Level-3 heading
#### Level-4 heading
##### Level-5 heading
###### Level-6 heading
{% endraw %}
</code>
</pre>

# Level-1 headings
## Level-2 heading
### Level-3 heading
#### Level-4 heading
##### Level-5 heading
###### Level-6 heading

## 1.2 Changing Colors of text

The color of the heading can be changed as you wish as following. As I mentioned earlier we are using **w3.css** we have lot of color options. We will discuss about those color options later. The output of an example is followed by coe is also shown below
<pre class="line-numbers">
<code class="language-markdown">
{% raw %}
<span> your text goes here</span>{: .w3-text-color }
{% endraw %}
</code>
</pre>
The core idea behind the <span>Raspberry Pi</span>{: .w3-text-red } (RPi) project was the development of a 
small and affordable computing platform that could be used to stimulate the 
interest of children in core information and communications technology (ICT) 
education. The rapid evolution of low-cost system on a chip (SoC) devices for 
mobile applications made it possible to widely deliver the affordable RPi plat-
form in early 2012.

# 2. Includes

### 2.1 quotes.html
<pre class="line-numbers">
<code class="language-markdown">
{% raw %}
{% include quotes.html container_color="pale-blue" leftbar_color="blue" icon_color="blue" quote="your quotes goes here" said_by="someone" %}
{% endraw %}
</code>
</pre>
{% include quotes.html container_color="pale-blue" leftbar_color="blue" icon_color="blue" quote="Any intelligent fool can make things bigger and more complex… It takes a touch of genius – and a lot of courage to move in the opposite direction." said_by="Albert Einstein" %}

### 2.2 MyNote.html

This theme is comes with four kinds of notes. These are **success, info, warning and danger.** This feature will make your blog interactive and different. You can add the nates by using following code:
<pre class="line-numbers">
<code class="language-markdown">
{% raw %}
{% include MyNote.html note_type="success/info/warning/danger" span_note="inline heading goes here: " text="your note goes here" %}
{% endraw %}
</code>
</pre>
{% include MyNote.html note_type="success" span_note="Success: " text="The software is provided as is, without wattanty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and infringement." %}
{% include MyNote.html note_type="warning" span_note="Warning: " text="The software is provided as is, without wattanty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and infringement." %}
{% include MyNote.html note_type="info" span_note="Info: " text="The software is provided as is, without wattanty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and infringement." %}
{% include MyNote.html note_type="danger" span_note="Danger: " text="The software is provided as is, without wattanty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and infringement." %}

## 2.3 video.html

{% include video.html aspect_ratio="4-3" id="zpOULjyy-n8?rel=0" %}
### Default aspect ratio
{% include video.html id="zpOULjyy-n8?rel=0" %}
