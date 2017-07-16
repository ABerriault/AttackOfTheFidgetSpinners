# Attack Of The Fidget Spinners
---
A game written in Processing (Java IDE) for semmy.me/ide online editor. The game is written with numerous errors listed below to help reinforce camper understanding of:
- variables
- loops
- conditionals
- basic functions

The repository contains a completed version as well as the camper version which they should begin with. The errors are listed below:

Line 24: 
```python
int level = 0;                                                           // Level should be 0
```

Line 25: 
```python
int lives = 3;                                                           // Lives should be 3
```

Line 36: 
```python
size(600,600);                                                        // Screen must be set to 600x600
```

Line 55: 
```python
p.draw();                                                             // Display the player to the screen using its class method.
```

Line 62: 
```python
text("Lives: "+lives, 0, 0, 150, 50 );                              // Display the lives by adding +lives variable.
```


Line 94-96: 
```python
  } else if (key == 'd') {                                              // Add an else if statement to move the player right.
    p.moveRight();
  } else if (key == ' ') {
```


Created by [Andrew Berriault](https://github.com/ABerriault) for *McMaster Venture Engineering & Science*
