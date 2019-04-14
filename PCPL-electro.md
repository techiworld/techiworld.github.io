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
GPIO.setmode(GPIO.BOARD)
GPIO.setwarnings(False)
{% endraw %}
</code>
</pre>

Rows of the keypad is connected to GPIO physical pins  8, 37, 11, and 12. While columns are connected to GPIO physical pins ( as per pin BOARD number) 32, 33, 35, and 36.
<pre class="line-numbers" data-start="7">
<code class="language-python">
{% raw %}
rows = [8, 37, 11, 12]
cols = [32, 33, 35,36]
keys = [
    ['1', '2', '3', 'A'],
    ['4', '5', '6', 'B'],
    ['7', '8', '9', 'C'],
    ['*', '0', '#', 'D']]
{% endraw %}
</code>
</pre>

{% include MyNote.html note_type="warning" span_note="Warning: " text="By pressing keys we are actually putting a short circuit between two GPIO pins. So that you have to make sure that columns are connected correctly. Unless there is chances for Blue smoke :rocket:" %}
