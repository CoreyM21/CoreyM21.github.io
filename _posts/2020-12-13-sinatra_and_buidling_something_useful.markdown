---
layout: post
title:      "Sinatra and Buidling Something Useful"
date:       2020-12-13 21:08:54 +0000
permalink:  sinatra_and_buidling_something_useful
---

**Building Something Someone Can Actually Use!**

https://github.com/CoreyM21/sinatra-cbd-customer-app

I procrastinated yet again but it worked out this time. Why? The steps I took to build out my project worked and even though I stilll gave myself a short amount of time to build out this massive project (way more time needed than the CLI project), it worked. out. At the time of writing this, my project isn't 100% done. It still needs work but it'll get done and be able to be used by my friends for their business!

**CBD Customer App

The way I started out my project was months ago! Figuring out what sinatra was capable of and also what I wanted to build that could: 1. Useful. 2. Fun to build. 3. Not impossible to get done! I settled on buidling a database for my friends CBD business on Long Island. Follow them @island_grow. They grew and harvested their first crop this year and now are in the process of selling their product. After talking with them and what my project ideas were, they agreed that something that each person could log into, create a customer they were focused on, edit if need be, delete if need be, and see what customers were created was program they could use daily.

The first steps to the project build started with writing out all my steps, I've actually included the below out line:

"CBD Customers Database"

App Overview

-I am going to build a customers database to store customers information to reach out to. It should be able to enter the customers information, store it, edit it, and show status of that customer i.e. Reached out, emailed, called, sold product, working on deal.

As a user, I will be able to....

-Log in, sign up, log out
-create a customer
-see customers created
-edit customer entry
-delete customer entry

Wireframing

Models will be User and CustomerEntry

User

Attributes

- name
- email
- password (if I use bcrypt, this will be "password_digest" in the database)

Associations

- has many :customer_entries

CustomerEntry

Attributes

- user_id <--- This will be the foreign key
- name
- address
- contact info
- status <--- is this a stretch goal?
- date added <--- is this a stretch goal?

Associations

- belong_to :user

MVP

- Users can sign up, log in, log out, create customer entries, edit their own entries and view their entries

Stretch Goal

- CSS - make it look really nice
- Tests
- Include a join model
include a customer model - users have different customers and a customer has many entries
- users can make their entries public or private
- have drafts (save drafts to edit later)

This helped tremendously! Ordering it all out and getting my steps reay. I was ready to start building and had where I wanted to go.

**Start Coding Already!

I started building my project with the Corneal Gem. Running Corneal essentially sets up the entire file structure for a Sinatra Application. I also used the Corneal Scaffold feature, which generates your models along with their associated controllers and views. The Corneal Gem was really handy; It saved me time and eased me into the coding itself. The Model syntax and Controller CRUD routes were all set up for me, so I could dive right into the code.

My application has two models - Usersa and Customer Entries. Users can have many Ciustomer Entries. Customer Entires can belong to a User. Essentially, Users can create Customer Entries with details such as name, address, phone number, email, and status of the customer. 

Seems relatively simple and it is! But I was surprised at how detail goes into just logging in the user! But all my focus was put into funtionality. I wanted to make sure this app wors and is solid. There would be pletny of time later to make it look pretyy and make sure everything looked unique but I needed to make sure this app works. Right now, its mostly done but its just going to take some more time to make sure it can do everything well.

**Conclusion

Overall, I came into this project way more prepared than the last one. I still took my sweet time getiing started and I need to fix that. But the foundations were there this time and I understood where I wanted to go with it. Working on this project was exciting though! See where I could literally buid the user interface and give it funtionality made it fantastic! Looking forward to what else can we build!




