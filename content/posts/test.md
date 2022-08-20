+++
author = "Vladislav Alexeyev"
date = "2019-03-07T12:00:00Z"
description = "Как правильно арендовать квартиру в Польше — подводный камень, с которым сталкиваются иммигранты"
slug = ""
tags = ["Польша", "аренда квартиры", "законы"]
title = "Ways to store passwords"
type = "post"
+++

Our purpose is to understand how to store this login + password pair on the server. 
If the database is stolen, the attackers would not be able to access the account itself or make this process as labor-intensive as possible.


## Plain-text storage
We store the password in clear text, here it was password123, and write password123 to the database

Everything should be obvious here, the database was stolen means that all passwords were stolen.  A real gift to the attacker, please do not be so generous. 

## Store password as a hash 
It was a popular solution quite some time ago. 

[Rainbow table - Wikipedia](https://en.wikipedia.org/wiki/Rainbow_table)
[Understanding Rainbow Table Attack - GeeksforGeeks](https://www.geeksforgeeks.org/understanding-rainbow-table-attack/)
![https://img.alexeyev.me/1638393509_28-celes-club-p-smeshnie-kabani-zhivotnie-krasivo-foto-32.jpeg](https://img.alexeyev.me/1638393509_28-celes-club-p-smeshnie-kabani-zhivotnie-krasivo-foto-32.jpeg)
## Store password with secret 
## Passwordless 

