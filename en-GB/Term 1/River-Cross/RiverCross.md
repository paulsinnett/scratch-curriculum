---
title: River Cross
level: Level 2
language: en-GB
stylesheet: scratch
embeds: "*.png"
materials: "*.sb2"
...

# Introduction {.intro}

In this project we are going to make a game similar to the classic game Frogger, your character will jump onto a series of logs to win. 

# **Step 1:** Create your character and logs {.activity}

## Activity Checklist { .check}

+ Start a new project
+ First delete the Scratch cat, and import / draw a character. If you want it to be a classic Frogger style game you can use a Frog. 
+ Import / draw your own background. This will be the background which your character will fall into if they miss the log. 
+ Draw 6 rectangles, these will be the ‘logs’ which your character will be hopping on. Make one log then duplicate the rectangle's 5 times. Give each log a name, Log 1, Log 2 etc.
 
# **Step 2:** Making the frog move {.activity}

+ We want the character to be controlled by the arrow keys to move. Use this script to make the character move to the left: 
```blocks
When [left arrow v] key pressed 
Change x by (-10)
```

+ Now you can use this script to make the character move to the right: 
```blocks
When [right arrow v] key pressed 
Change x by (10)
```
+ We also want the character to jump forward,onto the logs, so use this script:
```blocks
When[space v] key pressed 
play sound [Pop 1 v]
move (75) steps 
```
You can use any sound effect when your character jumps!

+ Finally use this script so your character can move backwards: 
```blocks
When [down arrow v]key pressed 
if <not <touching color [#00ff00] > > then
move (-75) steps 
```
The green colour can be replaced with the colour floor your character starts the game on. 

## Test Your Project { .flag}

__Click the green flag__, does your character move forward, back, left and right?

# **Step 3:** Create your background {.activity}

+ Our character need a background when they are jumping on the logs , start by using the paint fill tool to colour the whole background , you can use any colour you want. 
+ Use the rectangle shape tool, to draw the land your character, and fill the rectangle in. 
+ On your character script page, find the script that moves your character backwards, change the touching colour to the floor colour your character starts on. 
+ Lastly add some waves on to your background. 

# **Step 4:** Programming the logs 

+ Now we are going to programme the logs which your character will be hopping on to cross the river. On Log 1's script page make this script:
```blocks
when flag clicked  
go to x:(0)y:(-75)
repeat until < (x position) > (280) >
change  x  by(2)
end
forever
go to x:(-300)y:(-75)
repeat until< (x position) > (280) >
change  x  by (2)
```

+ Also make this script for Log 2 

## Test Your Project { .flag}

__Click the green flag__, does Log 1 and 2 both move in a 'right' direction?

# {.activity}

+ Now make this script for Logs 3 and 4 : 
```blocks
when flag clicked 
go to x:(132) y:(2)
repeat until < (x position) < [-280] >
change x by (-2)
end 
forever
go to x: (137) y:(2)
repeat until<(x position) < [-280] >
change x by (-2) 
```

Check that your logs 3 and 4 are moving in the left direction.

+ Finally make this script for logs 5 and 6:
```blocks
when flag clicked 
go to x:(15) y:(87)
repeat until < (x position) < [280] >
change x by (2)
end 
forever
go to x: (15) y:(87)
repeat until<(x position) < [280] >
change x by (2) 
```

# **Step 5:** Making a goal {.activity}
We want a goal for our character to reach after jumping on the series of logs, so we need to create a item / place for our character tio reach. You can create your own area / object for your character to reach or follow these instructions to make a lillypad. 

