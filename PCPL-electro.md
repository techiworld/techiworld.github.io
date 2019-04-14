---
layout: default
title: RFID Project Docs
prism: true
---

Clone my github repository using executing following commands one by one:
<pre class="line-numbers">
<code class="language-bash">
{% raw %}
cd ~
git clone https://github.com/arunksoman/PCPL-electro.git
cd PCPL-electro
{% endraw %}
</code>
</pre>

In order to install Python library used to read RC522, in current working directory execute following command on terminal:
<pre class="line-numbers">
<code class="language-bash">
{% raw %}
cd my-project
python setup.py install
cd ..
{% endraw %}
</code>
</pre>

## Explanation: main.py

Import necessary modules and packages:
<pre class="line-numbers">
<code class="language-python">
{% raw %}
import RPi.GPIO as GPIO
import time
import sys
from mfrc522 import SimpleMFRC522
{% endraw %}
</code>
</pre>

Choosing Physical pin numbering as BOARD and warnings about using GPIO channels are neglected.

<pre class="line-numbers" data-start="5">
<code class="language-python">
{% raw %}
GPIO.setmode(GPIO.BOARD)GPIO.setwarnings(False)
{% endraw %}
</code>
</pre>

