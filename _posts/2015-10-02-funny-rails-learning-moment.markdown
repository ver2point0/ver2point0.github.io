---
published: true
title: Funny rails learning moment
layout: post
tags: [rails, learning, moment, error]
---
<h2>What I saw</h2>
- I assumed that ***What I typed*** was one long command.

<h2>What I typed</h2>
- `rails generate rspec:controller welcome create spec/controllers/welcome_controller_spec.rb`

<h2>What resulted</h2>
- Three spec files and a weird folder structure. Guess what the folder structure looked like.

<h2>What I did after the results</h2>
- I deleted everything that was created by ***What I typed***, and typed `rails generate rspec:controller welcome`. I produced favorable results.

<h2>What I learned</h2>
- `rails generate rspec:controller welcome # this is a command`
- `create spec/controllers/welcome_controller_spec.rb # this is confirmation of my rails generate line`