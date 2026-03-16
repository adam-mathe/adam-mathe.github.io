---
layout: default
title: Rainstorm Project
---

## Rainstorm Framework

### Rainstorm is a 2D framework I am currently developing without the use of an external math library.

**Tech:** `C++` `OpenGL` `SDL2`

![Image](images/orthographic.png)

*A screenshot of the first time my perspective projection matrix from hand worked.*

Coming into this project I had a decent amount of experience with C++ and OpenGL, but I relied on GLM for matrix math.

With Rainstorm 2D, my goal is to learn the linear algebra behind graphics programming math by deriving and implementing each function by hand.

In the project so far, I have developed a matrix library which includes:
* Matrix multiplication
* Scaling matrices
* Translation matrices
* Othographic projection matrices

As this project continues, I plan to derive and implement arbitrary axis rotation completely on my own and implement a more stable projection matrix.

[View Source Code](https://github.com/storm453/rainstorm-framework)