---
layout: project
type: project
image: img/alien-invaders/Alien Invaders Photo.png
title: "Alien Invaders Game"
date: December 2021
published: true
labels:
  - Python
  - Game Development
summary: "For my Intro to Computing with Python course, my partner and I developed code in Python to create a game similar to the classic game 'Space Invaders.'"
---


https://github.com/jennjkim/jennjkim.github.io/assets/94199268/6e59e6b9-20a9-4690-803b-31a744fbe919




Alien Invaders is a game that pays tribute to "Space Invaders." My partner and I developed code in Python and used Atom editor to implement core game development ideas. We followed the model-view-controller (MVC) pattern and implemented various components of the game, including wave initialization, pausing, and end-game scenarios. 

We developed everything from creating the welcome screen and game features like aliens and ship animation to handling movement restrictions for the ship/player and features like firing rate. Additionally, we handled critical aspects like collision detection and interaction between different game elements. 

For example, here is some code for a function that checked for collisions between the aliens and bolts and deleted them from the screen as necessary:

```python
def _deleteAliensColl(self):
  """
  Checks if any alien in _aliens collided with any of the bolts in _bolts
  If yes, deletes both that bolt and that alien
  """
  for row in range(ALIEN_ROWS):
      for col in range(ALIENS_IN_ROW):
          alien = self._aliens[row][col]
          x = False
          y = None
          while x == False:
              for i in range(len(self._bolts)):
                  if alien is not None:
                      if alien.collides(self._bolts[i]) == True:
                          self._aliens[row][col] = None
                          y = i
                          x = True
              x = True
          if y is not None:
              del self._bolts[y]
```

Ultimately, completing this project helped me understand the significance of collaboration and design principles in complex coding projects. Throughout the process, I gained a greater ability to manage and organize code and practiced working with official class documentation and APIs. The project also served as a valuable opportunity to further develop my skills in Python and GUI programming. 
