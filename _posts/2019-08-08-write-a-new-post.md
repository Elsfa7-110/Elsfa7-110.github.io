---
title: favicon.ico for BugBounties
author: Elsfa7-110
categories: [Blogging, Tutorial]
tags: [writing]
---

## Introduction
## What is favicon.ico

Modern Browsers will show you a small image/icon to the left side of the webpage title , that icon is known as favicon.ico . This is icon is generally fetched from https://anywebsite/favicon.ico and browsers automatically request it when you will browse any website.

## How to calculate Favicon hashes from favicon.ico

https://gist.github.com/yehgdotnet/b9dfc618108d2f05845c4d8e28c5fc6a

## Favicon Hashes + Shodan

You can search for assets/IPs using favicon hashes on shodan using http.favicon.hash:[Favicon hash here] filter.

Example :

Generally the favicon hash of any spring boot application is 116323821. So we can use this shodan filter http.favicon.hash:116323821 for finding Spring Boot instances .
Here is a oneliner for doing the same using shodan CLI :
$ shodan search org:"Target" http.favicon.hash:116323821 --fields ip_str,port --separator " " | awk '{print $1":"$2}'

Note : This is just one example, you can use different favicon hashes for different services. Be creative !

## Automating all this

tool named “FavFreak” that makes my work a hell lot easier, it takes a list of urls (with https or http protocol) from stdin ,then it fetches favicon.ico and calculates its hash value. It sorts the domains/subdomains/IPs according to their favicon hashes and the most interesting part is , It matches calculated favicon hashes with the favicon hashes present in the fingerprint dictionary , If matched then it will show you the results in the output, there is option to generate shodan dorks as well (that is pretty basic and you can do it manually as well)
Example
FavFreak can be found here : https://github.com/devanshbatham/FavFreak
