---
layout: post
title:  "WhatsApp Share and Contact Button"
date:   2017-06-17 10:07:39 -0700
category: Jekyll
color: deep-orange
img: /static/IMG/whatsapp.jpeg
tags: 
- Jekyll
- HTML
---
### Whatsapp Share Button
Nowadays Whatsapp became a powerful messegaing platform. So get in touch with friends and colleagues we are using whatsapp. So Whatsapp has 600 million users in world wide. It is not a small number. Nowadays WhatsApp has more number of users than any other social media except facebook. In this post we will discuss how can we create a WhatsApp share button for a Jekyll Website. See the following code.
```markdown
<a href="whatsapp://send?text=The text to share!" data-action="share/whatsapp/share">Share via Whatsapp</a>
```
It will show something like this:
<a href="whatsapp://send?text=The text to share!" data-action="share/whatsapp/share">Share via Whatsapp</a>
Now we want to think how can we use use this as the share button. We know that for our Jekyll website has `site.url`, `base.url` and a `page.url`. We want share the url of post. It usually looks like 
```markdown
https://chipprogrammers.github.io/jekyll/2017/06/17/whatsapp-share-and-contact.html
```
Here https://chipprogrammers.github.io is my `site.url` and /jekyll//2017/06/17/whatsapp-share-and-contact.html is my `page.url`. I have no site.baseurl since I am named my repository in the format `username.github.io`. Now we can see how the code should be written.
```markdown
<a href="whatsapp://send?text= { site.url }{page.url }" style="position: relative; top: -8px; padding: 3px 8px 3px 8px;color: #fff;font-size: 11px;font-weight: bold;font-family: Helvetica, Arial, sans-serif;background-color: #5bb66f;border-radius: 3px;"><i class="fa fa-whatsapp" aria-hidden="true"></i> Whatsapp</a>
```
<font color="red">Note: 
<ul> <li>Actually Code Snippet not allowing me to write site.url and page.url in double braces. After copying and   pasting this code it is your responsibility to put them into double braces.</li>
<li> This code never works with every browser(especially from your desktop browsers). However this code works well with Google Chrome Android.</li>
</ul>
</font>
This will produce a button like following:<br /><br />
<a href="whatsapp://send?text={{site.url}}{{ page.url }}" style="position: relative; top: -8px; padding: 3px 8px 3px 8px;color: #fff;font-size: 11px;font-weight: bold;font-family: Helvetica, Arial, sans-serif;background-color: #5bb66f;border-radius: 3px;"><i class="fa fa-whatsapp" aria-hidden="true"></i> Whatsapp</a><br />
Reference: [Yateendra/very-simple-whatsapp-sharing-button](https://github.com/yateendra/Very-Simple-WhatsApp-Sharing-Button)

### Whatsapp Contact Button
It is very easy to build a Whatsapp contact button on your website. You can see perfect example for this on the header of this blog. I do not going to exaggerate theae things. It is the code:
```markdown
<a href="https://api.whatsapp.com/send?phone=+cc-xxxxxxxxxx"><i class="fa fa-whatsapp"></i>Whatsapp Contact</a>
```
Type your phone number with contry code instead `+cc-xxxxxxxxxx`. The output of this one shows something like this:<br /><br />
<a href="https://api.whatsapp.com/send?phone=+91-8281618806"><i class="fa fa-whatsapp"></i> Whatsapp Contact</a>
<br />
Sometimes this guy shows erroneous results too 😢. But it is the only possible way...<br />
