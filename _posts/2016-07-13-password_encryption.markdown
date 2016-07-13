---
layout: post
title:  "Password Encryption "
date:   2016-07-13 21:53:38 +0000
---


Recently I used bcrypt ruby gem to create the sign-up and login process for an application. I wanted to use this blog post to talk about the password encryption process and what is actually happening. 

Password encryption is absolutely crucial to web development as it protects your programs from hackers. This process takes 2 levels of encryption to make the ability to hack much more difficult. The first part of the encryption process to understand is password hashing.

Password hashing uses a hash algorithm that takes the given word that is entered ( password string) and turns it into a fixed length fingerprint that can't be reversed. An example of this is:

hash("password123") = 

c0e81794454496161f1777cdd2bc6bdedc38f616560b120fda8e90f383853542

The second part of the encryption process to understand is salting. Having a salted password means that you are adding a random word to your password before it is being hashed. This word is different for each password entered into your program. 

Your program is looking to save the password entered safely into the database to protect from hackers and then be able to safely retrieve when a user is logging in. Logging in will require them to authenticate if their password entered matches up with the stored password. Using bcrypt gem, Your password entered will be given salt before it is being hashed. It will then store the hashed word along with the salt word to use for retrieval. The hash generated is the password and the salt concentrated. 

One important thing to understand is that salt is primarily used in order to protect the passwords from brute force. Hackers can use tables that are precomputed with hashed passwords stored in them. These tables (rainbow tables) can run millions of hashes quickly in order to figure out what your password is. Using salt stops these programs from working as it creates a random word every time that can't be precomputed. This will then alter the hashed string. 

Proper password encryption is a must for any web developer and it was very helpful for me to take a step back and understand properly what is going on. 

Happy coding! 





