<script>
  document.title = "Adam Mathe";
</script>

## Cadaver Rewrite

### I rewrote my GameMaker survival game from the ground up to achieve enhanced project control and performance.

2023 - 2025

**Tech**: `C++` `OpenGL` `SDL2` `GLM`

![Rewrite](images/cadaver-rewrite.png)

*A screenshot of the game in its current state. The world features infinite procedural generation with varying tiles and trees*

## Motivation Behind the Project

[Cadaver](/portfolio/cadaver) was a survival game I initally created in GameMaker Studio 2. Towards the end of its life cycle, I started to become frustrated with the performance of GameMaker and the limited control I had over seemingly basic things for a game engine.

I realized that the game I wanted to make would not be possible if I stayed in GameMaker Studio 2 so I set out to rewrite it.

## Key Features

Currently the Cadaver Rewrite features:

* Infinite procedural world generation using simplex noise and a custom chunk library
* SDL2 for input and window management
* Serialization for saving and loading to and from world files
* An animation manager library which features frame triggers and an adjustable frame rate
* A custom game object which stores entities and handles delta time
* Finite State Machines for basic player and enemy controllers

## Future Plans

While I will return to finish the game at some point, I do not plan to do it in the engine it's currently in. My mindset regarding the project has changed, and I do not want the codebase to rely on an external math library like GLM.

I have shifted my focus to [Rainstorm](/portfolio/rainstorm) which will hopefully one day be the framework  [Cadaver](/portfolio/cadaver) runs on.

## Source Code & Repository

[View Source Code](https://github.com/adam-mathe/cadaver-rewrite.git)
