---
title: Development Goals for Drugwars
layout: post
date: 2014-12-09 20:00:00
categories: drugwars
---

# The Current State of Development

While the game may appear to be far from finished, most of the groundwork necessary has been laid. Continued development will focus mostly on connecting these elements. Because of this, it may be necessary to alter the size of the teams, first with precedence given to game logic, and then to user interface in order to maximize productivity.

# Future Goals

## Game Logic

The majority of the basic classes for game logic have been completed. The path for game logic is as follows:

- Implement the basic classes needed
    - Convert Location to be an enum class
- Implement a game loop
    - Method to represent each turn
    - Method to switch locations
    - Methods to buy/sell drugs
        - Price modifiers
    - Add interest each turn (A=P*e*<sup>rt</sup>, anyone?)
    - Random police encounters

Having implemented this and wrapping it in a UI, the project will essentially be completed!

## User Interface

- Output player stats
- Output inventory
- Menus to move around and interact with inventory
- Put game loop here

# Conclusion

These are the goals for the baseline of the game implementation. If club members desire, more and more can be added on. And if the UI is implemented correctly, we can even implement a windowed GUI for the application as a learning excercise, or even make an Android app!

Additionally, we can go over packaging the application. That way, it can be distributed to other students in the school and they can see how fly we are.