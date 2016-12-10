---
published: true
title: Funny rails learning moment
layout: post
---
## What I saw
- I assumed that ***What I typed*** was one long command.

## What I typed
- `rails generate rspec:controller welcome create spec/controllers/welcome_controller_spec.rb`

## What resulted
- Three spec files and a weird folder structure. Guess what the folder structure looked like.

## What I did after the results
- I deleted everything that was created by ***What I typed***, and typed `rails generate rspec:controller welcome`. I produced favorable results.

## What I learned
- `rails generate rspec:controller welcome # this is a command`
- `create spec/controllers/welcome_controller_spec.rb # this is confirmation of my rails generate line`