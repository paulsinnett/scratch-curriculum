Code Club : How to make a river crossing game project By

Emily Harding 

Introduction: In this project we are going to make a game similar to the classic game 

Frogger, your character will jump onto a series of logs to win. 

Step 1 : Create your character and logs

1. Start a new project

2.  First delete the Scratch cat , and import / draw a character .  

3.  Import / draw your own background. This will be the background which your 
    character will fall into if they miss the log. 

4. Draw 6 rectangles, these will be the ‘logs’ which your character will be hopping on. 
   Make one log then duplicate the rectangle's 5 times. 
 

Step 2 : Making the frog move 

1. We want the character to be controlled by the arrow keys to move. Use this 
   script to make the character move to the left: 

When [left arrow v] key pressed 
Change x by (-10)

2. Now you can use this script to make the character move to the right: 

When [right arrow v] key pressed 
Change x by (10)

3. We also want the character to jump forward,onto the logs, so use this script:

When[space v] key pressed 
play sound [Pop 1 v]
move (75) steps 

You can use any sound effect when your character jumps!

4. Finally use this script so your character can move backwards: 

When [down arrow v]key pressed 
if <not <touching color [#00ff00] > > then
move (-75) steps 

The green colour can be replaced with the colour floor your character starts the game on. 

Test your project! Does your character move forward , back , left and right?
