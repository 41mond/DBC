# DBC
A Card Building Game

# Game Mechanics Overview

## Characters

- **Player Character**: Located at the bottom left corner of the screen with three basic attributes:
  - **Attack**
  - **Defense**
  - **Health**
- Different classes have varying base attributes. After each battle, attributes reset to base values. Buffs or debuffs do not persist after battles.

- **Armor System**: 
  - Both player and enemies possess armor values.
  - Damage depletes armor first, then health.
  - Health below 0 triggers a "ghost state," where if the turn ends, the player/enemy loses. Players can act for one turn in this state to heal or defeat the enemy.

## Rooms

- **Roguelike Map**: Randomly generated with 3 major levels, each containing 5 sub-levels. Room types include:
  1. **Combat Room**: Battles reward coins and a card.
  2. **Intense Combat Room**: Harder battles grant a powerful blessing.
  3. **Shop Room**: Spend coins to buy or remove cards.
  4. **Wanted Room**: Exchange specific cards for coins.
  5. **Campfire Room**: Upgrade cards or restore health.
  6. **Laboratory Room**: Enhance cards in various ways.

## Turns

- Each turn begins with replenishing action points, drawing two cards, and playing cards using action points or energy.
- After the player's turn, the enemy will indicate their next moves, execute them, and then the player's turn resumes.

## Cards

- Cards require action points or energy to play.
- Effects may relate to attack or defense.
- Upgrading a card increases its values by 20%.
- The player's hand limit is 10 cards.

# Modding Guide for DBC Game

## Modding Overview
To create mods for the game, navigate to the `DBC_Data\StreamingAssets` folder in the game's root directory. This guide will walk you through the process of creating various mods.

## Creating New Classes
- **Class Files**: Create new classes by adding `Class_X.ini` files.
- **Character Configuration**: Update the `Characters.ini` file simultaneously to ensure the new class is recognized by the game.

## Card Packs (DLC)
- **Basic Information**: Store the basic information of new card packs in the DLC section.
- **Card Files**: 
  - Navigate to the `Mod` folder.
  - Follow the structure of existing folders to create card files for your expansion pack.
  - Card files represent data such as name, description, cost, etc.
- **Lua Scripts**: 
  - Enter the `Lua` folder.
  - Use Lua language to script the usage effects of your cards.
  - Refer to Deka’s function library for guidance.
  - Ensure the file suffix is `.lua.txt`.

## Illustrations
- For vivid card illustrations, place png images in the `Sprite` folder using the same name as the card.

## Modifying Enemy Skills
- **Skill Library**: Modify enemy skills by following the naming format `__ESK_X.ini`.
- **Levels and Enemies**: 
  - Adjust generated levels and enemy appearances in the `Enemies` folder.
  - Update `MapNames.ini` to enable the enemy map folder.
  - Design your enemies by imitating the structure of other files.
  - Use `__Enemy_X` for normal enemies, `Elites_X` for intense battle encounters, and `__BOSS_X` for bosses.
  - Enemies will use skills in a sequential order.
- For multi-form enemies, adjust the `next` key value to point to the new form directory.

## Obtainable States
- **State Folder**: Modify, add, or delete obtainable states.
- **State Information**: 
  - `StateInfo` stores introduction text.
  - `StateUI` contains the state images.
- **Lua Effects**: 
  - Lua files in this folder define the effects.
  - Implement trigger timing, consumption, and other state behaviors by referring to these scripts.

Remember to maintain a professional tone and clarity throughout your modding process to ensure a smooth and enjoyable experience for all players.
