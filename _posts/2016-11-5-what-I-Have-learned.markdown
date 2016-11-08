---
layout: post
title:  "What I have learned working on coding challenges"
date:   2016-11-07 18:52:00
categories: programming 
---

# What I have learned from coding challenges 

Lately I've been on the path to make a career change.  Right now I work as a legal assistant and I'd like to become a web developer.  Part of the interview process for becoming a web developer includes completing code challenges and submitting them to the interviewer for their team to review.  All previous projects I have worked on have been my own design.  When I say design, I probably should say lack of design.  I start out with a vague idea like I want to improve how I make legal documents or I want to do something with the CTA bus tracking API.  From there I kind of hack on the idea until it becomes an application.  This process is fun and great for exploring ideas, however it isn't an efficient way to solve a problem.  

Many of the challenges I have received are basically a couple paragraph narratives on a product I am to build.  They give some guidelines, like which libraries are allowed, how much UI design is needed, whether the project needs to be mobile friendly etc.  Upon reflection of the last couple projects that I have submitted I found that I have not broken the instructions down into features and then created tests with the list of features.  My work flow needs improvement, and though no interviewer has given me this feedback, by looking back on my previous work I can see this as an area of improvement.  Additionally I see this as an area that if I was a professional and I saw my work, I'd be concerned that I could not breakdown problems into features and then implement those features.  

## Change in how I am plan on approaching testing 

For the reason above I have decided to change how I approach testing my applications and how I do test driven development.  I have previously and incorrectly believed that Unit Tests first TDD is the way to go, I no longer believe this is the best route.  I intend on taking the route of looking at the whole problem, breaking it down to features and then ordering the features by priority.  Finally writing a feature test, write passing code, then refactor.  After feature tests are in place I'll look at unit test and integration tests.  I think writing feature tests first will put an emphasis on covering all the features so that the product doesn't deviate from the instructions.

## Graphs 

Recently I worked on a coding challenge that involved graphs.  I feel like a have a pretty good understanding of graphs for someone who is mostly a ruby developer.  However in this last challenge I got stuck, and the reason I believe I got stuck was because I was trying to optimize the solution to early instead of finding a working solution.  Most of my knowledge about graphs is from the Princeton Algorithms course on Coursera.  In the problem I was working on I was trying to find all the cycles between two points, I was trying to use a BFS algorithm, however it would only find the shortest cycles, but not all of them up to a certain weight.  I believe a less efficient/optimized algorithm could have found these cycles at a hefty computation cost. Since the problem was dealing with like 8 points, not 8000, a more costly computation time would have still worked.  

## When you realize you aren't using rails in a rails way and how to fix that 

I am self taught, I sometimes use tools in ways that may not be the community standard way.  I don't always do things in the Ruby on Rails way.  I have set myself on a mission to fix this.  The first step is I picked up a copy of Rails 4 in Action.  I chose this book over The Rails Way 4 book because of the reviews saying that it was mostly a restatement of the Rails guides online.  Since I am perfectly capable of reading the rails guides, I didn't think the book was necessary at the moment, however I do want to pick up the book when he releases the next edition that addresses Rails 5.  

I picked up Rails 4 in action because it walks the reader through building a ticket tracking application.  So far I've read half the book and started building the beginning parts of the application.  I am blown away by what the book covers.  Specifically namespaced controllers, capybara feature tests, pundit app to authorize multiple types of users to do certain actions.  I think after I work through the book I plan on rewriting parts of my Subpoena application to handle multiple organizations and users with users and admin roles.  I also would like to go back and rewrite 2 of my coding challenge projects with Rails to further ingrain what I have learned from the book. 

I have also picked up Eloquent Ruby from the library.  The book is really informative, and is probably a must read for Ruby devs, I wish I had picked it up sooner.  

Additionally, I hope to find new people to pair program with and hopefully learn to program in a more rubyistic (is this a word???) way.  


