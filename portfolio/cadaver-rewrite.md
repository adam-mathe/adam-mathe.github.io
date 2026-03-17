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

## Why did I make it?

Cadaver was a survival game I initally created in GameMaker Studio 2. I spent a long time on it and learned several things. Towards the end of its life cycle, I started to become frustrated with the performance of GameMaker and the limited control I had over seemingly basic things for a game engine.

I realized that the game I wanted to make would not be possible if I stayed in GameMaker Studio 2 so I set out to rewrite it.

## What have I implemented?

Currently the Cadaver Rewrite features:

* Infinite procedural world generation using simplex noise and a custom chunk library
* SDL2 for input and window management
* Serialization for saving and loading to and from world files
* An animation manager library which features frame triggers and an adjustable frame rate
* A custom game object which stores entities and handles delta time
* Finite State Machines for basic player and enemy controllers

To move away from GameMaker's object system I had to create my own Entity data structure:

<details markdown="1">

<summary><strong>View Entity Struct</strong></summary>

```c++
struct Entity
{
    V2 position = {0, 0};
    unsigned int flags;
    bool render = true;
    bool animation_enabled = true;
    Animation animation;
    Sprite sprite;
    Chunk* owner;
    struct 
    {
        int swings = 0;
        V2 last_direction;
        PlayerState state = PlayerState::idle;
        Animation* idle_animation;
        Animation* walk_animation;
        Animation* run_animation;
        Animation* swing_animation;
        Animation* stab_animation;
    }player;
    struct
    {
        V2 velocity = {0,0 };
        V2 target_velocity = {0, 0};
    } character;
    struct
    {
        EnemyState state = EnemyState::idle;
    } enemy;
    struct
    {
        float hp = 100;
    } life;
};
```

</details>

## What are my plans going forward?

While I will return to finish the game at some point, I do not plan to do it in the engine it's currently in. My mindset regarding the project has changed, and I do not want the codebase to rely on an external math library like GLM.

I have shifted my focus to [Rainstorm](rainstorm/) which will hopefully one day be the framework  Cadaver runs on.

## Source Code & Repository

[View Source Code](https://github.com/storm453/cadaver-rewrite.git)
