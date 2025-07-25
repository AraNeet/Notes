# Voided Masks - Game Design Document

## Table of Contents

1. [Introduction]
2. [Game Overview]
3. [Target Platforms]
4. [Technical Specifications]
5. [Core Gameplay]
6. [Game World and Setting]
7. [Characters and Teams]
8. [Map Design and Environment]
9. [Game Systems]
10. [Progression and Objectives]
11. [Visual and Audio Design]
12. [User Interface]
13. [Technical Architecture]
14. [Development Timeline]
15. [Appendices]

---

## 1. Introduction

### 1.1 Document Purpose

This Game Design Document (GDD) serves as the primary reference for all team members to understand the fundamental mechanics, systems, and vision of "Voided Masks." It should be consulted when making design decisions or implementing new features throughout the development process.

### 1.2 Project Vision

Voided Masks is a multiplayer strategy MOBA set in a futuristic space colony, emphasizing tactical gameplay and coordinated team strategies. The design concepts and vision are based on ideas developed by Aramis Martinez.

### 1.3 Document Conventions

- **Normal text**: Core design elements and recommendations by Aramis Martinez
- **Bold text**: Suggestions and additions contributed by team members and collaborators
- _Italicized text_: Items requiring further development or team discussion

### 1.4 Version History

| Version | Date | Changes                   | Author          |
| ------- | ---- | ------------------------- | --------------- |
| 1.0     | TBD  | Initial document creation | Aramis Martinez |

---

## 2. Game Overview

### 2.1 Game Concept

Voided Masks is a fast-paced, team-based multiplayer online battle arena (MOBA) that emphasizes strategic gameplay, coordinated team tactics, and objective-based territorial control.

### 2.2 Core Pillars

- **Strategic Depth**: Complex decision-making through character selection, map control, and team coordination
- **Accessibility**: Intuitive mechanics that are easy to learn but difficult to master
- **Visual Identity**: Distinctive voxel art style that optimizes performance while maintaining unique aesthetics
- **Cross-Platform Unity**: Seamless gameplay experience across multiple platforms

### 2.3 Target Audience

- **Primary**: PC MOBA
- **Secondary**: Console strategy game players
- **Tertiary**: Mobile competitive gaming audience

### 2.4 Unique Selling Points

- 6v6 team-based combat in a space colony setting
- Dynamic map control through movable turrets and claimable structures
- Voxel art style optimized for performance across platforms
- Innovative fog of war system with day/night cycles

---

## 3. Target Platforms

### 3.1 Primary Platforms

**Windows & macOS**

- Main development focus targeting PC and Mac users
- Support for hardware configurations from 2019 onwards
- Optimized for mid-range gaming setups

**System Requirements:**

- **Minimum**: Hardware up to 6 years old
- **Recommended**: Mid-range gaming configurations from 2021+

### 3.2 Secondary Platforms

**Console Platforms** _(Planned but not prioritized during initial development)_

**Challenges to Address:**

- **Control Adaptation**: Redesigning input schemes for controller interfaces
- **Performance Optimization**: Ensuring smooth gameplay on console hardware
- **UI Scaling**: Adapting interface elements for television displays

### 3.3 Future Platforms

**Mobile Platforms**

**Challenges to Address:**

- **Touch Interface**: Complete UI/UX redesign for touch controls
- **Performance Constraints**: Optimization for mobile hardware limitations
- **Screen Adaptation**: Interface scaling for various mobile screen sizes

---

## 4. Technical Specifications

### 4.1 Game Engine

**Unity Engine** - Selected for cross-platform capabilities and robust multiplayer networking support

### 4.2 Development Environment

- Unity 6 (or latest stable version)
- Version control: Unity Version Control
- Project management: Aramis Martinez ( Lead Project Manager )

### 4.3 Performance Targets

- **60 FPS** on recommended hardware
- **30 FPS minimum** on minimum hardware
- **Sub-100ms** network latency for optimal gameplay

---

## 5. Core Gameplay

### 5.1 Match Structure

- **12 players total** (6 players per team)
- **Two opposing factions** with mirrored character rosters
- **Match duration**: 20-40 minutes average
- **Objective-based gameplay** centered around territorial control

### 5.2 Victory Conditions

#### 5.2.1 Primary Objective

**Capture and control the enemy team's main base**

#### 5.2.2 Secondary Objectives

- Control two neutral control points
- Secure jungle buffs for team advantages
- Destroy or claim mini bases for strategic positioning

### 5.3 Core Player Actions

Players select characters at match start, each providing unique abilities to:

- **Attack** enemy players and objectives
- **Control** strategic map elements and interactive objects
- **Manage** various systems throughout the battlefield
- **Coordinate** with team members for tactical advantages

### 5.4 Cross-Platform Features

- **Cross-play compatibility** across all supported platforms
- **Cross-save functionality** allowing progress maintenance across devices
- **Universal friend system** for cross-platform social features

---

## 6. Game World and Setting

### 6.1 Narrative Setting

#### 6.1.1 Time Period and Location

**31st Century Space Colony** - The game takes place in a futuristic orbital habitat where civil conflict has erupted, dividing the colony into warring factions.

#### 6.1.2 Faction Background

_Detailed faction lore and motivations to be developed_

### 6.2 Environmental Themes

- Futuristic space colony architecture
- Industrial and technological aesthetic
- War-torn civilian infrastructure
- Zero-gravity and artificial gravity zones

---

## 7. Characters and Teams

### 7.1 Team Composition

- **6 players per team** (12 total per match)
- **Various character roles and specializations** available to each faction
- **Mirrored character rosters** ensuring balanced competitive play

### 7.2 Character Roles

_Specific character classes and roles to be defined during development_

### 7.3 Character Selection

- Pre-match character selection phase
- **Unique abilities** for each character type
- Strategic team composition considerations

---

## 8. Map Design and Environment

### 8.1 Overall Map Structure

**Setting**: Space colony civil war battlefield _Final map dimensions and layout to be determined during playtesting_

### 8.2 Core Structures

#### 8.2.1 Turrets

- **Dynamic positioning**: Turrets start near map center and retreat to mini bases after 12 minutes
- **Mid-lane turrets**: Destructible throughout the match
- **Strategic repositioning**: Affects map control and lane dynamics

#### 8.2.2 Mini Bases

Interactive structures that can be:

- **Destroyed**: Causes nearby turrets to retreat and become destructible (3000 HP)
- **Claimed**: Disables enemy turrets for 30 seconds and enhances passing minions

#### 8.2.3 Main Bases

- **Primary victory objective**
- **Heavily fortified** requiring coordinated team assault
- _Specific mechanics to be developed_

### 8.3 Environmental Elements

#### 8.3.1 Infrastructure

- **Pathways**: Main travel routes connecting key areas
- **Space Buildings**: Defensive structures and strategic positions
- **Rovers and Vehicles**: Mobile cover and interactive elements

#### 8.3.2 Interactive Objects

- **Supply Crates**: Resource containers with multiple implementations:
    - Jungle crates providing permanent stat boosts
    - Buried crates requiring 4 seconds to excavate
    - Minion-dropped crates offering bonus stats or gold
- **Impact Craters**: Terrain obstacles providing natural cover
- **Floating Debris**: Environmental hazards and platforms with dynamic behavior:
    - 2-second platform functionality for player movement
    - Random falling debris with location indicators

### 8.4 Terrain Features

#### 8.4.1 Ground-Level Elements

- **Pathways**: Primary movement corridors
- **Crates**: Interactive supply containers
- **Craters**: Natural cover and tactical obstacles

#### 8.4.2 Multi-Path Lane Design

- **Top and Bottom Lanes**: Multiple path options allowing strategic minion routing
- **Mid Lane**: Single lane with targeted minion control mechanics
- **Path Distance Variations**: Different route lengths enabling timing control

---

## 9. Game Systems

### 9.1 Vision and Fog of War

#### 9.1.1 Fog of Space

- **Limited vision distance** due to reduced planetary lighting
- **Elevation advantage**: Higher ground provides extended vision range
- **Strategic positioning**: Vision control becomes crucial tactical element

#### 9.1.2 Day/Night Cycle

- **10-minute intervals** with 1 minute 30 seconds of daylight
- **Enhanced visibility** during day cycles
- **Elevation bonuses** amplified during daylight

### 9.2 AI Elements and Progression

#### 9.2.1 Minions

Primary resource generation and lane progression mechanism.

**Spawn Rate**: Every 15 seconds (varies by wave type)

**Unit Types:**

- **Basic Units**:
    - _Melee_: Short range, higher durability, lower damage
    - _Ranged_: Long range, higher damage, lower durability
- **Special Units**:
    - _Snipers_: Increased damage, die in 3 attacks from any source
    - _Leaders_: Provide defensive buffs to nearby minions
    - _Tanks_: High durability, reduced damage output

**Wave Configurations:**

- **Base Wave**: 6 units (3 melee, 3 ranged) - 15-second spawn
- **Speed Wave**: 4 melee units - 10-second spawn
- **Range Wave**: 4 ranged + 1 sniper - 12-second spawn
- **Power Wave**: 5 basic + 2 special units - 25-second spawn
- **Enhanced Wave**: 6 basic + 2 special units - 25-second spawn

**Minion Control:**

- **Side Lane Pathing**: Direct minions through multiple route options
- **Mid Lane Targeting**: Assign specific targets to minions
- **Objective Participation**: Only minions present at objective start can participate

#### 9.2.2 NPCs

**Concept Status**: _Under consideration_

Two map-positioned NPCs providing:

- **Team-wide stat boosts** based on controlled objectives
- **Gambit Quests**: Alternative progression for teams without objectives
- **Random objective buffs** upon quest completion

#### 9.2.3 Jungle Camps

**Standard Camps**: 6 per team side

- **Rewards**: 250 gold + experience per camp
- **Respawn**: Every 1 minute 30 seconds

**Buff Camps**: 2 per team side

- **Effects**: Enhanced jungle clearing or temporary power boosts
- **Respawn**: Every 4 minutes

**Jungle Buff Types:**

- **Clearing Buff**: 3-minute duration, bonus damage to camps and enemy players
- **Enhancement Buff**: 3-minute duration, every second ability becomes enhanced with increased damage/effectiveness

#### 9.2.4 Neutral Camps

**Rotating Objectives:**

- **Vehicle Objective**: Grants slow, player-controlled vehicle with structure-focused damage
- **Empowerment Objective**: Provides 3 enhanced ability casts plus bonus health damage

**Stacking Objectives:**

- **Defensive Stacking**: Auto-attacking minions under friendly turrets grants stacking defense (max 15 seconds)

**Persistent Objectives:**

- **Turret Advancement** (5-minute intervals): Temporarily pushes turrets forward on one map side
- **Enemy Debuff** (10-minute intervals): Increases damage taken and reduces turret attack speed for enemies

---

## 10. Progression and Objectives

### 10.1 Match Progression

- **Early Game**: Standard minion waves and jungle farming
- **Mid Game**: Turret repositioning and mini base control
- **Late Game**: Main base assault and team fights

### 10.2 Resource Systems

- **Gold**: Primary currency from minions, camps, and objectives
- **Experience**: Character progression throughout match
- **Buffs**: Temporary advantages from objectives and camps

### 10.3 Strategic Elements

- **Map Control**: Territory management through structures
- **Timing**: Coordinated pushes and objective control
- **Resource Management**: Efficient farming and team resource allocation

---

## 11. Visual and Audio Design

### 11.1 Art Direction

#### 11.1.1 Visual Style

**Voxel Art Aesthetic**: Distinctive blocky, pixelated 3D style supporting both performance optimization and unique visual identity.

#### 11.1.2 Color Palette

**World Color Theme**: First planet color scheme reference:
![[Planet+Color+Palette+sq.webp]]

_Additional visual specifications to be developed_

### 11.2 Environmental Design

- **Futuristic space colony** architecture
- **Voxel-based FBX objects** for all environmental elements
- **Consistent aesthetic** across all map elements and structures

### 11.3 Audio Design

_Audio specifications and requirements to be developed_

---

## 12. User Interface

### 12.1 Control Schemes

#### 12.1.1 PC (Primary)

- **Customizable keybindings**
- **Mouse and keyboard optimization**
- **Precision control** for competitive gameplay

#### 12.1.2 Console (Secondary)

- **Controller support** with adapted UI
- **Platform-specific button mapping**
- **Optimized for television displays**

#### 12.1.3 Mobile (Future)

- **Touch controls** with gesture recognition
- **Adaptive UI** for various screen sizes
- **Simplified control scheme** maintaining gameplay depth

### 12.2 Interface Design

_UI mockups and design specifications to be developed_

---

## 13. Technical Architecture

### 13.1 Server Architecture

**Status**: _Under deliberation_

#### 13.1.1 Option 1: AWS WebSocket Backend

![[qs_arch_websockets.png]]

#### 13.1.2 Option 2: Session-Based Game Server with Serverless Backend

![[GameLift with Serverless backend reference architecture diagram.png]]
### 13.2 Data Management Systems

- **Player Data**: AWS Cognito and DynamoDB
- **Matchmaking**: AWS GameLift queue system
- **Game Updates**: S3 storage for builds and patches
- **Save Systems**: Cross-platform progress synchronization

### 13.3 Network Architecture

_Technical specifications for multiplayer networking to be determined_

---

## 14. Development Timeline

### 14.1 Development Phases

_Detailed timeline and milestones to be established_

### 14.2 Testing and Iteration

_Playtesting schedule and feedback integration process to be defined_

---

## 15. Appendices

### 15.1 References

_To be updated as development progresses_

### 15.2 Glossary

_Game-specific terminology and definitions_

### 15.3 Development Notes

- Sections marked "_to be determined_" require team discussion and prototype testing
- **Bold additions** from team members should be reviewed and integrated into core design
- Regular updates to this document as development progresses
- All placeholder sections require further development and team input

---

_Document Version: 1.0_  
_Last Updated: [Date TBD]_  
_Next Review: [Date TBD]_