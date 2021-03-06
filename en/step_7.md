## Add some sound

Now it's time to add the scream to make the game a little scarier. In Python, just like the images, the sound needs to be loaded first before it can be used. Load the sound **before** the second image is displayed.

--- task ---
Lad the sound file as a variable called `scream` like this:

--- code ---
---
language: python
filename: scary_spot_the_difference.py
line_numbers: true
line_number_start: 
highlight_lines: 18
---
import pygame
from time import sleep
from random import randrange

pygame.init()

width = pygame.display.Info().current_w
height = pygame.display.Info().current_h

screen = pygame.display.set_mode((width, height))

difference = pygame.image.load('spot_the_diff.png')
difference = pygame.transform.scale(difference, (width, height))

zombie = pygame.image.load('scary_face.png')
zombie = pygame.transform.scale(zombie, (width, height))

scream = pygame.mixer.Sound("scream.wav")

screen.blit(difference, (0, 0))
pygame.display.update()

sleep(randrange(5,15))

screen.blit(zombie, (0,0))
pygame.display.update()

pygame.quit()
--- /code ---
--- /task ---

--- task ---
Then add a line of code to start playing the sound just before the second image is shown, and add another line to stop the sound just before Pygame quits.

--- code ---
---
language: python
filename: scary_spot_the_difference.py
line_numbers: true
line_number_start: 
highlight_lines: 18
---
import pygame
from time import sleep
from random import randrange

pygame.init()

width = pygame.display.Info().current_w
height = pygame.display.Info().current_h

screen = pygame.display.set_mode((width, height))

difference = pygame.image.load('spot_the_diff.png')
difference = pygame.transform.scale(difference, (width, height))

zombie = pygame.image.load('scary_face.png')
zombie = pygame.transform.scale(zombie, (width, height))

scream = pygame.mixer.Sound("scream.wav")

screen.blit(difference, (0, 0))
pygame.display.update()

sleep(randrange(5,15))

screen.blit(zombie, (0,0))

scream.play()

pygame.display.update()

scream.stop()

pygame.quit()
--- /code ---
--- /task ---

--- task ---
Save and run your code to see if it works. Then surprise your friends by telling them you have made a 'spot the difference' game for them to play.
--- /task ---
