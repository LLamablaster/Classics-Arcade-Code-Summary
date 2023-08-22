# Classics-Arcade-Code-Summary
Code summary for 2 week live game dev project, where I recreated 1942.
# 1942 Scenes
I created 3 separate scenes for my game: a splash title screen, a main level scene, and a game over scene.

Transitioning between the scenes was completed using a SceneLoader prefab.

![](https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExNmk3MWV1NzExeHczcWg0bzN5Ym9rbDI5ejc0bTk1cGhyMnhpcjhzZCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/7cSlb1sBblBAtHhZaj/giphy.gif)

# 1942 Player Movement
In the original arcade game, the player can move their plane around the screen, fire their machine gun, and perform a loop-the-loop maneuver to avoid enemy fire. I made sure to implement all of these controls in my recreation. I decided to remove the limited stock of loop-the-loops present in the original, since there was enough opportunity cost baked into the limited movement during the loop.

![](https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExN3V3a2U1Njd6YTRyZDZ0YTQ2MzZyeHZ0dTdvaWJ2OWJoMnV2Z3djbiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/JQVQ9iVMcKl7qZNMTC/giphy.gif)

A game referee object keeps track of how many bullets the player has in the air, ensuring that th eplayer can only fire 3 volleys at a time, just like the original. Bullets are culled by a death box surrounding the play area.

# 1942 Enemy Behavior
I implemented various enemy types that pull u-turns, turn varying degrees, or just fly straight. I also created spawners that generate groups of enemies with coordinated movement. They all can shoot bullets at the player.

As enemies are killed and the player's score increases, enemies will spawn more frequently and in larger groups. This is also controlled by the game referee, and tracked by the 'intensity' element of the UI.

![](https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExZTk2bzdmYTQxeTVyNm05dXBxZG5qZjFtcWQ0Zm9scHVveDhlNW9mdSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/6uHFjL0vWc9ODbHTbs/giphy.gif)

# 1942 Player Behavior
Enemies and their bullets will cause the player to die and respawn, losing a life. When they come back they have a small window of invulnerability to get their bearings.

![]([https://giphy.com/gifs/zcicvNIRaJOUf9fqBb](https://media3.giphy.com/media/kwiFs7QSFx92M5gxjI/giphy.gif))

Large enemies drop powerups, which grant the player more bullets per volley. A second powerup spawns two flanking helicopters, which can protect the player and fire bullets.

![](https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExMnhxZmE2enA5MnUxbzdvb2ViaG11Y202N2o2dGpxZ2d6bm8wNWdxdSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/ZNZX1KEQaEHKi6RQL2/giphy.gif)

Extra bullets are created by adding additional game objects to the player's list of hardpoints, which each spawn a bullet whenever the player fires.

# Extra Effects
I also had time to add some sound effects, background music, and particle emitters for shooting, crashes, and menu interactions in the game. The whole game can be played on my portfolio website at U R L
