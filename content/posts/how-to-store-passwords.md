+++
author = "Vladislav Alexeyev"
date = "2022-08-20T00:40:00Z"
description = ""
slug = "how-to-store-passwords"
tags = ["passwords", "manual"]
title = "Ways to store passwords 🔑"
type = "post"
+++

Our purpose is to understand how to store this login/password pair on the server. If the database is stolen we want the attackers not to be able to access the account itself or make this process as labor-intensive as possible.

## Plain-text storage 
We store the password in clear text, here it was `qwerty` and write `qwerty` to the database

Everything should be obvious here, the database was stolen means that all passwords were stolen. A real gift to the attacker, please do not be so generous. 

Also, remember to remove sensitive data if you use loggers inside your application. Ensure you don’t keep plain-text passwords even if you protect your passwords on the DB side and the attacker won’t be able to see them inside logs.

```
{"login": "john", "password": "**removed**"}
```

is much better than

```
{"login": "john", "password": "qwerty"}
```

## Store password as a hash 
According to the definition, a hash function is an irreversible function.

Just a simple example: let’s say that  f(x) = x % 10 will be our hash function. 
```
 f(x) = x % 10
 f(123456789) = 12345679 % 10 = 9 
```

As you can see in the previous example. You can’t get 123456789 back using 9. Because all the numbers ending with 9 will hash to f(x) = 9. 
In plain words, a hashing algorithm is a mathematical function that garbles data and makes it unreadable. 

Let’s store a hash of the password, for example, take one of the most popular algorithms MD5 (NB: It’s highly not recommended for storing passwords) 

```
md5(qwerty) = 897c8fde25c5cc5270cda61425eed3c8
```

As we already discussed, there is no way to get `qwerty` from `897c8fde25c5cc5270cda61425eed3c8` within a computational way. But to crack such 

A rainbow table is a precomputed table for caching the output of cryptographic hash functions.

You can do such a simple trick - take the database of popular passwords and run md5 through it, you get a dictionary where `qwerty` corresponds to `897c8fde25c5cc5270cda61425eed3c8`. 
This dictionary can be expanded and attackers already have millions of compromised passwords inside rainbow tables. 

## Store password as a hash + salt 
[Rainbow table - Wikipedia](https://en.wikipedia.org/wiki/Rainbow_table)
[Understanding Rainbow Table Attack - GeeksforGeeks](https://www.geeksforgeeks.org/understanding-rainbow-table-attack/)

## Store password with secret 
## Passwordless 
