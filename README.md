# C64 New Lands  
New Lands v.0.2.0
  
New Lands is a game developed for Commodore 64.   
Game combines elements of a strategy and simple economy in pirate styled genre.   
  
Please notice, that this is alpha version of the game, without any real challange yet (no attacking pirates, victory conditions etc.).  
This version focuses on "sim" aspect of the game, meaning exploration, expansion and building.  
  
You can contact me on Discord 64bites (@MagicKrol) or via email mzkrol@gmail.com  
  
# Quick guide:  

## CONTROLS   
Use Joystick (both ports should work fine) for controls. 

## OBJECTIVE   

Your goal so far is to colonize as many islands as possible, expand your colonies to maximum and build a huge fleet.  
  
## ISLANDS  
  
Every Island is defined by several parameters:  
All resources are randomized between 0 and 3.   
0 meaning that this particular resource is not available on this island.   
Any value above 0 means that you can build appropiate building to start producing this resource. You can expand your buildings to the max level of the island resource. Eg. Island with WOOD: 2 cannot have Sawmill lvl 3.   
  
### Island Params  
  
Wood - Basic resource. Needed to build 1 lvl buildings and construct ships.   
Food - Required to populate your colonies.   
Stone - Stone is needed when you want to expand your 1 lvl buildings.   
Iron - Iron can be used to make guns in Foundry.   
Defense - How easy to defend island is. 0 meaning that island is easly accessible, with no natural barriers. 3 meaning that island is hard to attack.   
Size - Literally how many buildings and their upgrades you can build.   
  
## SHIPS:  
  
Ships are your basic tools to shape your Empire. Some are good in exploration and scouting, others in transporation and finally in battles.   
  
There are 6 types of ships.  
  
### Ship types:  
  
Pinance - Very small, quick ship. It's perfect for exploration and scouting missions. Should avoid battles.   
Sloop - Your first choice, when it comes to gun fights. Relatively good in all aspects.   
Flyut - Mainly transport ship.   
Brig - Solid balance between transporation, exploration and fire power.   
Galeon - Big, dangerous but slow.   
Frigate - Fast and nibble fighting ship.   
  
### Ship params:  
  
Exploration - How effective ship is in finding or scouting islands.   
Load - how many resources can ship hold in a storage (including loaded guns)  
Guns - how many guns can a ship use in a battle  
Hull - represents ship condition and how difficult it is to destroy a ship  
Wood cost - as the name says.   
Shipyard - shipyard required level to construct a ship  
  
### Ship Actions:  
  
1. Exploration allows to find new islands. Exploration attribute assigned to every ship type directly affects chances of finding new lands.   
  
2. Colonization. This action will create your new colony on selected island. To perform this action, you need to have 2 food loaded onto your ship.   
  
3. (Un)load gives possibility to transport goods between islands, or to simple (un)arm a ship with guns. Please notice that loading and unloading requires 1 turn, so transported good will be available for futher use next turn.   
  
To represent cargo change we use two numbers devided by "|". First number tells what is a planned change to the second number which represents current state (with beginning of the turn). Eg:  
  
Wood: 0|3  
  
Ship has 3 units of wood in cargo and upon "next turn" this will not change (player is not unloading).  
Next turn: 0 + 3 = 3  
  
Wood: 2|0  
  
Ship does not have any wood in cargo, but because of the (Un)Load action it will be increased by 2 in the next turn.  
Next turn: 2 + 0 = 2  
  
Wood: -3|3  
  
Ship has 3 wood, but will unload all of it.  
Next turn: -3 + 3 = 0  
  
4. Patrol (NOT IMPLEMENTED YET)  
Patrol is a defense action for one of your colonies. It will increase chances to defeat any attacking force that directs selected colony or any ship that (un)loads or repair ship in the colony.  
  
5. Attack
Selected ship will attack and try to defeat any enemy force on selectd island.   
  
6. Repair (NOT IMPLEMENTED YET)  
Action to repair all damage to your ship   
  
7. Scout
Find if selected island is inhabited by cannibals or pirates.   
  
7. Idle   
No action  
  
## COLONIES  
  
Colony is your way to expand your dominance, by building, constructing and populating.   
  
You start with 1 colony, but you can and you should quickly colonize other colonies.   
  
### Colony actions:  
  
Build  
Allows to build first level of buildings. It requires a coresponding resource, except: Foundry, Shipyard and Fort.  
To build and expand you need to have an appropiate level of island's free space and colony's population.   
You can build and expand freely, but sum level of all your buildings cannot exceed island size.  
  
Sawmill - produces wood  
Farm - produces food  
Quarry - produces stone  
Iron mine - produces iron  
Foundry - converts iron to guns  
Shipyard - constructs ships  
Fort - increases defense of the island   
  
Expand  
Upgrade existing building, to the level of coresponding resource, except: Foundry, Shipyard, Fort.  
Max level of any building is 3.   
Expand action for any building takes 2 turns.   
  
Raze  
Completely destroys a building. Can be useful if you want to make a space for other buildings, or you cannot afford to populate your colony.  
  
Populate  
All buildings need workers and for that you need a populated colonies. 1 population is needed for every level of your buildings.   
Eg. Sawmill lvl 3 and Quarry lvl 1 will need in total 4 population.   
  
To increase a population by 1, you need to spend food equal to half of the future population (floor the result) + 1. Eg.   
To increase population from 5 to 6, you need 6/2 + 1 = 3 + 1 = 4 food
  
Construct  
Allows to build new ships.   
In Shipyard level 1 you can construct pinances and sloops. In level 2 brigs and fluyts. In level 3 frigates and galeons.   
By default all ships are built in 2 turns. But if level of your shipyard is higher than a level of the ship than it's reduced to 1 turn. Eg. Building sloop in Shipyard lvl 2 will take 1 turn, instead of 2.   
  
That's all for now!   
Good luck have fun  

Changelog  

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
- Addd Scenarios (Free Play, Conquest, Survive, Peaceful Play)
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