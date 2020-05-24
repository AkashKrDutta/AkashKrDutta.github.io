---
layout: post
title: HTML 5 Game Dev
comments: true
tags:
  - html5
  - gamedev
categories:
  - dev

---
## HTML5 Game Development  
For all those gaming nerds out there, there isn’t a better way to develop your gaming skills but to start from scratch of how a game works and to build your own one!
HTML 5 provides rich environment to create your games using Javascript and the html5 canvas object.  
<!-- more -->
<br/>

### PRE-REQUISITES
Well, all you need is to know the basics of Html and javascript. And of course, a little bit of enthu in the pot is forever welcomed!  :)  
<br/>

### WHY NOT OTHER GAME-ENGINES ? 
We have hundreds of cool game engines in the market, to name few unity, unreal engine, cryengine, source 2 etc. But here we focus on learning things from the scratch, in engines like these things are more drag and drop and the essence of how things work from the basic fails to deliver. In this article, we discuss things from the very basic!  
<br/>

### GAME CANVAS AND GAME COMPONENTS
Without much ado, we talk about the canvas object in the html 5 that offers to us the workplace for doing all our cool gaming stuff. To note is that it is a container to hold the graphics content and nothing more. Everything that needs to be done must be defined beforehand unlike the game engines like unity which have predefined objects like planes, spheres etc.  
<br/>

### Game Components
We can draw rectangles, circles, lines using the 2D context of canvas object ( in layman's term - drawing in the canvas holder by using its 2 Dimensional object ).We can provide colors to fill, or use gradient colors, or even load images to make animations in the 2d context of canvas object.
{% highlight js %}
var canvas=Document.createElement("canvas");  
document.appendChild(canvas);  
var context=canvas.getContext("2D");  
context.fillStyle="red";  
context.fillRect(10,20,30,40);
{% endhighlight %}
This creates a color filled red rectangle in the canvas at (10,20) coordinates of 30px as width and 40px as height.  
<br/>

### GAME COMPONENTS AND THEIR MOVEMENT 
The importance of these objects is that they can be moved inside the canvas by redrawing them to different positions, this being done every fixed time interval (frame rate). The <code>addEventListener</code> captures the input and calls a function (callMe as in the code shown) at fixed intervals to make the game component move. The function callMe then calls another function that takes the current position as arguments and redraws it according to the key pressed, this being done at fixed interval of time, creating an effect of movement. The position can be incremented each time adding a constant or a uniformly increasing mathematical function to make the component move uniformly or accelerate respectively.
The movement is triggered by adding event handlers through javascript, like “keydown” , “keyup” for keyboard keys, which can be recognized using the keyCode attribute of the event argument of event -handler function call.
{% highlight javascript %}
window.addEventListener('keydown', function (e) {  
  myGameArea.key = e.keyCode;
  //for calling a function callMe at 50 every millisecond ( or   
  //better say 20 frames per second)  
  setInterval(callMe,50);
 })
{% endhighlight %}
Hence by knowing which key is pressed, we can call the required functions for action to be taken.  
<br/>

### GAME OBSTACLES AND SCORE 
Like other game components game obstacles are also game components but being generated at random coordinates of random shape, the code of which is much the same and I leave it to you :) .  
The score in most of the cases is decided by certain collision events or by the count of the current frame from the beginning of the game.
It's very easy to ascertain the collision between objects exploiting the boundary coordinates. The current frame can be known by ensuring a  counter that is incremented for the function that is called per frame. I leave the job for you to google out the way to write text in canvas element to display the score when needed.  
<br/>

### ALMOST THERE !
We have known everything to create our first simple html5 game with our own game arena and game components, game obstacles and score to compete!  
<br/>

### LONELY WITHOUT SOUNDS ?
Well everyone loves the charm when there’s music in the air! Luckily we can have it too in case of html5 “audio” object. Sounds can be added when a collision occurs or when a key is pressed by calling the function for sound whenever the event is captured inside the functions that we have already seen. Not going into much detail, we can add sound using the following code link, which I leave you to dissect.  
<br/>

### LINKS AND FURTHER READING

* [adding sounds](http://home.iitk.ac.in/~akashdut/sounddev.txt)
* [udacity course on html5 game dev](https://www.udacity.com/course/html5-game-development--cs255)
* [udacity course on html5 canvas element](https://www.udacity.com/course/html5-canvas--ud292)
* [w3schools tutorial for html game](http://www.w3schools.com/games/default.asp)<br>

