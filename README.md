# Universe-Simulator-Showcase
![An atmospheric planet encountered in the simulator](images/image-102.png)

An atmospheric planet encountered in the simulator.

# Table Of Contents
- [Introduction](#introduction)
    - [Links](#links)
    - [Important notes](#important-notes)
    - [What is this?](#what-is-this?)
    - [Why am I making this?](#why-am-i-making-this?)
- [How it works](#how-it-works)
    - [High level architecture](#high-level-architecture)
        - [Architecture diagram](#architecture-diagram)
        - [Entity Component Systems](#entity-component-systems)
        - [Networking for multiplayer](#networking-for-multiplayer)
    - [Galaxies](#galaxies)
        - [Galaxy generation](#galaxy-generation)
        - [Galaxy rendering](#galaxy-rendering)
    - [Stars](#stars)
      
    - [Planets](#planets)
        - [Planetary terrain generation](#planetary-terrain-generation)
        - [Planetary terrain rendering](#planetary-terrain-rendering)
        - [Planetary ocean generation](#planetary-ocean-generation)
        - [Planetary ocean rendering](#planetary-ocean-rendering)
        - [Atmospheric scattering](#atmospheric-scattering)
        - [Volumetric clouds](#volumetric-clouds)
  

# Introduction
## Links
Here are some links to other sites where you can see the development of my project as I continue to work on this README.
* https://abdualyajouri.artstation.com/
* https://www.youtube.com/@usualspace3247
  
## Important notes:
* The full engine source is private, but selected design/implementation details and visual demonstrations will be shown below.
* This project is a work in progress and some of the topics listed in the table of contents may not be complete

## What is this?
This is a hobby project of mine meant to serve as a videogame revolving around the exploration of space, as in, exploring other planets, galaxies, and even other universes. I used to develop it inside of Unreal Engine 4, however, in the last couple of years I have abandoned all game engines and essentially started writing my own just to implement this game, as I felt working in other game engines required too many custom changes to the engine source itself and there were just so many features in these engines that I didn't need. I also thought that it would be a great learning experience to try implementing a game engine on my own. Interestingly, while the engine itself is quite specialized for my game, the data structures and tools I have been writing are generic enough to be used for other games I may want to implement in the future.

## Why am I making this?
I have had a keen interest in the topic of space since I was in elementary school, gained through old astronomy books my family would have lying around the house and through newer books I would receive as gifts. The concept of exploring space fascinated me. At the same time, I had interests in computer programming and game development. One day, the trailer for a videogame called No Man's Sky released, which boasted the ability to fly through space, towards planets, and even land on them and walk around, which was completely insane to me as I had never seen a game like that before. It had shown me that something like that was possible, and inspired me to use my skills to try to make a videogame with the same feature.

# How it works

## High level architecture

### Architecture diagram
### Entity Component Systems
### Networking for multiplayer

## Galaxies
### Galaxy generation
### Galaxy rendering

## Stars

## Planets
Planets are a key phenomenon to consider when trying to simulate a universe. In my case, I want to provide the player with the experience of flying towards a planet (or moon) from deep space, entering its atmosphere (if it has one), landing on its surface, and exploring a very detailed surface hosting many of the common features you would expect an alien world to have. There are many problems that need to be solved in order to do this efficiently on a computer, and there are also many approaches one can take to solve said problems, which I will discuss over the next few sections.

NOTE: As of now, the only planet/moon type you can explore in the simulator are rocky planets with oceans. Though I have experimented with rendering full scale volumetric gas giants, I have not yet devised an optimized approach to handling them.

### Planetary terrain generation
When it comes to terrain generation in general, you need some way of defining the elevation or displacement of the terrain across a region of space. There are two main methods to do so, both having their own tradeoffs. One method is to simply use real world elevation data. The second method is to use procedural generation. With the first method, the benefit of using real world elevation data is that your terrain ends up looking quite realistic. The issues with this approach pertaining to my case, however, include:
* The need to externally source the elevation data, and depending on its format or resolution, the need to do some extra processing to be able to use it in the simulator.
* Storage space requirements for elevation samples (which I would need an impractical amount of given the effectively infinite number of planets you can encounter).
* The lack of variability among elevation samples (everything would have to be sourced from earth and the limited data from the surrounding planets and moons of our solar system).

When it comes to procedural generation, many of the issues with the first method can be overcome:
* All data is calculated directly on the computer, ideally in the same program, so this can eliminate the need to use any external data sources.
* Assuming the generation is completely deterministic, You do not need to permanently store any data at all, as the procedural generation algorithm is able to recalculate the exact same data on demand.
* 

So, for these reasons, I opted to use procedural generation to create my planetary terrain on the fly, without the need to store anything permanently. This entails using a variety of algorithms that are capable of efficiently producing smooth and natural patterns that closely resemble the terrain formations we are familiar with and more. There are some downsides to procedural generation however, in that unless you simulate

TO BE CONTINUED


### Planetary terrain rendering
### Planetary ocean generation
### Planetary ocean rendering
### Atmospheric scattering
### Volumetric clouds
