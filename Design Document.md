
# Pachinko Dungeon
## Synopsis
**Genre**: Roguelite Arcade

- The core gameplay is a sort of Rock, Paper, Scissors game, but the action selection is done by playing Pachinko.
 - The main game loop consists of passing through a small dungeon consisting of a series of rooms in which the player can expect some challenge, some treasure, or other kind of activity.
 - Outside the dungeon, the player can spend accumulated resources to unlock new abilities/items or acquire new ones.
## Gameplay
### Before the descent
>TODO
### Dungeon map
![dungeon scheme example](https://i.ibb.co/yqg0Yhm/dungeon-map-example.png) 
- The game session begins with the ***Player*** descending into the ***Dungeon*** and seeing its ***Map***. 
- The ***Dungeon*** is a set of ***Rooms*** arranged in a graph.
- All the ***Rooms*** in the ***Dungeon*** fall into one of four categories: ***Encounter***, ***Rest***, ***Treasure***, or ***Special Event***. 
- After completing the ***Room***, the ***Player*** can choose where to proceed next.
- At the end of the ***Dungeon*** are three ***Rooms*** of increased difficulty. Winning one of them means completing the ***Dungeon*** descending.
- After completing the ***Dungeon*** descending, the ***Player*** has a choice: safely leave the ***Dungeon*** with all the ***Items*** or risk going deeper into the next ***Dungeon***.
- All ***Items*** taken out of the ***Dungeon*** are converted into ***Money*** for permanent character ***Upgrades***.
![room examples](https://i.ibb.co/Gn4KHsM/room-examples.png)
### Encounter
- The ***Player's*** encounter with the ***Enemy*** consists of ***Rounds***.
	- Each ***Rounds***, the ***Player*** and the ***Enemy*** decide how to ***Act***: ***Tricky***, ***Quickly*** or ***Carefully***. 
	 - ***Tricky*** beats ***Quickly***, ***Quickly*** beats ***Carefully*** and ***Carefully*** beats ***Tricky***.
	 - A competition of identical ***Acts*** is counted as a draw.
 - Between ***Rounds*** both sides has the opportunity to use their ***Items*** and ***Active Skills***

### Rest
- Upon reaching the ***Rest Room***, the ***Player*** is faced with a choice: 
	- To ***Rest*** quietly and restore ***Health***
	- Or to ***Rest*** actively and gain some ***Energy***.
### Treasure
- In the ***Treasure Room***, the ***Player*** is guaranteed to find one or more useful ***Items***.

### Special Event
- In some ***Rooms***, the ***Player*** may encounter a ***Dialogue***, ***Puzzle***, or other ***Situation*** with multiple possible answers. Each of the options may reward the player, punish them, or do nothing.

### Meta
- Between dungeon runs, the ***Player*** can spend ***Money*** to unlock ***Passive*** and ***Active*** character ***Skills***.


## Systems & mechaninc
### Safe Hub
>TODO
### Dungeon
![dungeon map example](https://i.ibb.co/yqg0Yhm/dungeon-map-example.png)
- A ***Dungeon*** is a graph-like network of ***Rooms***.
- Each ***Room*** presents the ***Player*** with a choice or challenge that can be solved by playing ***Pachinko***. It can be:
	- ***Encounter*** with an ***Enemy***.
	- Safe space with a couple of ***Rest*** options.
	- ***Treasure Room*** with a several ***Items***. 
	- Some kind of puzzle, dialogue, dilemma, etc. with several answer options.
- The ***Player*** must make this choice or pass this challenge for the ***Room*** to be considered ***Complete***.
- Once a ***Room*** is ***Completed***, the ***Player*** must choose where to go next:
	- To one of the ***Rooms*** below, which has a passage from the current one.
	- Safely leave the ***Dungeon*** with all the loot.
- At the beginning of the descent into the ***Dungeon***, the ***Player*** can choose which of the first three ***Rooms*** to enter.
- The final three ***Rooms*** contain either a particularly powerful ***Enemy*** or an ***Event*** with a particularly difficult choice.
- ***Completing*** the final ***Room*** means ***Completing*** the ***Dungeon***.
- Upon ***Completing*** a ***Dungeon***, the ***Player*** can safely leave it with all the ***Items*** or go down to the next one of increased difficulty.

### Pachinko
![room examples](https://i.ibb.co/6r73Xvt/room-examples.png)
- Each ***Rooms*** presents the player with a ***Choice***.
	- How to behave in battle
	- What precious item to take
	- How to answer the riddle.
	- etc.
- The ***Options*** are represented by ***Holes*** at the bottom of the playing field. 
- If the ***Choice*** implies only one ***Answer***, it is made by throwing more ***Marbles*** into that ***Option's Hole*** than into the others.
	- If several ***Answer Options*** score the same number of ***Marbles*** , the ***Choice*** is made of them randomly.
- Otherwise, each ***Answer Option*** is counted as many ***Points*** as the number of ***Marbles*** that fell into it's ***Hole***.
- The ***Player*** can influence the ***Choice*** of ***Option*** by moving the ***Marble's Source*** horizontally along the top edge of the playing field.
### Enemy Encounter
![enemy encounter example](https://i.ibb.co/cJJDMvx/encounter-example-long.png)
- At the beginning of each ***Round*** the ***Player*** and the ***Enemy*** can use their ***Items*** or ***Active Skills***
	- ***Items*** are limited and ***Active Skills*** require ***Energy*** to use.
- The ***Player*** and the ***Enemy*** must then decide how exactly to ***Act*** in this ***Round***:
	- ***Acting Tricky*** allows one to ***Attack*** the ***Quick*** opponent.
	- ***Acting Quick*** allows one to ***Attack*** the ***Careful*** opponent
	- ***Acting Careful*** allows one to ***Attack*** the ***Tricky*** opponent
- The ***Player*** performs ***Act*** by playing ***Pachinko***.
- The ***Enemy*** distributes his ***Marbles*** randomly, depending on the predetermined probability. 
	> So, for example, each ***Marble*** of a ***Sneaky Goblin*** have a chance of getting into ***Tricky***, ***Quick*** or ***Careful*** ***Holes*** around 50/40/10, and for a ***Wise Wizard*** it is 25/5/70.
	
- The ***Player*** and the ***Enemy*** contests in their ***Acts*** stepwise.
	- First, the ***Acts*** with the most ***Points*** of both are compared, then the second, then the least.
	- In a contest of different ***Acts*** one is considered as an ***Attacking*** and other as a ***Defending***. 
		 >The ***Defending*** side takes ***Damage*** equals to ***Attacking Points*** minus ***Defending Points*** if total is more than zero.
	- In a contest of same ***Acts*** the one with more points gets ***Energy*** in an amount of ***Their Points*** minus ***Opponent's Points***
- If Someone's ***Health*** reaches zero - they lose
- If no one loses, the next ***Round*** begins.
### Rest Room
![rest room example](https://i.ibb.co/FKzHN8j/rest-room-example-long.png)
- In the ***Rest Room***, the ***Player*** must ***Choose*** between ***Active***, ***Productive*** and ***Quiet*** rest.
	- The ***Choise*** is made by playing ***Pachinko***.
	- Each ***Point*** of ***Active Rest*** gives the ***Player Energy***.
 	- Each ***Point*** of ***Productive Rest*** increases the ***Level*** of the ***Item*** the ***Player*** can obtain. 	
	- Each ***Point*** of ***Quiet Rest*** restores the ***Player's Health***
### Taking an Item 
![item choosing example](https://i.ibb.co/KD5SJW5/item-selection-example-long.png)
- When defeating an ***Enemy*** or entering a ***Treasure Room***, the ***Player*** is faced with a ***Choice*** of ***Items*** as a reward.
	- The ***Choise*** is made by playing ***Pachinko***.
	- Each ***Hole*** represents one ***Item*** that the ***Player*** can obtain.
	- Every ***Point*** scored on an ***Item*** increases its ***Level***.
	- The ***Player*** obtains all ***Items*** that have scored more than zero ***Points***.
### Other choices
![special event example](https://i.ibb.co/024zZTt/special-event-example-long.png)
- In other ***Rooms***, the ***Player*** may encounter a riddle, puzzle, trap, dialogue, or other situation that requires making a ***Choice*** between several ***Options***.
	- The ***Choise*** is made by playing ***Pachinko***.
- The consequences of the choice depend on the situation. It can be:
	- Taking ***Damage***.
	- Restoring ***Health***
	- Gaining ***Energy***
	- Founding an ***Item***.
	- Nothing at all.


## Visual
The intended visual style of the game is cartoonish, colorful, and a bit parodic.
### Referrences
![Kennney's Rolling Ball Assets](https://kenney.nl/media/pages/assets/rolling-ball-assets/8985e8ce1f-1677495687/sample.png)

![Good Knight Story](https://androidik.net/uploads/posts/2022-12/1671683074_img2.jpg)

![Dungeon Crawlers canceled cartoon](https://i.ibb.co/hVB3KLB/Screenshot-2024-07-03-210940.png)

![Postknight 2](https://assets.nst.com.my/images/articles/mgo_113d.jpg_1520822855.jpg)
