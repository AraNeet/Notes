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

### 5.6.1 Two Neutral Control Points
- Provide strategic advantages through buffs, debuffs, or system access

#### 5.6.1.1 Ideas
- One of the obj give player a vehicle for a determine time frame
	- Vehicle - Is slow and must be controlled by a player. The vehicle does an increase amount of damage to structs. But can only damage player by running over.
- One of the obj give players (base on the character) that last hit an empower ability for 3 casts. Second part of the buff also give play an amount of bonus max health damage equal to a % of the bonus stats.
- Idea for persistent obj Every 5 mins or so. A obj spawn that gives the ability to the player to push their turret up on one side of the map for an amount of time that the turrets return to previous locations


 _Specific effects and mechanics to be determined during development_
## 5.7 Structure

### 5.7.1 Turrets
For a set time frame at the start of the game turrets will be close to the center of the maps for both sides as the game reaches (12 mins) example. The turrets will slowly retreat to the mini bases to reinforce the mini bases.

Mid turret will be destructible.

### 5.7.2 Mini Bases
These structure could be destroyed or claimed. 
If destroyed the turrets of the near by will retreat and become destructible. 
If claimed the turrets get disable for the opposite team then minion that pass through the claim mini base become enhanced.

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
- **Craters**: Natural cover and obstacles

### 6.4 Interactive Map Objects

- **Rovers and Vehicles**: Mobile environmental elements
- **Space Buildings**: Static defensive structures
- **Floating Objects**: Aerial platforms and obstacles

### 6.5 AI Elements & Game Progression

**NPCs, Minions, and Neutral Camps** These serve as the primary mechanisms for match progression and map control.



_Detailed breakdown and mechanics require further development_

### 6.6 Control Schemes

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