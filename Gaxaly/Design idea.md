# Voided Masks - Game Design Document

## 1. Introduction

This document outlines the core gameplay design for "Voided Masks," a multiplayer strategy MOBA set in a futuristic space colony. The design concepts and vision are based on ideas developed by Aramis Martinez.

### 1.1 Document Purpose

This GDD serves as the primary reference for all team members to understand the fundamental mechanics, systems, and vision of Voided Masks. It should be consulted when making design decisions or implementing new features.

### 1.2 Content Conventions

- **Normal text**: Core design elements and recommendations by Aramis Martinez
- **Bold text**: Suggestions and additions contributed by team members and collaborators

## 2. References

_To be updated as development progresses_

## 3. Target Platforms

### 3.1 Primary Targets: Windows & macOS

These platforms represent our main development focus. The game is designed primarily with PC and Mac users in mind, targeting systems that are up to 6 years old to ensure broad accessibility.

**Technical Requirements:**

- Support for hardware configurations from 2019 onwards
- Optimized performance for mid-range gaming setups

### 3.2 Secondary Targets: Console & Mobile

**Planned but not prioritized during initial development**

**Challenges to address:**

- **Control Adaptation**: Redesigning input schemes for touch and controller interfaces
- **Performance Optimization**: Ensuring smooth gameplay on last-generation console hardware
- **UI Scaling**: Adapting interface elements for various screen sizes

## 4. Development Environment

### 4.1 Game Engine

**Unity Engine** - Selected for its cross-platform capabilities and robust multiplayer networking support.

## 5. Core Game Specification

### 5.1 Game Concept

Voided Masks is a fast-paced, team-based multiplayer online battle arena (MOBA) that emphasizes strategic gameplay and coordinated team tactics.

### 5.2 Narrative Setting

#### 5.2.1 World & Time Period

**31st Century Space Colony** - The game takes place in a futuristic orbital habitat where civil conflict has erupted, dividing the colony into warring factions.

### 5.3 Team Structure & Match Format

- **Two opposing factions** with mirrored character rosters
- 6 players per team** (12 players total per match)
- Each faction offers **various character roles and specializations**
- **Objective-based gameplay** centered around territorial control

### 5.4 Cross-Platform Features

- **Cross-play compatibility** across all supported platforms
- **Cross-save functionality** allowing players to maintain progress across devices

### 5.5 Core Player Actions

Players select characters at match start, each providing unique abilities to:

- **Attack** enemy players and objectives
- **Control** strategic map elements
- **Manage** various systems and interactive objects throughout the battlefield

### 5.6 Victory Conditions

#### Primary Objective

**Capture and control the enemy team's main base**

#### Secondary Objectives

### 5.6.1 Two Neutral Control Points and Jungle buffs
- Provide strategic advantages through buffs, debuffs, or system access


## 5.7 Structure
- Turrets
- Mini Bases
- Main Bases

### 5.8 Visual Design

#### 5.8.1 Art Direction

**Voxel Art Style** - A distinctive blocky, pixelated 3D aesthetic that supports both performance optimization and unique visual identity.

_Additional visual specifications to be developed_

### 5.9 Data Management

_Technical specifications for player data, save systems, and server architecture to be determined_

## 6. Gameplay Systems

### 6.1 Map Design

**Setting**: Space colony civil war battlefield _Final map dimensions and layout to be determined during playtesting_

### 6.2 Environmental Elements

The battlefield will feature various voxel-based FBX objects:

**Infrastructure:**

- **Pathways** - Main travel routes connecting key areas
- **Space Buildings** - Defensive structures and strategic positions
- **Rovers and Vehicles** - Mobile cover and interactive elements

**Interactive Objects:**

- **Supply Crates** - Resource containers
- **Impact Craters** - Terrain obstacles and cover
- **Floating Debris** - Environmental hazards and platforms

### 6.3 Ground-Level Features

- **Pathways**: Primary movement corridors
- **Crates**: Interactive supply containers
	- Crates Ideas. 
		- These could fall around the jungle giving permeant stats boost to a player.
		- Dark spawn around the maps spawn where buried crates are the take 4 second to dig out. 
		- They could be dropped by minions allowing for player to pick up the crates give bonus stats or gold.
- **Craters**: Natural cover and obstacles

### 6.4 Interactive Map Objects

- **Rovers and Vehicles**: Mobile environmental elements
- **Space Buildings**: Static defensive structures
- **Floating Objects**: Aerial platforms and obstacles
	- Floating Objects Ideas
		- They can allow player to jump on them for 2 second moving them around the map.
		- They could randomly fall. Creating an indicator at fall location.

## 6.5 Fog of space / Vision
Light on the plant is less that on other plants. So player can only see a set distance around them. If the plant is on higher ground the player can see a lot move around them.

### 6.5.1 Day/Night Cycle
Every 10 min for 1 min and 30 seconds It because Day This allow player to see more of the maps and high ground allow to see the player to see even more.

### 6.6 AI Elements & Game Progression

**NPCs, Minions, Jungle camps and Neutral Camps** These serve as the primary mechanisms for match progression and map control.

### 6.6.1 Minions
So minions are the main way to get resources in lanes. Minions spawn around every 15 seconds. Players have the ability to choose what type of wave it is as the game goes.
#### 6.6.1.1 Waves and units
- Basic Minion units
	- Melee are short range. they live longer then a range but deals less damage.
	- Range are long range. they deal more damage then a melee but dead faster.
- Special Minions units 
	- Snipers deal increase damage but are able to die in 3 attacks of any source.
	- Leaders buff the other minion around with a small defenses boost.
	- Tanks are able to take more damage compare to normal minions but deals less damage as a trade off.
- Minions waves ideas
	- Interchangeable waves
		- Base wave - This wave spawn with 6 basic minion 3 melee and 3 range. and it the starting wave. it spawn every 15 seconds
		- Speed wave - This wave spawn with 4 basic minions it only melee. IF this wave is set to base wave during the game it spawns every 10 seconds.
		- Ranges wave - This wave spawn with 4 basic minions and 1 special minions. 4 range and 1 snipers. If this wave is being use spawn every 12 seconds.
	- Objectives waves
		- Power wave - This wave spawn with 5 basic minions and 2 special minion. 2 melee, 3 range, and 2 If this wave is being use spawn every 25 seconds.
		- Enhanced wave - This wave spawn with 6 basic minions with 2 special minions. 3 melee, 3 range, 1 tank, and 1 sniper. If this wave is being use spawn every 25 seconds.
#### 6.6.1.2 Minions Controls
Minions on the side lanes can be direct to path in a different way.
Because of the top and bot multi path structure player are allow to tell minion what path to take. each path has a different distance that the minions need to cover. So this can be use to control minion timing.
In Mid lane because of it single lane structure minions can be tell to target a specific minions. or Near by objects. Minions only that are in lane during the start of the objective  are the only minions that can target objective.

### 6.6.2 NPC's (Idea not Sure)
There are 2 NPC around the map. 
These NPCs allows players to get a unique stat boost for the whole team base on what objective and how many objective you have. 
If the team is unable to get any objective by the time these NPCs spawns The NPCs will give a quest called gambit. 
That if the team can complete the NPC will give them a random Objective buff. and a unique stat boost base of the buff received.
### 6.6.3 Jungle Camps 
Jungle camps are groups of monsters or creatures that are around the maps 6 per each side of the map. 
These camps gives around 250 golds plus an exp amount per camps. 
Then there are 2 additional camp on each side of the maps this camp a jungle buffs. These buffs are to allow jungles to clear the camp quicker or to give them bonus power for a allotted time frame.
Normal camps spawn every 1min and 30 seconds
and Buff spawn every 4 mins.

### 6.6.4 Neutral camps 
#### 6.6.1.1 Ideas
##### 6.6.1.1.1 rotating objs
- One of the obj give player a vehicle for a determine time frame
	- Vehicle - Is slow and must be controlled by a player. The vehicle does an increase amount of damage to structs. But can only damage player by running over.
- One of the obj give players (base on the character) that last hit an empower ability for 3 casts. Second part of the buff also give play an amount of bonus max health damage equal to a % of the bonus stats.
##### 6.6.1.1.2 Stacking objs
- One of the obj is a stacking obj that give player that auto attack minions under their turret increase defense for 2 seconds. for a max of 6 second which scales with amount of stacks for a max of 15 seconds. If player attack enemy player under their turret bonus defense go to normal.
##### 6.6.1.1.3 persistent objs
- Idea for persistent obj Every 5 mins or so. A obj spawn that gives the ability to the player to push their turret up on one side of the map for an amount of time that the turrets return to previous locations
- Idea for persistent obj Every 10 mins or so. A obj spawn that give a rebuff to enemy player receive a % of bonus damage. and reduce turret attack speed by %.

##### 6.6.1.1.4 Jungle Buffs
- One of jungle buff give jungler a buff that lasts 3 mins. This buff give jungler a bonus damage to jungle camp and a % increase against enemy player.
- One of jungle buff give jungler a buff that lasts 3 mins. This buff gives jungler an enhanced ability every 2 ability. This enhanced ability deals % extra damage from base. If the ability is a shield or buff it increases the ability effectiveness by a %
 _Specific effects and mechanics to be determined during development_
_Detailed breakdown and mechanics require further development_

## 6.7 Structures.
### 6.7.1 Turrets
For a set time frame at the start of the game turrets will be close to the center of the maps for both sides as the game reaches (12 mins) example. The turrets will slowly retreat to the mini bases to reinforce the mini bases.

Mid turret will be destructible.

### 6.7.2 Mini Bases
These structure could be destroyed or claimed. 
If destroyed the turrets of the near by will retreat and become destructible.  3000
If claimed the turrets get disable for the opposite team then minion that pass through the claim mini base become enhanced.  30 second.


### 6.8 Control Schemes

**PC (Primary):**

- **Customizable keybindings**
- **Mouse and keyboard** optimization

**Console (Secondary):**

- **Controller support** with adapted UI
- **Platform-specific button mapping**

**Mobile (Future):**

- **Touch controls** with gesture recognition
- **Adaptive UI** for various screen sizes

---

## Development Notes

- Sections marked "to be determined" require team discussion and prototype testing
- **Bold additions** from team members should be reviewed and integrated into core design
- Regular updates to this document as development progresses