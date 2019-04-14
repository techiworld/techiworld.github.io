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

{% include MyNote.html note_type="warning" span_note="Warning: " text="By pressing keys we are actually putting a short circuit between two GPIO pins. So that you have to make sure that columns are connected correctly. Unless there is chances for Blue smoke." %}

Here I chose a 2D array (Python List) to  save name of product, RFID unique number, and price of product respectively.
<pre class="line-numbers" data-start="14">
<code class="language-python">
{% raw %}
product = [
    ['Product1', 858624605840, 8000],
    ['Product2', 236811894460, 1000],
    ['Product3', 650705026722, 1200],
    ['Product4', 99658219146, 800],
    ['Product5', 30953647075, 900]
    ]
{% endraw %}
</code>
</pre>
{% include MyNote.html note_type="info" span_note="Info: " text="Here I added only 5 cards. You have to add details of 5 more cards. I written unique ID of each card on it using a cd marker. You have to just make a 2D array using that info as I written above." %}

As I mentioned in the class the GPIO pin connected to row of keypad  pulled-low to ground in order to avoid floating condition. GPIO pins connected to column is configured as output.

<pre class="line-numbers" data-start="21">
<code class="language-python">
{% raw %}
for row_pin in rows:
    GPIO.setup(row_pin, GPIO.IN, pull_up_down=GPIO.PUD_DOWN)

for col_pin in cols:
    GPIO.setup(col_pin, GPIO.OUT)
{% endraw %}
</code>
</pre>
{% include MyNote.html note_type="info" span_note="Info: " text="Refer Raspberry Pi hardware reference <a href='https://www.raspberrypi.org/documentation/hardware/raspberrypi/bcm2835/BCM2835-ARM-Peripherals.pdf'> documentation</a> in order to know which GPIO pins are pulled to LOW(Refer page number 102). If you have to change GPIO pins connected to keypad you have to keep this documentation in mind to find out GPIO pins pulled to ground."%}

The keypad is scanned by output a logical HIGH (1) through column pins one by one and scans for 0.3 seconds for key press in order to avoid noise as well as false key press. If there is a short circuit the raw GPIO pin gets a logical HIGH, so that we can detect key press. The following function helps to find out pressed key. Please go through 3 articles I given on readme file.

<pre class="line-numbers" data-start="26">
<code class="language-python">
{% raw %}
def get_key():
    key = 0
    for col_num, col_pin in enumerate(cols):
        GPIO.output(col_pin, 1)
        for row_num, row_pin in enumerate(rows):
            if GPIO.input(row_pin):
                key = keys[row_num][col_num]
        GPIO.output(col_pin, 0)
    return key
{% endraw %}
</code>
</pre>

`fixed` is a variable that stores maximum digit number for transaction. Here I choose that as 5 so that we can do maximum transaction of ₹99999. `count` is the variable increments after each detection of each key press. `budget, count and fixed` are the variables used to convert each digits entered via key press into single number. `budget_enter` is an _indicator_ used to indicate whether 5 times key press occurred or not.

<pre class="line-numbers" data-start="35">
<code class="language-python">
{% raw %}
count = 0
budget = 0
cart = 0
print("Enter your Budget as a 5 digit number on keypad:")
fixed = 5
Budget_enter = False
{% endraw %}
</code>
</pre>
{% include MyNote.html note_type="warning" span_note="Warning: " text="User have to enter digit as 5 digit number by prepending zeros to numbers. For example in order to enter 123, he should enter 00123"%}
