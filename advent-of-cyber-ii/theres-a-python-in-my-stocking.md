---
description: Scripting
---

# There's a Python in my stocking!

## Video

{% embed url="https://www.youtube.com/watch?v=lvcZRKO-B20" %}

## Resources

`pip install X`

`pip3 install requests beautifulsoup4`

```python
# Import the libraries we downloaded earlier
# if you try importing without installing them, this step will fail
from bs4 import BeautifulSoup
import requests 

# replace testurl.com with the url you want to use.
# requests.get downloads the webpage and stores it as a variable
html = requests.get('testurl.com') 

# this parses the webpage into something that beautifulsoup can read over
soup = BeautifulSoup(html, "lxml")
# lxml is just the parser for reading the html 

# this is the line that grabs all the links # stores all the links in the links variable
links = soup.find_all('a href') 
for link in links:      
    # prints each link    
    print(link)
```

&#x20;This was a very short introduction to Python, but here are some more links if you wanted to learn more:

* [Python Zero to Hero](https://polymath.cloud/python/)
* [Python Moduluo Operator in Practice](https://realpython.com/python-modulo-operator/)
* [Automate the Boring Stuff with Python](https://automatetheboringstuff.com)

## Challenge

### What's the output of True + True?

{% hint style="success" %}
2
{% endhint %}

### What's the database for installing other peoples libraries called?

{% hint style="success" %}
PyPi
{% endhint %}

### What is the output of bool("False")?

{% hint style="success" %}
True
{% endhint %}

### What library lets us download the HTML of a webpage?

{% hint style="success" %}
Requests
{% endhint %}

### What is the output of the program provided in "Code to analyse for Question 5" in today's material?

&#x20;(This code is located above the Christmas banner and below the links in the main body of this task)

{% hint style="success" %}
\[1, 2, 3, 6]
{% endhint %}

### What causes the previous task to output that?

{% hint style="success" %}
Pass by reference
{% endhint %}
