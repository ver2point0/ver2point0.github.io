---
published: true
title: Project Mini Notes case study
layout: post
tags: [android, project, notes]
---
<h2>Summary</h2>
Mini Notes is a simple note taking application that implements Google's Material Design visual language.

<h2>Explanation</h2>
This project's data management layer was created using an SQL live database. A content provider was was used to create, read, update, and delete notes. Additionally, a loader managed database calls asynchronously.

I made this project as part of my Android development apprenticeship to increase my competency with building applications from start to finish. 

<h2>Problem</h2>
The following are the requirements for this application:

1. Create new notes.

2. Edit existing notes.

3. Delete existing notes.

4. Save data persistently. 

5. Implement Material Design.

6. Implement a floating action button.

<h2>Solution</h2>

1. Create new notes.

   To create new notes, I made a main activity screen where users can perform this action in one of two ways: clicking the floating action button or creating sample data via the action bar.

2. Edit existing notes.

   I made an editor activity screen for users to edit notes. Creating a new note immediately brings up the editor activity. Existing notes need to clicked to edit them.

3. Delete existing notes.

   Clicking an existing note brings the user to the editor activity where it can be deleted. A trash can icon is only available to the user in this view. Pressing the icon deletes the note, deleting the current note text and going back to main activity deletes the note, or selecting "Delete all notes" from the action bar deletes all of the notes in the list. 

4. Save data persistently. 

   To save data persistently, I created a class that extended SQLiteOpenHelper. This helper class allowed me to define my database and manage connections to it.

5. Implement Material Design.

   Giving my application its flat, bold appearance was easy with [Material Palette](https://www.materialpalette.com). This site instructs users to pick two colors. The first color is the primary, and the second color is the accent. The other six colors that it gives you are primary dark, primary light, text/icons, primary text, secondary text, and a divider. 

6. Implement a floating action button.

   To implement the floating action button in my application, I had to add Google's design support library to my project (`com.android.support:design:22.2.0`). From there, I called `android.support.design.widget.FloatingActionButton` in my main XML file.

<h2>Results</h2>
Please, see my Github account to reference [Mini Notes](https://github.com/ver2point0/Mini-Notes).

<h3>Main</h3>

<div id="wrapper" style="width:100%; text-align:center">
          <img src="https://cloud.githubusercontent.com/assets/12492121/9154286/6df7c19a-3e55-11e5-809b-39552fa1a1be.png"  width="250" text-align= "center" >
</div>

   - To test my application, I created three notes using the floating action button: *Monthly bills*, *Class schedule*, and *Shopping list*.

<h3>New note</h3>

<div id="wrapper" style="width:100%; text-align:center">
          <img src="https://cloud.githubusercontent.com/assets/12492121/9154287/715a38a4-3e55-11e5-8ff7-f03bb844cfc6.png"  width="250" text-align= "center" >
</div>

   - In the editor activity, I typed the names of the notes above to serve as titles. These names would help me remember what contents are contained in each note. 

<h3>Notes list</h3>

<div id="wrapper" style="width:100%; text-align:center">
          <img src="https://cloud.githubusercontent.com/assets/12492121/9154288/73feb18e-3e55-11e5-9151-1279841c060c.png"  width="250" text-align= "center" >
</div>

   - Now that I have three notes in my notes list, I can delete them three different ways. First, I clicked on *Monthly bills*, and deleted it using the trash icon. Next, I selected *Class schedule*, backspaced until the text area was empty, and went back to my main activity successfully deleting this note. Lastly, I chose "Delete all notes" from the action bar to delete the *Shopping list* note.

<h2>Conclusion</h2>

I enjoyed making this application. This is something I would personally use because it has a simple interface and very few actions.