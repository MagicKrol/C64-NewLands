# C64 New Lands  
New Lands v.0.4 (BETA)
  
New Lands is a game developed for Commodore 64.   
The game combines elements of strategy and simple economy in the pirate styled genre.   
  
Please notice, that this is a beta version of the game. Most of the game elements are already implemented, but it still might be a bit buggy and imbalanced (to hard, or to easy).
  
You can contact me via email mzkrol@gmail.com  

<img width="891" alt="newlands5" src="https://user-images.githubusercontent.com/22881963/196254788-9b58cc5f-0bd8-4dd7-9b4a-7c873ee4ac91.png">
<img width="851" alt="newlands1" src="https://user-images.githubusercontent.com/22881963/196254745-40aaf572-d0ea-413d-8f65-0f9b70ea61ef.png">
<img width="877" alt="newlands2" src="https://user-images.githubusercontent.com/22881963/196254761-56099838-0a30-43e4-b1b2-0c0ab046235c.png">
<img width="883" alt="newlands3" src="https://user-images.githubusercontent.com/22881963/196254767-0f4d0823-6799-4d58-9ed5-5b1397130c58.png">
<img width="852" alt="newlands4" src="https://user-images.githubusercontent.com/22881963/196254779-c904622c-c3af-4be0-853a-6a2934b50422.png">

  
# Quick guide:  

## CONTROLS   
Use Joystick (both ports should work fine) for controls. 

## OBJECTIVE   

There are 4 scenarios you can play.

Conquer - you need to destroy all pirates' hideouts and the stronghold. 
Survive - try surviving until 50th turn. 
Free play - Same as Conquer, but without victory conditions.
Peaceful play - No enemies. 
  
## ISLANDS  
  
Every Island is defined by several parameters. All resources are randomized.    
An island resource parameter with 0 enas that this particular resource is not available on this island.   
Any value above 0 means that you can build appropriate building to start producing this resource. You can expand your buildings to the maximize resource gathering. Once resouce reaches 0, all production is stopped. You can also raze unused buildings.
Usually all available resources are masked with "?" sign, meaning that island has this resource available, but exact amount is not known. You need to colonize or scout colony to find out that.    
  
### Island Params  
  
Wood - Basic resource. Needed to build 1 lvl buildings and construct ships.   
Food - Required to populate your colonies.   
Stone - Stone is needed when you want to expand your 1 lvl buildings.   
Iron - Iron can be used to make guns in a foundry.   
Defense - How easy to defend the island is. 0 meaning that island is easly accessible, with no natural barriers. 3 meaning that island is hard to attack. 
Size - Literally how many buildings and their upgrades you can build (with 1 lvl building taking 1 space, 2 and 3 level buildings taking 2 space).   
  
## SHIPS:  
  
Ships are your basic tools to shape your Empire. Some are good in exploration and scouting, others in transporation and finally in battles.   
  
There are 6 types of ships.  
  
### Ship types:  
  
Pinnace - Very small, quick ship. It's perfect for exploration and scouting missions. Should avoid battles.   
Sloop - Your first choice, when it comes to gun fights. Relatively good in all aspects.   
Flyut - Mainly transport ship.   
Brig - Solid balance between transporation, exploration and fire power.   
Galleon - Big trade ship, with solid fighting capabilities.   
Frigate - Fast and nibble fighting ship.   
  
### Ship params:  
  
Exploration - How effective ship is in finding or scouting islands.   
Load - how many resources a ship can hold in a storage (including loaded guns)  
Guns - how many guns a ship can use in a battle  
Condition - represents ship's and crew's condition and how difficult it is to destroy a ship  
Wood cost - as the name says.   
Shipyard - shipyard required level to construct a ship  
  
### Ship Actions:  
  
1. Exploration allows to find new islands. Exploration attribute directly affects chances of finding new lands. First islands are easier to find.   
  
2. Colonization. This action will create your new colony on selected island. To perform this action, you need to have 2 food loaded onto your ship.   
  
3. (Un)load gives possibility to transport goods between islands, or to simple (un)arm a ship with guns. Please notice that loading and unloading requires 1 turn, so transported good will be available for futher use the next turn.   
  
To represent a "cargo changes" we use two numbers devided by "|". First number tells what is a planned change to the second number which represents current state (with beginning of the turn). Eg:  
  
Wood: 0|3  
  
Ship has 3 units of wood in a cargo and upon "next turn" this will not change (player is not unloading).  
Next turn: 0 + 3 = 3  
  
Wood: 2|0  
  
Ship does not have any wood in cargo, but because of the (Un)Load action it will be increased by 2 in the next turn.  
Next turn: 2 + 0 = 2  
  
Wood: -3|3  
  
Ship has 3 wood, but will unload all of it.  
Next turn: -3 + 3 = 0  
  
4. Patrol
Patrol is a defense action for one of your colonies. If attacked, all patrolling ships will be involved in a battle to defend your island. Ships on patrol will also intercept any pirate ship that tries to attack your trading ships (un)loading goods in a colony.  
  
5. Attack
Selected ship will attack and try to defeat any enemy force on selectd island.   
  
6. Repair
Action to repair any ship's damage.
  
7. Scout
Find if selected island is inhabited by cannibals or pirates, also investigates how big are island's resources.    
  
7. Idle   
No action  
  
## COLONIES  
  
Colony is your way to expand your dominance, by building, constructing and populating.   
  
You start with 1 colony, but you can and you should quickly colonize other islands.   
  
### Colony actions:  
  
Build  
Allows to build the first level a chosen building.  
To build and expand you need to have an appropiate level of island's free space and colony's population.   
You can build and expand freely, but sum level of all your buildings' sizes cannot exceed island size.  
  
Sawmill - produces wood  
Farm - produces food  
Quarry - produces stone  
Iron mine - produces iron  
Foundry - converts iron to guns  
Shipyard - constructs ships  
Fort - increases defense of the island   
  
Expand  
Upgrade an existing building.
Max level of any building is 3.   
Expand action for any building takes 2 turns. Any expanded building level takes also 1 extra space of island (1 lvl building = 1 space, 2 lvl building = 3 space, 3 lvl building = 5 space)
  
Raze  
Completely destroys a building. Can be useful if you want to make a space for other buildings, resources are depleted or you cannot afford to populate your colony.  
  
Populate  
All buildings need workers and for that you need populated colonies. 1 population is needed for every level of your buildings.   
Eg. Sawmill lvl 3 and Quarry lvl 1 will need in total 4 population.   
  
To increase a population by 1, you need to spend a food in equal to half of the future population (floor the result) + 1. Eg.   
To increase population from 5 to 6, you need 6/2 + 1 = 3 + 1 = 4 food
  
Construct  
Allows to build new ships.   
In Shipyard level 1 you can construct pinnaces and sloops. In level 2 brigs and fluyts. In level 3 frigates and galleons.   
By default all ships are built in 2 turns. But if level of your shipyard is higher than a level of the ship than it's reduced to 1 turn. Eg. Building sloop in Shipyard lvl 2 will take 1 turn, instead of 2.   
  
General tips:

1. Defense is really important. Try to build a fort in your colonies as soon as possible. Also consider colonizing islands with a high defense parameter.  
2. Bigger colonies atract pirates more often. Take that into consideration when planning your strategy.  
3. Attack enemy as soon as possible. With more and bigger hideouts, it might get difficult.  
4. Remember to scout often! Pirates near your colonies might be more aggressive. Also an island that was empty few turns ago, might be now packed with pirates.  
5. Destroying Pirate's Strongold is your key to the victory.  
6. Every ship has it's role. Do not neglect that.  

That's all for now!   
Good luck have fun  

Changelog  

0.4 

Improvements: 
 
- Big change in island resources. Islands will now have a limited number of resources to gather. Also colonies can now expand their resource buildings to a maximum level. 
- Reimplemented how pirates spawn their hideouts, how they expand and how we calculate strength of pirates attacks. Hideouts and stronghold will now actually produce battle ships (pirates prefer sloops) that can be used for a defense or an attack. 
- Scout islands to get info about the current number of pirates ships in their ports. 
- Reimplemented exploration and scout chances of success. First islands are now explored more easily, while the last islands will be much more difficult to find. 
- Failed scouting can result now in receiving damage, or even getting your ship sunk when enemy is present on the island. Remember to take your guns with you! 
- Replaced "Save game" with "Options" in the main menu. Options will also allow to Restart the Game. Load/Save game is still not implemented. 
- Added possibility to restore default island parameters after randomizing them. 
- Pirates can build their hideouts only if the Stronghold was not defeated. 
- Reverted back "2 iron for 1 gun".
  
0.3.2 

Improvements: 
  
- Moved action window, so it does not overlap colony/ship info. 
- Reduced size of the default island 
- 2 units of iron are now required to produce 1 gun 
- Nerfed Galleon and Frigate. Made Galleon more trade focused instead of being good at everything. 
 
Bugs: 
 
- Fixed#5: Reassigning repair to another port does not reset repair state 
- Fixed#4: Broken ship name in news in some cases. 
- Fixed#2: Issue with line breaking in news
- Some code fixes to hopefully reduce number of crashes 


Known bugs: 
 
- Random crashes 
 
0.3.1  

Improvements: 
  
- Minor UI changes 
- Decreased chances of being attacked by pirates 
 
Bugs: 
  
- Colony info screen was displaying wrong colony max. size (actually island size) 
- Fixed text formating in News 
- Fixed Joystick in Port#2 (you can now use any joystick anytime) 
- Resolved issue of not decreasing colony used space when fort is getting destroyed 

0.3.0  

Improvements: 
  
- Added Pirates. Pirates start with a Stronghold on the last island. Pirates will try to expand on other islands and build hideouts. Their "colonies" can grow over time. More and bigger hideouts pirates have, more and stronger attacks they will deploy. 
- Defeated colonies will have their population decreased and some resources will be lost. 
- Patrol will add a ship to the defensive forces of the island, if attacked. 
- New islands will now have some information about island params hidden by default. Scout island to get more precise information about it resources. 
- Implemented all victory and defeat conditions, and all scenarios are now implemented.
- Added current ship's load on transport screen 
 
Bugs: 
  
- Some typos
- Reimplement battle mechanics. It was full of bugs 
- Could not colonize some islands 
- Cancel button in Transport screen was cancelling action, but not moved resources. 
 
0.2.0  
 
Improvements: 
  
- Added battle mechanics. Guns give 50% chance to inflict a damage to the enemy and vice versa (where Cannibals' equivalent of guns is a village size)
- Island defense works like armor. You need to inflict enough damage to the island itself, before you can inflict damage to the cannibals village. 
- Changed "Hull" to "Cond." (Condition)
- Decreased Hull/Cond. for all ships by 1
- Repair action is now implemented. It allows to repair 1 damage with 1 wood. It requires shipyard in selected colony. 
- Possibility to display multile pages of News (done by selecting NEWS option from menu)
- For lvl 2 and lvl 3 (expanded) buildings size was increased from 1 to 2. 
- Changed pseudorandom number generator function. 
- Added Scenarios (Free Play, Conquest, Survive, Peaceful Play)
- Multiple changes to game balance (ship/building params and costs)
  
Bugs: 
  
- Fixed bugs that allowed to "spawn" resources by using transport action and cancelling it a specific way. 
- Wrong building name when displaying "razed building" news.
- Fixed a bunch of other, minor bugs
- Guns production wasn't working good enough
  
Known issues:  
  
- So far none :)
  
0.1.1  
  
Improvements: 
  
- Added Game Menu with Logo
- Added support for joysticks selection. For now, the first joystick port you use will be marked as selected and used. 
- Added the first type of enemy "Cannibals" that can spawn on random islands. 
- Implemented the simple version of "attack action", which for now simply removes cannibals from the islands (if you have enough guns loaded vs enemy group size).
- Implemented "scout action". It's used to check if the island is inhabited by Cannibals. Ship's explore param affects the chances of success. 
- Added logic to prevent colonizing islands if cannibals are present there. Colonization attempts without loaded guns can result in failure! 
- New "news" was included - Unloading, scouting, attacking and unsuccessful colonization.
- Added support for multiline news
- Decreased number of food needed for next level
- Increase all buildings wood cost by 1 
  
Bugs: 
  
- Resolved issue when transported goods were not unloaded
- Also resolve a case when setting the ship to Idle, did not cancel previous transport action (goods were still loaded).
- Fixed wrong wood cost for buildings
- Fixed bug for Islands that displayed “Your colony @Red Rock”.
- Fixed bug for Ship's action status that displayed "Scout @Red Rock"
- Corrected error that did not handle properly turns for some colonies 
  
Known issues: 
  
- News screen is not able to handle to many news yet (it can actually crash the game :). News paging is on the To Do list. 
- There is a way to "spawn" resources using (un)loading action. Problem was diagnosed and there will be a fix for it
