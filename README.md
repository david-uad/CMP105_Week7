# CMP105_W7
CMP105 Lab 7 projects

Lab sheet notes:
Code 7_1 :

There was a missing semicolon at the end of the Enemy header file, which caused the Player class which inherited from Enemy to cause compile time errors.
I used the debug output and knowledge of correct syntax to go through first the player class, and then its includes until I found the syntax error.


Code 7_2:

Another syntax error, this time in the player header file. A colon was missing after the 'private' identifier on line 17. Again the IDE debug output was used,
and the error was quickly located within player.h. Also of use was the IDE suggestion dialogue which made identifying the error much easier. There is also a
large discrepancy between what the program is supposed to do and what it actually doe, based on the lab notes, but I will assume this is intentional as it is not 
a bug.


Code 7_3:

Here the error was occurring because inside the player class the pointer to the Bullet object was never made to point to a bullet object in memory, resulting
in a nullptr exception being thrown. It was solved by again reading through the debug output, but also some rubber duck debugging when it was not clear why the 
exception was occurring and so it would help to talk through the steps the program was making around manipulating the Bullet object.


Code 7_4:

The issue here was that when a bullet was spawned, a bullet object was created inside a function, and the address returned to the player's bullet pointer,
however the pointer would now point to empty memory as the bullet object is destroyed on exiting the function, creating a memory access violation error.
This was tricky to diagnose,  but was solved using a combination of the debug output, breakpoints, annd stepping through the code and watching the values
of objects such at the bullet pointer or the newBullet object as they were manipulated.


Code 7_5: What was wrong? How did you fix it? and cruically what tools and techniques did you use to find it?



Code 7_6:

The issue here was the use of <= operators instead of < operators when iterating through the array of Bits. This was found and solved using the debug out,
breakpoints and again stepping through and watching the value of the iterator i.


Code 7_7:

Here Gameobject go was declared twice, which clearly led to the issue which was that it was not drawn to the screen. Attempts to find the cause using 
breakpoints and watch variables were mostly fruitless, and so rubber duck debugging and walking through the code which initialised the Gameobject object 
was the eventual way to identify and solve the issue.

