---
layout: post
title:      "Ruby On Rails: Delicate Balance"
date:       2021-02-14 13:33:59 -0500
permalink:  ruby_on_rails_delicate_balance
---

**Working within the scope**

Git Repo: https://github.com/CoreyM21/Ruby-On-Rails-Donut-Review-App
Video Walkthrough: https://www.youtube.com/watch?v=aNsoN38TsnQ

For my Ruby on Rails project, I wanted to stick to the idea that this could potentially be used now and not just exist in the vacuum of, "Well, I built this for school, and I want to show it off later in portfolio" but more in the idea that, I can take this project that I did for school and allow people to use it now. One of the many companies I have been a part of include the "North Fork Donut Company" located on Long Island, NY. Something their company needs but does not have is a way to gauge people's reactions to the donuts they were creating, past and present! This could: 1. Build a rapport with their customer 2. Engage with their audience in a more personal manner and finally, 3. Discover fan favorites and why! It’s all about building a better business and for myself, learning and implementing the lessons learned to practical world applications.

**Donuts Review App**

The basic premise for this app is that a user can sign up, login, create a new donut, see the donuts they have created, see all donuts created by all users, review their donut, see reviews made on that or any donut, see all the reviews they created, edit and delete donuts they have created, edit and delete reviews, and finally logout of the application. You can also login to this app using a third party. I used Google.

The fun aspect of this project was creating the models of User, Donut, and Review and their relationships. Creating the joins table, has many, and belong to relationships so that I may call on these relationships and view the right information I want to see. It became all about creating that delicate balance. Before I started coding, I consulted my cohort lead to get the relationships right and the following outline was created:

USER
has many reviews #that they created
has many donuts #that they created
has_many :reviewed_donuts, through: :reviews, source: :donuts #

DONUT
has many reviews
has many users through reviews

REVIEW
belongs to donut
belongs to user

This allowed me to have Donut be my has many through relationship and open up all the possibilities that entails! This was my greatest lesson coming out of this project. I was able to fully grasp what these relationships meant, what they allowed me to do, and what specific calls I could make to get the right information created and displayed to my users.


**Start Coding Already!**

I was not allowed for this project to use Scaffold for Ruby on Rails. However, to streamline the process and put myself on the right foot, I did use Rails Resource Generator. This created for me: creates a migration for me, model, controller, and opens all routes in config/routes.rb. This instantly gave me MVC capabilities.

Then I created migrations to add donut to reviews, add user to reviews, and add user to donuts. Fantastic but what did this allow to do? Now when I create a User and that User then creates a Donut, I can call in my code:

User.donuts.all 

Or more specifically in my show view for a User I called the following logic for if the User did not create any donuts, a message was displayed but they did their donuts they created were displayed:

<h2> Your Donuts</h2>

    <% if @user.donuts.empty? %>

        <p>You have not created any donuts yourself! <%= link_to "Click here to create your first donut!", new_donut_path %> </p>

    <% else %>

        <% @user.donuts.each do |d| %>

        <div>        
            <%= link_to(d.name, donut_path(d)) %>
        <div>
            
        <% end %>

        </div>

    <% end %>
	

 As you can see, first I was able to ask @user.donuts.empy? which says look into this created User and see if you can find any donuts created by it. If empty, show that but if not, display those donuts created by THIS User. 
 
 This goes another fun step when I tell the page to show the reviews created by this User with the Donuts those reviews are for:
 
 <h3> Your Reviews</h3>

    <% if @user.reviews.empty? %>

        <p>You have not created any reviews yourself! <%= link_to "Click here to see the all the donuts made and review!", donuts_path %> </p>

    <% else %>

        <% @user.reviews.each do |r| %>

        <div>    
            <%= "#{r.donut.name} - " %><%= link_to(r.description, review_path(r))%>
        <div>
            
        <% end %>

        </div>

    <% end %>

Here, I ask the code to go into this User, look for the reviews created then through that pull each review and display to User in "r: which Review, Review.donut.name then with the review in Review.description.

Through these relationships, I could call User.donuts.reviews.count and it would go into each donut this user created, see the reviews this user created for each of these donuts and then count them for me. This was both the most frustrating thing for me to understand and build but when it all came together, it was a work of delicate art put together before my eyes and the possibilities became limitless. 

**Nested Routes**

Through this relationship, I was also able to create nested routes for my program to understand. It took me a while to grasp and at one point, it nearly broke me, but I was able to understand this vital pathway: new_donut_review_path. This route was able to tell my code to take this Donut that was created and create a new Review that belongs to this Donut and to this User. The key takeaway that opened it all up: this Review belongs to this User THROUGH this Donut. Once I had that down, I was able to have the User show page show donuts they have created, and reviews they created, whether they created the donut. Nested Routes was the key to my understanding the joins table and able to create a viable working program. It was very exciting and certainly a pat on the back moment for me.

**Conclusion**

Creating the balance between these Model was a fun endeavor. I learned the key to relationships and nested routes which opened my mind and my program to lots of capabilities. Not only that but made the world fun to look at when I go this coffee belongs to me through Dunkin. Granted that is a very simple version but makes the world interesting to look at.

