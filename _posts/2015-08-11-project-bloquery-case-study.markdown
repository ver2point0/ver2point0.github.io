---
published: true
title: Project BloQuery case study
layout: post
tags: [Project, Bloquery, CaseStudy]
---
<h2>Summary</h2>

BloQuery takes advantage of the free-to-use Parse API to create an open question and answer platform.

##Explanation

This project employed a Mobile Backend as a Service (MBaaS) to provide a cloud backend for my Android application. I chose Parse's API because it provides features required of most backend APIs: databases, push notifications, authentication, file storage, and much more. Parse made it easy for a mobile developer like me to build my application without having to master backend software development. 

I made this project as part of my Android development apprenticeship to learn how to build applications on my own with minimal explanations and guidance.

##Problem

The following user stories are what I was required to implement:

1. As a user, I want to create a BloQuery account.

2. As a user, I want to view the latest user-generated questions or BloQueries.

3. As a user, I want to answer questions with text responses.

4. As a user, I want to view existing answers to questions.

5. As a user, I want to post new questions.

6. As a user, I want to customize my profile with a profile image and description.

7. As a user, I want to view other users' profiles.

8. As a user, I want to up vote answers to questions.

9. As a user, I want to sort answers by the number of up votes they've received.

##Solution

Before I began implementing the user stories, I consulted Parse's quick start [guide](https://parse.com/apps/quickstart "Parse's Quick Start guide") on how to integrate the API into my application. Integrating the API into applications is relatively easy because it is guided and uses visual content to make sure it is done properly. 

The guide starts with users selecting their desired product among 7 choices: Data, Push, Analytics, Social, Cloud Code, Hosting, and Embedded. Next, you select your environment. I chose mobile. After that, you select your operating system. Parse currently has iOS, Android, or Windows. The next step is to choose Native (Java) or Xamarin (C#) as your language. Lastly, it is time to decide between setting up Parse with a new project or existing project. I chose an existing project. 

1. As a user, I want to create a BloQuery account.

   In order for the user to create a BloQuery account, login and signup screens were needed. I was able to design my [login](http://www.android-app-patterns.com/category/login-screens "Android App Patterns") and [sign up](http://www.android-app-patterns.com/category/signup "Android App Patterns") screens by referencing varying implementations across other applications on Android App Patterns. I used Parse's ParseUser class to create and store new users

2. As a user, I want to view the latest user-generated questions or BloQueries.

   The user must be logged in to view the latest user-generated questions. I created a fragment to show users the latest questions. Each item in the list the shows the question and the associated user. I created another fragment to view individual questions. If users click an individual question, they will see that question and the user's name.

3. As a user, I want to answer questions with text responses.

   Users can answer questions by viewing them individually. I created a dialog fragment that pops up when users press the plus button on the application's toolbar. From there, users can answer questions and submit them.

4. As a user, I want to view existing answers to questions.

   To view answers to existing questions, I created an adapter and a new layout for my existing individual question fragment. By clicking on an individual question, users can view any and all answers to existing questions. 

5. As a user, I want to post new questions.

   The functionality is similar to the third user story. From the list of user-generated questions, users can post new questions by click the newly added plus button on the toolbar. A dialog fragment will open up allowing users to ask new questions and submit them.

6. As a user, I want to customize my profile with a profile image and description.

   Users can customize their profile images and descriptions if they are logged in under their names. I utilized the SquareImageView class and a new fragment to allow users to edit their profiles. After users have logged in under their names, they have to click their names in the question view or answer view for profile customization. 

7. As a user, I want to view other users' profiles.

   Users can only view other users' profiles in a read only version. In the previous user story, functionality was implemented in the fragment see other user profiles.

8. As a user, I want to up vote answers to questions.

   In the adapter I created for the fourth user story, I added buttons that would allow users to give points to the most helpful answers and take away points from the least helpful answers.

9. As a user, I want to sort answers by the number of up votes they've received.
   
   Sorting answers by the number of up votes they've received was implemented by including a         `query.orderByDescending("points");` call in my ParseQuery class.

##Results

Please, head over to my Github account to reference my [BloQuery](https://github.com/ver2point0/BloQuery "BloQuery") application. I will be explaining how I made sure the user stories above worked in my application. 

###Login 
   
<div id="wrapper" style="width:100%; text-align:center">
          <img src="https://cloud.githubusercontent.com/assets/12492121/9129891/1bf57b04-3cab-11e5-9413-85cbdfb0bdb3.png"  width="250" text-align= "center" >
</div>

   - First, I tried to login into BloQuery without signing up. It did not work. A message appeared saying *Username or Password incorrect*. Next, I clicked the sign up button to create a new account.

###Signup

<div id="wrapper" style="width:100%; text-align:center">
          <img src="https://cloud.githubusercontent.com/assets/12492121/9129893/2b5706bc-3cab-11e5-8a97-33748a330497.png"  width="250" text-align= "center" >
</div>

   -  I created a new user named John Doe, then I logged out and created another user named Jane Smith. 

###Question

<div id="wrapper" style="width:100%; text-align:center">
          <img src="https://cloud.githubusercontent.com/assets/12492121/9129895/31ea39ae-3cab-11e5-8e9a-9548dd086742.png"  width="250" text-align= "center" >
</div>

   - Logging in as an existing user or signing up as a new user will bring you to the list of user-generated questions. I posted a question as each respective user by clicking the plus button, typing my question into the dialog that appears, and clicking submit. 

###Answer

<div id="wrapper" style="width:100%; text-align:center">
          <img src="https://cloud.githubusercontent.com/assets/12492121/9129897/3789ff3e-3cab-11e5-95e9-a87c505fc3e0.png"  width="250" text-align= "center" >
</div>

   - As Jane, I clicked on John's question that he asked, and was brought to the individual question view. Initially, there was not an answer. I pressed the plus button on the toolbar, an answer dialog appeared, I typed my answer, and clicked submit. Next, I logged out, signed in as John, viewed Jane's answer to his question, and up voted it to 5 points. Lastly, I answered Jane's question as John (not shown in my screenshots). 

###Profile

<div id="wrapper" style="width:100%; text-align:center">
          <img src="https://cloud.githubusercontent.com/assets/12492121/9129903/40e75838-3cab-11e5-8172-2b723d965553.png"  width="250" text-align= "center" >
</div>

   - As John, I clicked on his name in the list of questions. His profile appeared. I edited his profile description, but did not upload a picture. Then, I clicked on Jane's name seeing a read-only version of her empty profile. After that, I logged in as Jane, edited her profile, saved it, and viewed John's read-only version of his new profile.

##Conclusion

I liked that I was able to use Parse an MBaaS. If I have I had to create my own backend to house my data, I know that I would have had a very difficult time doing so, and would have spent much more than necessary on this project. I am glad that everything I implemented worked as described. If I had to do things differently, I would have included background pictures for the login and signup screens instead of using solid colors, and  included pictures next to each user's username.