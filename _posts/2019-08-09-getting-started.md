---
title: Automating XSS, ParamSpider and Dalfox
author: Elsfa7-110
categories: [XSS, Tutorial]
tags: [XSS]
pin: true
---


## Installation

Hello Everyone! 😄

Hope you all are good.
```

Pre-Requisites :
https://github.com/devanshbatham/ParamSpider
https://github.com/hahwul/dalfox
```

## Workflow

    After Installation of all above mentioned tools, Choose your Target. Let’s use “http://testphp.vulnweb.com/” for demonstration purposes.
    Use ParamSpider to fetch URL’s for the chosen target and save the Output in a text file.
    python3 paramspider.py --domain testphp.vulnweb.com
    Time to fire Dalfox and start finding XSS.
    
    dalfox file output/testphp.vulnweb.com.txt -b saad.xss.ht pipe

    Make sure you replace my Blind XSS Hunter Payload with that of yours.
Hope you guys like this. Do give it a Clap if liked it. 👏```
