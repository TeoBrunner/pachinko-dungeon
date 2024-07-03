# Pachinko Dungeon
## Synopsis
**Genre**: Roguelite Arcade
![dungeon scheme example](https://i.ibb.co/bRG2z6n/dungeon-scheme-example.png)

 - The main game loop consists of passing through a small dungeon consisting of a series of rooms in which the player can expect some challenge, some treasure, or other kind of activity. The room category is usually known in advance. Each room has one or more options for where to go next without the ability to go back. The dungeon ends with an especially difficult challenge with an especially valuable reward.
 - After completing a dungeon, the player is faced with a choice: take away the collected reward or go to a more difficult next dungeon in the hope of a better reward, but at the risk of losing the most of what he has collected.
 - Outside the dungeon, the player can spend accumulated resources to unlock new abilities/items or acquire new ones.
## Gameplay
The core gameplay is a sort of Rock, Paper, Scissors game, but the action selection is done by playing Pachinko.
![core gameplay example](https://i.ibb.co/zPyJNmn/core-gameplay-example.png)  
- ***Player's*** encounter with ***Enemy*** consists of ***Rounds***.
- Each ***Rounds***, ***Player*** and ***Enemy*** decide how to ***Act***: ***Tricky***, ***Quickly*** or ***Carefully***. 
 - ***Tricky*** beats ***Quickly***, ***Quickly*** beats ***Carefully*** and ***Carefully*** beats ***Tricky***.
 - A competition of identical ***Acts*** is counted as a draw.



## Systems & mechaninc
### Pachinko
![core gameplay example](https://i.ibb.co/zPyJNmn/core-gameplay-example.png)
- ***Player*** performs ***Act*** by distributing his ***Marbles*** between ***Holes***.

> To do this, ***Player*** can move ***Marble*** ***Source*** horizontally along the top edge of the playing field. ***Marbles*** fall down, colliding with obstacles. When ***Marble*** hits ***Hole*** , it disappears and is counted as a point for ***Act*** corresponding to ***Hole***.

- ***Enemy*** distributes his ***Marbles*** randomly, depending on the predetermined distribution. 

> So, for example, each ***Marble*** of a sneaky goblin have a chance of
> getting into ***Tricky***, ***Quickly*** or ***Carefully*** ***Holes*** around 50/40/10, and for a wise wizard it is 25/5/70.

## Visual
The intended visual style of the game is cartoonish, colorful, and cheerful.
### Referrences
![Kennney's Rolling Ball Assets](https://kenney.nl/media/pages/assets/rolling-ball-assets/8985e8ce1f-1677495687/sample.png)
![Good Knight Story](https://androidik.net/uploads/posts/2022-12/1671683074_img2.jpg)![Dungeon Crawlers canceled cartoon](https://i.ibb.co/hVB3KLB/Screenshot-2024-07-03-210940.png)![Postknight 2](https://assets.nst.com.my/images/articles/mgo_113d.jpg_1520822855.jpg)
