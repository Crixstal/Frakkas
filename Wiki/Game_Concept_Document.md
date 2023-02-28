### **Warning**  
  This Game concept document has been written at the beginning of the project. The result is almost as excepted, but there are some differences. Just remember that this document is an old pitch of Frakkarena.   

## Summary
1. [Gameplay](#gameplay) 
1. [Scene](#scene)   
2. [Enemies](#enemies)  
3. [Player](#player)  
4. [Score](#score)  
5. [Visual effects](#visual-effects)  
1. [Audio](#audio)
6. [Inspirations](#inspirations)


## Gameplay

**3C:**  
> - The character is a warrior that fights with a sword.
> - The view is made with a "top-down" camera which is far above the player. The camera cannot rotate. We can clearly see the player's surroundings. Moreover, the camera is not orthogonally facing down, it is a little tilted in order to see the relief of the ground.
> - The player can move in every direction, attack, dodge/dash, and pause the game.

The game genre is a **Survival - Beat'em up**. The goal is to get the highest score, teleporting from one arena to another. The player has to survive 2'30'' in each arena, fighting a bunch of enemies spawning without interruption at the edge of the arena.  
When the time is up, a portal appears and allows the player to get to the next level, they have 15'' to reach the portal.  

## Scene

The middle-sized arenas are square-shaped. There are no holes or apertures that let the player escape but there are boxes, and platforms to make the arena look like a labyrinth. The player would be able to climb on the platforms with stairs and would also be able to jump off them to reach the ground. The enemies would not jump.  

The camera is oriented non-orthogonally not to film the scene as a square but as a diamond. The 2 walls facing the camera, those in the back, are visible and tall whereas the 2 closest walls are either transparent or invisible.  
<img src="https://cdn.discordapp.com/attachments/956569497635000340/956570158191771748/unknown.png" width=50% height=50%><img src="https://cdn.discordapp.com/attachments/956569497635000340/956570492763009024/unknown.png" width=50% height=50%>

The portal appears at a given location in the arena. There are no signs to show where it is located, if the player does not know the arena, they will have to dash in order to spot it quickly. The portal is not hidden but can be placed on the high grounds or the platforms.  

## Enemies

The enemies are regularly, uninterruptedly, and randomly spawned at the edge of the arena. Their behavior is to move toward the player as fast as possible, not regarding their current position. Once close to the player, they wait a random amount of time before attacking.  
If the enemies are stacked around the player, they would either find a way to reach them or wait until they can finally hit them.  

There are 2 types of enemies, each of them has its own attacking style:  
> - ***Claw***, instant attack easy to dodge without dashing (the attack range is quite small) and a rather small amount of damage dealt.  
> - ***Mace***, heavy and slow attack, hard to dodge without dashing (the attack range is quite wide), the attack is similar to an ***AoE*** ([1](#AoE))   

When changing arena, accessing the next level, the enemies will have one of their statistics (see below) upgraded:
> - health
> - damage
> - move speed
> - attack speed _(charging time before actually throwing the attack)_  

These statistics are upgradable 5 times maximum each. The upgrade order is random.  

The enemies stop moving when they are hit non-lethally. When dying, *ragdoll* ([2](#Ragdoll)) activates and their body reacts to every other entity. The ragdoll body lasts for 5''. A killed enemy can drop a **health item** that heals 5% of players' max life.  

## Player 
  
The player possesses health, they cannot be killed in one hit. The first step would be to display the player's health as a health bar in the user interface, but we would like the health information to be the screen contour more or less red, according to the remaining health, just like some FPS. The actual player would feel oppressed.  

The player can move in every direction. Rotations and U-turns are instant.  

The player can dash in their movement direction. This dash would be useful to dodge an attack or to move very quickly at a certain distance to get out of enemy attack range. After dashing, the player cannot dash again until 0.5''. The dash allows the player to stay at altitude if so. They can then jump gaps to access usually inaccessible platforms. They cannot attack and dash at the same time.  

The player can attack non-stop. They only have one attack input but can have 2 different attack style:   
> - **swing right**
> - **3 hits combo** : swing right, swing left, swing down *AoE* ([1](#AoE))  

This combo is performed without changing direction. It allows you to chain 3 quick attacks, however, the player will be slowed down a bit at the end of the third hit. The player cannot move during an attack, however, they are very fast so the player does not feel blocked.
If the player presses dodge while attacking, it will be executed as soon as the attack is complete. If an attack is in progress, it will be stopped. The third hit of the combo prevents the player from dodging for 0.5''.

The player can stop the game at any time from the pause menu. In this case, they will be eliminated immediately, and they will follow the same ending as a Game Over.
Their game is over when:
> - The player has no more health points remaining.  
> - The player does not reach the portal in the given time.  

The player's death will trigger an animation or the ragdoll. Regardless of the endgame reason, the death animation will be the same. The collisions between the player's body and the enemies are deactivated.  

## Score  

Each kind of enemy bring a specific amount of point :   
> - ennemi '_Claw_' = 10 pts  
> - ennemi '_Mace_' = 20 pts    

Killing enemies in chain grants a point multiplier _(combo)_. This multiplier will increase the points given by defeated enemies before adding it to the score. The multiplier increases by 1 every 5 enemies defeated, its maximum is 8. If no enemies are eliminated for 3 seconds or if the player receives damage, the multiplier drops back to 1.
The score is only displayed at Game Over, and it is only the total points accumulated. A grade (C, B, A, S) will be assigned to the player based on the score and the number of arenas the player has survived.
_Example:_  
> - _200 points and 1 arena => B_  
> - _200 points and 5 arena => C_  
> - _1000 points and 1 arena => S_  

## Visual effects  

Here is a set of visual effects ideas that will be used to energize the action of the game.
> - Transparent trail that follows the movement of a swing.
> - Particles sphere for the third combo attack.
> - Blood/spark explosion on contact with enemies.
> - Dodging leaves a large trail or several fine trails.
> - Enemies and players flash red when hit.
> - The outlines of the screen are more red and opaque when the player takes damage.
> - Health items and portals have flying particles around/above them.
> - An exclamation point appears above the enemies that will attack.
> - The score is displayed above enemies for 0.5'' when they are defeated. The multiplier is directly applied.
> - The multiplier grows according to its value, perhaps with a shake or a particle system that forms a flame behind.
> - The timer changes color when the portal appears.

## Audio  

Audio is not an important element of the game, the minimum sound would be the following list:
> - Sound when pressing a menu button.
> - Sound when the player swings aiming at no one.
> - Sound when the player hits an enemy.
> - Sound when player dodges.
> - Continuous music.
> - Sample when the player loses.
> - Sound when an enemy is killed.

To have more epic feelings, here is what we could add:
> - A sound with increasing pitch as the multiplier increases.
> - Enemies' screams would be heard more or less loudly depending on the distance.
> - Special sound for the third combo attack.

## Inspirations  
  
**Hades** _(Supergiant Games)_

**Warframe** _(Digital Extremes)_ **Sanctuary Onslaught** mission

**Lysfangha** - Team Bagarre

---

*1 - Area of Effect, a type of attack that hits all entities present in the affected area.* <a name="AoE"></a>

*2 - Ragdoll, means that the physics of an entity's body is removed, the body then begins to fall absurdly.* <a name="Ragdoll"></a>

[Head of page](#summary) - [Home](Home.md)
