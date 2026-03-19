<script>
  document.title = "Adam Mathe";
</script>

## Game AI Prototypes

### A collection of quick GameMaker prototypes made to learn various game AI algorithms.

2025 - 2026

**Tech**: `GameMaker Studio 2` `GameMaker Language` `GOAP` `BFS` `Dijkstra's Algorithm`

| ![Rewrite](images/heat.png) | ![goap](images/goap2.png) |
| :---: | :---: |
| *A screenshot showing the AI's sightlines and its heatmap logic used to predict the player's movement.* | *GOAP evaluates a statespace and returns the best path to a goal: Here you can see the path it decided to take in order to damage the player.* |

## Motivation Behind the Project

*Alien: Isolation* is one of my favorite games because it features the best game AI we have seen to date. Despite how good *Alien: Isolation* is, I still think more can be done with game AI.  

Hence, my goal with this project was to learn some common game AI algorithms and then see if I could come with something on my own to make them even better.

## Key Features

In various GameMaker prototypes I have implemented:
* A Dijkstra's algorithm implementation of Jeff Orkin's GOAP (Goal Oriented Action Planning) algorithm to navigate state spaces using the most efficient path.
* Breadth First Search so the AI can pathfind to the player.
* My own Heat Map system which the AI uses to predict player movement.
* Player movement prediction by using the player's velocity and the distance between the AI and player.
* Implementation of a raycasting system for AI line of sight. 

## Source Code & Repository

[View Source Code](https://github.com/adam-mathe/ai-prototypes)