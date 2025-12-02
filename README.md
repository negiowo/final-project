# Final Project!


## Project planning: Design Doc
#### Introduction
What motivates your project?
- To furthur extend a project that I have worked on, allowing it to have more meaningful levels and be filled with 3D objects.

#### Goal
What do you intend to achieve with this project?
- Create an algorithm to procedurally generate meaningful grid-based map that coherent with existing game mechanics, then spawn 3D objects on each tile.

#### Inspiration/reference:
- [Wave Function Collapse](https://github.com/mxgmn/WaveFunctionCollapse)

#### Specification:
Outline the main features of your project

- An algorithm that generates the map
- The ability to spawn designated objects on each tile
- Allowing the objects to despawn and respawn following changes to the tile type in-game 

#### Techniques:
- Approach 1: Wave Function Collapse
  - First hand craft a few maps to showcase meaningful map definition, then feed them into the algorithm to produce map of similar and larger sizes.
  - The Algorithm will be implemented as described in the wave function collapse github.
- Approach 2: L-System-like spreading
  - Given a board with set size, player spawn location, and player's target exit, starts from the spawn point and "grow" one tile in all directions each step until the entire board is filled.
  - The new tiles generated each step depends on the two closest tiles around it, following a set of rules with possibilities.
 
    
#### Design:
<img height="350" src="/Image/0.png">

#### Timeline:
- Week 1
  - Barebone of the algorithm that generates "something", may not be meaningful yet.
- Week 2
  - Tune the generation rules so that the output fits the game mechanics more.
- Week 3
  - Finalize the algorithm tuning, start adding objects to the generated map.
- Week 4
  - Final polish for the visual output.

## Milestone 1 
Created the blueprint framework that reads the current map size and generate a map with randomized tile type. The current version is simply assigning types with a random number generator, but final version will be implemented with algorithms that generates map that make sense to the game mechanics.

Original hand-crafted map:

<img width="700" src="./Image/original_map.png"> 

Sample randomly generated maps:

<img width="700" src="./Image/random_map_1.png"> 

<img width="700" src="./Image/random_map_2.png"> 

<img width="700" src="./Image/random_map_3.png"> 

## Milestone 2
Implemented the main feature of Wave Function Collapse algorithm. The generated map now learns adjacency rules from the original hand-crafted map so that the placement of tiles should make more sense now. 

Original hand-crafted map altered to satisfy more adjacency rules:

<img width="700" src="./Image/original_map2.png"> 

Sample Wave Function Collapse algorithm generated maps:

<img width="700" src="./Image/WFC_map_1.png"> 

<img width="700" src="./Image/WFC_map_2.png"> 

<img width="700" src="./Image/WFC_map_3.png"> 

## Final submission
Added a feature of relocating actors to more meaningful locations after random map generation. (Successful)

Attempted to add a feature of resizing the map to have more tiles, but the plug-in does not seem to support tile count changes at runtime. (Code under BP_MapGenerator: functions RandomizedMap and ResizeMap)

Attempted to add a feature of spawn and despawn objects as tile type changes, but debugging takes way longer than expected. The hardest part is to correctly link each object to its corresponding tile and know when to destroy them. (Code under BP_FloorManager)

Sample actors relocated maps:

<img width="700" src="./Image/Actor_Relocated_WFC_map_1.png"> 

<img width="700" src="./Image/Actor_Relocated_WFC_map_2.png"> 

