---
layout: default
title: Cadaver Rewrite
---

## Cadaver Rewrite

### I rewrote my GameMaker survival game from the ground up to achieve enhanced project control and performance.

2023 - 2025

**Tech**: `C++` `OpenGL` `SDL2` `GLM`

![Rewrite](images/cadaver-rewrite.png)

*A screenshot of the game in its current state. The world features infinite procedural generation with varying tiles and trees*

## Why did I rewrite it?

Cadaver was a survival game I initally created in GameMaker Studio 2. I spent a long time on it and learned several things. Towards the end of its life cycle, I started to become frustrated with the performance of GameMaker and the limited control I had over seemingly basic things for a game engine.

I realized that the game I wanted to make would not be possible if I stayed in GameMaker Studio 2 so I set out to rewrite it.

## What was the process like?

The Cadaver Rewrite was one of the hardest projects I've ever worked on. This game was my first ever foray into OpenGL and SDL2. Let alone the fact that I barely knew C++ at the time of starting, it was set out to be a difficult project.

Nonetheless, I stuck with it and slowly improved and adding onto the project.

## What have I implemented?

Currently the Cadaver Rewrite features:

* Infinite procedural world generation using simplex noise and a chunk library I wrote
* Entity serialization for saving and loadings chunks to and from world files
* An animation manager library which supports frame triggers and adjustable frame rate
* A custom game object which stores entities and handles delta time
* Finite State Machines for basic player and enemy controlers

## Source Code & Repository

[View Source Code](https://github.com/storm453/cadaver-rewrite.git)