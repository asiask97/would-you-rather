# **Would You Rather?**  - JavaScript, HTML and CSS on frontend and Flask and PostgreSQL on backend

<a href='https://asiask97.github.io/would-you-rather/'><img src='documentation/devices.png' alt='Main screen of the website'></a>

### [Live Webiste](https://asiask97.github.io/would-you-rather/)
### [Backend](https://github.com/asiask97/would-you-rather-backend)

<br/>

# Table of Contents 
* [Introduction](#introduction)
* [Features](#features)
* [UX](#ux)
* [Testing](#testing)
* [User Stories](#user-stories)
* [Credits](#credits)
* [Deployment](#deployment)
* [Backend](#backend)

<br/>

# Introduction  

Would You Rather is a small project which consists of two parts, frontend with vanilla JavaScript and backend made with Flask and PostgreSQL database.
<br/>  

The whole point of the game is to ask the users to answer a set of questions and display all their results in the form of a pie chart. The purpose of this project is to see what another anonymous user would rather choose. The user gets an option of two choices and must pick the option that they would prefer more, users choice is saved in a database for each answer and then all results are displayed on a chart for the user to see. It's a fun and lighthearted game to kill some time and have a laugh.  

<img src='documentation/flow.gif' alt='flow of webiste on mobile screen'>
<br/> 

**Time frame to finish this project was about 20-25 hours.** 


<br/> 
<br/> 
 
# Features 

The whole front end of the website consists of four containers that are animated to go in and out depending on the current need. The game starts with a 'start' container which invites the user to play the game. Once the user decides to join, the screen is transitioned to the 'game' window which displays the current question. On the game screen the user gets two very interesting choices to pick from, once the user makes up their mind, they are moved to the results screen where all results of all players are displayed on a pie chart.  


## Start Window  
 
Start page gives a brief explanation of what the user is about to experience. It tells the user what the game is about in a lighthearted way. Once the user decides to play the game they are moved to the 'game' screen. The button on this page on hover shows hidden text, there is an event listener added to this button that fetches all the questions from the database, if a user has slower internet a load spinner is displayed.  

<img src='documentation/start.png' alt='start game section'>

## Game Window 

Here the user gets an especially important question - 'Would you rather?' and a pair of buttons which contain the answers. Users are asked to choose the one that they think is the preferred option. On hover each button displays different fun text as shown in the picture below. Once the users clicks on one of the given options a result is posted to database which increases the overall count for that option. 

<img src='documentation/game.png' alt='game section'>

## Results Window 

On the Results window we can see a pie chart which displays exact results fetched from the database. Below the pie chart there is a section with the same results but displayed as a percentage. There the user is also reminded of the two questions and how they are linked with colors on the pie chart. When user is done analyzing the results, they can continue the game using the button at the bottom of the screen.  

<img src='documentation/results.png' alt='results section'>

## End Window 
On the very last slide in screen a user has an option to play again. If the button is clicked the window will be refreshed and the game will start up from the very beginning.  

<img src='documentation/end.png' alt='end section'>

# UX
## Wire Frames
I have planned out how the website will look using Balsamiq Wireframes.
- Home screen / Start Game 
<img src='documentation/wire_home_decktop.png' alt='wire desktop home section'>

- Game screen 
<img src='documentation/wire_game_desktop.png' alt='wire desktop game section'>

- Statistics screen 
<img src='documentation/wire_stats_desktop.png' alt='wire desktop stats section'>

- Mobile screen 
<img src='documentation/wire_mobile.png' alt='wire desktop stats section'>

## Animations and Effects
<img src='documentation/button-hover.jpg' alt='game section'>
- I have made sure to add some UX features that help user enjoy the game little bit more. As shown in the image above I have added fun hover effect on some buttons that gives some comedic relief in the game.

- I have also added animation effect when each section is shown to add some movement and interaction with the user. The user can see each section slide in and out smoothly after each press of a button.


# Testing
Throughout the project I have kept in mind the performance and best practices. I made sure that my code passes all relevant tests like Validator tests shown below. I have also made sure that the website is fully responsive with the help of Chrome developer tools. 


List of devices which the website was tested on: 
- IPhone SE
- IPhone XR
- IPhone 12 Pro
- Pixel 5
- Samsung Galaxy S8+
- Samsung Galaxy S20 Ultra
- Ipad Air
- Ipad Pro 2020
- Ipad Mini
- Surface Pro 7
- Surface Duo
- Galaxy Fold
- Samsung Galaxy A51/71
- Nest Hub Max

I have also made sure that the website works across a range of browsers like Chrome, Opera, Firefox and Brave.

Each button on the website was tested to make sure it works correctly and that all links are working and are fully functional. Tests were carried out to make sure that form is validating inputs correctly as previously discussed above. 

## Manual Testing
 - Tested the start game button to:
    1. Make sure it shows the game screen.
    1. Make sure it fetches the questions from API 
    1. Make sure that loader is shown while the API data is being fetched.

<br/>

- Tested each option button on game screen to:
    1. Make sure correct option is send to database.
    1. Make sure statistic screen will be shown
    1. Make sure there isn't any surprise errors or bugs that I didn't see.

<br/>

- Tested the next question button on statistics screen to:
    1. Make sure that next question will appear.
    1. Make sure that the question displayed has correct set of options to choose. 

<br/>

- Checked that each question displayed is only shown to user once.
- Checked that statistics shown are exactly the same as the ones in the database.
- Checked that button at the end of the game will take the user to the start by refreshing the browser window.

##  Validator Testing
<br/>

- # [HTML Validator - passed with no issues](https://validator.w3.org/nu/?doc=https%3A%2F%2Fasiask97.github.io%2Fwould-you-rather%2F)
- # [CSS Validator - passed with no issues](https://jigsaw.w3.org/css-validator/validator?uri=https%3A%2F%2Fasiask97.github.io%2Fwould-you-rather%2F&profile=css3svg&usermedium=all&warning=1&vextwarning=&lang=en)
- # JSHint Validator shown the fallowing warnings <img src='documentation/jshint.png' alt='lighthouse on mobile'>
- Warnings generated by JSHint are discussed in the [Issues & Fixes](#issues-and-fixes) section below.  

<br/>

##  Lighthouse Testing

### Desktop 
<img src='documentation/lighthouseDesk.png' alt='lighthouse on desktop'>

### Mobile 
<img src='documentation/lighthouseMobile.png' alt='lighthouse on mobile'>

## Issues and Fixes 
During the development of the project, I have come across several issues.  

- First issue was with chartJS library. The error I was getting when trying to update the chart for each question was caused by a function creating an instance of a cart each time it was called. To fix this issue I decided to use global variable for chart object.  

- Another issue was related to event listeners attached to buttons. Each time a button was clicked a new instance of a function was called multiple times. To fix this problem I have decided to remove event listeners after a click was made so the same button wont fire more than once.  

- I had to wait for data to finish fetching before continuing the code as the questions array was returning empty. This issue was easy to fix with async and await.  

- Not so much an issue but an improvement was creation of helper functions which are called to do one specific thing like start animation or fetch specific data.

- During my meeting with mentor I have been informed to have my commits more descriptive. This isn't something I can go back and change but this is something Im now aware off and will be improving on going forwards.

###  Disccusing Warnigs From JSHint

- The first thing to address is the ‘async functions is only available in ES8 (use 'esversion: 8')’ warning. This warning in my case is to be ignored as ES8 has an extremely high support (96.25%) across most browsers so there should not be an issue unless someone is using a very outdated browser. Asnyc function are widely used and one of the most popular ways to fetch data with JavaScript. Another way would be to use Promises but I have decided to use the most recent solution.  
 <img src='documentation/async.png' alt='lighthouse on mobile'>
  
- The second warning is ‘One undefined variable’ on line 99 named ‘Chart’. This warning shows up because I'm using an object from the ChartJS library which is imported though html header. JSHint does not recognize it so it shows up as a warning. 

# User Stories
### Some of user stories that got completed 

| #           | User Story      
| ----------- | ------------- 
| 1           | As a user I want to be able to clearly see all questions and answers. 
| 2           | As a user I want to be able to have a clear path of the game and not be confused about what to do. 
| 3           | As a user I want to know how other users answered the questions. 
| 4           | As a user I want to be able to start the game when I want to.         
| 5           | As a user I want to enjoy the modern look of a modern app.          
| 6           | As a user I want to play the game on all screen sizes.          
| 7           | As a user I want to know when I have reached the end of all the questions.          
| 8           | As a user I want to see results in a readable and clear to understand way.          
| 9           | As a user I want to see some animation or movement, so the game has a flow throughout.           
| 10          | As a user I want to be able to see when the questions are loading if I have slower internet.    

<br/>

### Some of user stories are planned for next sprint

| #           | User Story      
| ----------- | ------------- 
| 1           | As a user I want to be able to go back to the question I left the game on.   
| 2           | As a user I want to share my results on social media.
| 3           | As a user I want to see what my friend and only my friends answered in each question. 
| 4           | As a user I want to have sections or topics of questions.       

<br/>

# Credits

I used the fallowing websites and libraries throughout the project: 

- [Google fonts were used to pick out fonts relevant to the design.](https://fonts.google.com/)
- [Images and videos from pexels.com.](https://www.pexels.com/)
- [Loader used to indicate detching data.](https://loading.io/css/)
- [Inspiration for buttons was taken from this website - Button 57.](https://loading.io/css/)
- [ChartJS library.](https://www.chartjs.org/)
- [Insparation for would you rather questions.](https://www.signupgenius.com/groups/would-you-rather.cfm)
- [Insparation for would you rather questions.](https://www.quizbreaker.com/would-you-rather#difficult-would-you-rather-questions)
- [Insparation for would you rather questions.](https://woulduratherquestions.com/deep-would-you-rather-questions/)
- [Insparation for would you rather questions.](https://www.becomemorecompelling.com/blog/would-you-rather-questions)
- [Insparation for would you rather questions.](https://www.thecoolist.com/would-you-rather-questions/#20_Deep_Would_You_Rather_Questions)
# Deployment
To create A repository, I: 

- Loged into my account 
- Pressed plus on the left side 
- Clicked New repository button 
- Added a name of my repository 
- Made my repository public 
- Added a readme 
- Clicked create repository button 

 
Then I followed the commands that were given to me to make my first commit though CLI on Visual Studio Code. 

<br/>
To deploy this project, I have decided to use GitHub pages as it is only a sample project not a official website. 

To deploy I have made a Repo on GitHub and pushed initial code. Then I have: 

- Navigated to GitHub Repo with current project. 
- Clicked Settings 
- Navigate to Pages tab 
- Choose branch correct branch 
- Press Save button 

The website is now live. 

# Backend
Backend is currently deployed on Heroku with postgres database. 
- [More on backend can be found here.](https://github.com/asiask97/would-you-rather-backend)