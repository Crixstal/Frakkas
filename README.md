![shool_year](https://img.shields.io/badge/shool_year-second-blue)
![duration](https://img.shields.io/badge/duration-5_months-blue)  
![Manjaro](https://img.shields.io/badge/Manjaro-35BF5C?style=for-the-badge&logo=Manjaro&logoColor=white&style=plastic)
![Windows 10](https://img.shields.io/badge/Windows%2010-%230079d5.svg?style=for-the-badge&logo=Windows%2011&logoColor=white&style=plastic)
![Windows 11](https://img.shields.io/badge/Windows%2011-%230079d5.svg?style=for-the-badge&logo=Windows%2011&logoColor=white&style=plastic)  
![CMake](https://img.shields.io/badge/CMake-%23008FBA.svg?style=for-the-badge&logo=cmake&logoColor=white&style=plastic)

## Credits

All rights reserved for Frakkas team.  
[![Itch.io](https://img.shields.io/badge/Florian_MARCELLOT-%23FF0B34.svg?style=for-the-badge&logo=Itch.io&logoColor=white&style=flat&link=https://fura-x.itch.io/)](https://fura-x.itch.io/)
[![Itch.io](https://img.shields.io/badge/Jarod_SENGKEO-%23FF0B34.svg?style=for-the-badge&logo=Itch.io&logoColor=white&style=flat&link=https://sjarod.itch.io/)](https://sjarod.itch.io/)

https://user-images.githubusercontent.com/91843760/224386258-254d8523-1d9d-4059-bccc-330b3ea79203.mp4

# FRAKKAS ENGINE => 'FRAKKARENA'  

## Summary
1. [Frakkas](#frakkas)  
    1.1 [Description](#description)  
    1.2 [Open in an IDE](#open-in-an-ide)  
    1.3 [Update submodules](#update-submodules)  
2. [Frakkarena](#frakkarena)  
    2.1 [Controls](#controls)

# Frakkas  
  
## Description

The project's goal is to produce a game from an adapted homemade game engine. The project lasted 4 months, and we are a group of 3 second-year Game Programmer students, supervised by a fifth-year student.  
  
Our engine is called **_Frakkas_**, and our game **_Frakkarena_**. The game is a Top-Down Survival Beat'em up in a fantasy world, with a toon aspect. That was cool to code this game with the engine, and we could make whatever other type of game thanks to an efficient entity/component system.  
  
In short,  **_Frakkas_** is a 3D casual game engine, with animations, shadows, and toon shading.  

## Open in an IDE

If you are using CLion, just open the project directly with it.  
In case you are using Visual Studio Community/Enterprise 2022, check our [tutorial](Wiki/Launch_With_Visual_Studio.md).  

## Update submodules

The engine integrate several submodules.  
They are normally automaticaly update with the main CMakeLists.txt but in case you encounter problems here is three solutions:
1. In the project source directory, open a Git Bash command prompt and execute this command: `git submodule update --init --recursive`
2. In each submodule directory located in extern/ (ex: Frakkas/extern/tracy), execute this command in a Git Bash command prompt: `git checkout`
3. Contact us!

---

# Frakkarena

## Controls

- __Gamepad _(Xbox binding)___

Input                          | Action
-------                        | ------
Left stick / D-PAD             | Move
A / X                          | Attack
Right Trigger / B / Y          | Run
Start                          | Play / Pause  
D-PAD / A                      | Menu navigation  
    
- __Gamepad _(PS4 binding)___

Input                                   | Action
-------                                 | ------
Left stick / D-PAD                      | Move
cross / square                          | Attack
Right Trigger / circle / triangle       | Run
Options                                 | Play / Pause  
D-PAD / cross                           | Menu navigation  

- __Mouse / Keyboard (QWERTY)__

Input                          | Action
-------                        | ------
WASD / Arrows                  | Move
Space bar / Left click         | Attack
E / Left Shift / Right click   | Run
P / Esc                        | Play / Pause  
Arrows / Mouse / Space         | Menu navigation  

---

Looking for additionnal informations? Look at our [wiki](Wiki/README.md)!

[Head of page](#summary)
