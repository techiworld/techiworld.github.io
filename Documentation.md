---
layout: default
title: Docs
prism: true
---

This is multi-purpose Jekyll template made by Chipprogrammer. I am not a web designer. But I put some awesome effort to make this theme possible since I have some enthusiasm in Webdesigning. This Jekyll theme has some awesome include features. But errors and omissions are allowed. Since I mentioned earlier I am not a **web designer**.
# Includes

### quotes.html
<pre class="line-numbers">
<code class="language-markdown">
{% raw %}
{% include quotes.html container_color="pale-blue" leftbar_color="blue" icon_color="blue" quote="Any intelligent fool can make things bigger and more complex… It takes a touch of genius – and a lot of courage to move in the opposite direction." said_by="Albert Einstein" %}
{% endraw %}
</code>
</pre>
{% include quotes.html container_color="pale-blue" leftbar_color="blue" icon_color="blue" quote="Any intelligent fool can make things bigger and more complex… It takes a touch of genius – and a lot of courage to move in the opposite direction." said_by="Albert Einstein" %}

### MyNote.html
{% include MyNote.html note_type="success" span_note="Success: " text="The software is provided as is, without wattanty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and infringement." %}
{% include MyNote.html note_type="warning" span_note="Warning: " text="The software is provided as is, without wattanty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and infringement." %}
{% include MyNote.html note_type="info" span_note="Info: " text="The software is provided as is, without wattanty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and infringement." %}
{% include MyNote.html note_type="danger" span_note="Danger: " text="The software is provided as is, without wattanty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and infringement." %}
